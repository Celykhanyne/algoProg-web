<template>
  <div class="download-file">
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
      onClickDwnloadFile(ev) {
          console.log(ev)
      }
  },
  props: {
      img: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>