<template>
  <div class="row justify-content-center">
    <div class="col-4">
       <select name="author" id="author" class="select" @change="log">
                    <option value="Bon Jovi"><span>Bon Jovi</span></option>
                    <option value="Queen"><span>Queen</span></option>
                    <option value="Sting"><span>Sting</span></option>
                    <option value="Steve Gadd Band"><span>Steve Gadd Band</span></option>
                    <option value="Iron Maiden"><span>Iron Maiden</span></option>
                    <option value="Deep Purple"><span>Deep Purple</span></option>
                    <option value="Metallica"><span>Queen</span></option>
                    <option value="Dave Weckl"><span>Sting</span></option>
                    <option value="Michael Jacjson"><span>Queen</span></option>
        </select>

    </div>
       
  </div>
</template>

<script>
export default {
  data(){
    return{
      filterAuthor: document.getElementById("author")
    }
  },
  methods:{
    log(){
      console.log(this.filterAuthor)
    }
  }
    

}
</script>

<style>
.select{
    width: 100%;
    padding: .3rem 1rem;
    border-radius: 10px;
}

</style>