<template>
  <div class="row justify-content-center">
    <div class="col-4">
       <select v-model="selected" name="author" id="author" class="select" @change="$emit('filter-author', selected)" placeholder="select author">
                    <option value="Bon Jovi"><span>Bon Jovi</span></option>
                    <option value="Queen"><span>Queen</span></option>
                    <option value="Sting"><span>Sting</span></option>
                    <option value="Steve Gadd Band"><span>Steve Gadd Band</span></option>
                    <option value="Iron Maiden"><span>Iron Maiden</span></option>
                    <option value="Deep Purple"><span>Deep Purple</span></option>
                    <option value="Metallica"><span>Metallica</span></option>
                    <option value="Dave Weckl"><span>Dave Weckl</span></option>
                    <option value="Michael Jacjson"><span>Michael Jacjson</span></option>
        </select>

    </div>
       
  </div>
</template>

<script>
export default {
  data(){
    return{
      selected: ""
    }
  },
 
    

}
</script>

<style>
.select{
    width: 100%;
    padding: .3rem 1rem;
    border-radius: 10px;
}

</style>