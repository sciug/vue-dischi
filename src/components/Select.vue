<template>
  <div class="row justify-content-center">
    <div class="col-4">
      <!-- <label for="author" class="select-label">select author</label>
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
        </select> -->
        <label for="genre" class="select-label">select genre</label>
       <select v-model="selected" name="genre" id="genre" class="select" @change="$emit('filter-genre', selected)" placeholder="select author">
                    <option value="Rock"><span>Rock</span></option>
                    <option value="Jazz"><span>Jazz</span></option>
                    <option value="Metal"><span>Metal</span></option>
                    <option value="Pop"><span>Pop</span></option>
                   
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
.select-label{
  color: white;
  letter-spacing: 1px;
  font-size: .8rem;
  order: 2;
}

</style>