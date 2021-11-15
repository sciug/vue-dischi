<template>
  <div class="row">
      <div class="col-md-2" v-for="album in albums" :key="album.title">
          <div class="album_card">
              <img :src="album.poster" :alt="album.title" class="img-fluid">
              <h3>{{album.author}}</h3>
              <h4>{{album.year}}</h4>
          </div>
      </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
data(){
    return{
         albums:[],
         Api_URL:"https://flynn.boolean.careers/exercises/api/array/music",
         loading: true,
         error:""
    }
   
},
mounted(){
    setTimeout(this.callApi, 3000)

},
methods:{
    callApi(){
        axios
        .get(this.Api_URL)
        .then(response =>{
            console.log(response.data.response)
            this.albums = response.data.response
            this.loading= false

        }).catch(e =>{
            console.log(e, "oops error");
            this.error= e
        })
    }
}
}
</script>

<style lang="scss">
@import '../assets/scss/variables.scss';
.album_card{
    color: $info_color;
    padding: 1rem;
    background-color: $secondary-color;
}

</style>