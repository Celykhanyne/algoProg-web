<template>
<form>
    <label for="chooseImageBtn">choisir une image</label>
    <input id="chooseImageBtn" @change="getImage" type="file" accept="image/png, image/jpeg/" >
    <img :src="render">
</form>
</template>

<script>
export default {
  emits:["newUrl"],
  data(){
    return{
      render:null
    }
  },
    methods: {
    getImage(event)
    {
      let reader = new FileReader(event.target.files[0]);
      reader.onload=(e) => {
        this.render = e.target.result;
        this.$emit('newUrl', this.render);
        console.log(e.target.result,this)
      }
      reader.readAsDataURL(event.target.files[0]);
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
