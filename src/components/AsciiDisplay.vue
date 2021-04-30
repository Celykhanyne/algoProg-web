<template>
<div id="display">
    <img :src="image" class="collapse-img" />
    <pre class="aa-image">
    </pre>
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
    var byteString = atob(this.imgURL.split(',')[1]);

    // separate out the mime component
    var mimeString = this.imgURL.split(',')[0].split(':')[1].split(';')[0]

    // write the bytes of the string to an ArrayBuffer
    var ab = new ArrayBuffer(byteString.length);
    var ia = new Uint8Array(ab);
    for (var i = 0; i < byteString.length; i++) {
        ia[i] = byteString.charCodeAt(i);
    }

    // write the ArrayBuffer to a blob, and you're done
    let blob = new Blob([ab], {type: mimeString});

      let url = URL.createObjectURL(blob);
      this.image = url
      aalib.read.image.fromURL(url)
        .map(aalib.filter.contrast(0.9))
        .map(aalib.aa({ width: 250, height: 90 }))
        .map(aalib.filter.brightness(10))
        .map(aalib.render.html({ el: document.querySelector(".aa-image")}))
        .subscribe();
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