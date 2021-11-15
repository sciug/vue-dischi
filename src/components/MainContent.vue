<template>
  <div class="row gy-3">
      <div class="col-2" v-for="album in albums" :key="album.title">
          <div class="album_card text-center">
              <img :src="album.poster" :alt="album.title" class="img-fluid">
              <h5 class="text-white text-uppercase mt-3">{{album.title}}</h5>
               <h6 class="mb-0">{{album.author}}</h6>

              <h6 class="mt-0">{{album.year}}</h6>
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
    padding: 1.3rem;
    background-color: $secondary-color;
    height: 330px;
}

</style>