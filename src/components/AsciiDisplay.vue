<template>
<div>
    <img :src="imgURL" class="collapse-img" />
    <img class=".aa-image" />
</div>
</template>

<script>
const aalib = require("aalib.js");
export default {
    props: {
    imgURL: String,
  },
  methods:{
    OnImgUrlChange(){
      console.log(this.imgURL);
          let test = aalib.read.image.fromHTMLImage(document.querySelector(".collapse-img"))
    .map(aalib.filter.contrast(0.9))
    .map(aalib.aa({ width: 530, height: 160 }))
    .map(aalib.filter.brightness(10))
    .map(aalib.render.html({ el: document.querySelector(".aa-image") }))
    console.log(test);
    test.subscribe();
    }
  },
  watch:{
    imgURL: function () {
      this.OnImgUrlChange();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>