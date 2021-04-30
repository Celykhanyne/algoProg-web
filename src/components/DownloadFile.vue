<template>
  <div id="download-file">
    <h1>Download file</h1>
    <p>
      To save your beautiful piece of art ~
    </p>
    <button v-on:click="onClickDwnloadFile">Download result</button>
  </div>
</template>

<script>
export default {
  name: 'DownloadFile',
  methods: {
      onClickDwnloadFile() {
        let a = document.createElement('a');
        a.href = this.img;
        a.download = "output.png";
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
      }
  },
  props: {
      img: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #download-file {
    margin-top: 2%;
    margin-bottom: 3%;

    display:flex;
    flex-direction: column;
    justify-content: center;
  }

  h1 {
  padding-left: 4%;;
  margin-bottom: -1%;
  }

  button {
    padding-left: -10%;
    padding-right: -10%;
    
  }

</style>