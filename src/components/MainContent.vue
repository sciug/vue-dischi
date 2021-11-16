<template>
 <div>
     <Select/>

      <div class="row gy-4 justify-content-center" v-if="!loading">
      <div class="col-md-4 col-xl-2" v-for="album in albums" :key="album.title">
          <div class="album_card text-center">
              <div class="img_wrapper">
                  <img :src="album.poster" :alt="album.title" class="album_img">
              </div>
              
              <h5 class="text-white text-uppercase mt-3">{{album.title}}</h5>
               <h6 class="mb-0">{{album.author}}</h6>

              <h6 class="mt-0">{{album.year}}</h6>
          </div>
      </div>
      </div>
  <div v-else class="loading">
      
         
              <img src="../assets/img/spin.svg" alt="" class="spin">
              <p class="mt-2 loading_text">loading</p>

          
    
      
  </div>
 </div>
</template>

<script>
import axios from 'axios'
import Select from './Select.vue'
export default {
components:{
    Select
},
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
    transition: all 250ms;
    color: $info_color;
    padding: 1.3rem;
    background-color: $secondary-color;
    height: 330px;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.397);
    h5{
        font-size: 1rem;
        letter-spacing: .8px;
        font-weight: 700;
    }
    h6{
        font-weight: 400;
        letter-spacing: .5px;
    }&:hover{
        background-color:#384755ec;
        cursor: pointer;
    }
}

.loading{
    color: white;
    text-align: center;
    height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

}
.spin{
    width: 30px;
    animation: loading 1s ease infinite;
}

@keyframes loading {
    to{transform: rotate(1turn);}
    
}
.loading_text{
    letter-spacing: 1px;
}
.img_wrapper{
    width:100%;
    height: 155px;
    position: relative;
    &::after{
            content: "";    
    width: 100%;
    height: 100%;
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, rgba(34, 44, 56, 0) 15%, rgba(22, 22, 31, 0.788) 90%);
    mix-blend-mode: multiply;
    border-radius: 5px;
    cursor: pointer;

    }


}


.album_img{
    border-radius: 5px;
    width: 100%;
    height: 100%;
    object-fit: cover;
    cursor: pointer;

   
}


</style>