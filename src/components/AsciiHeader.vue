<template>
<header>
  <h1>Ascii Generator</h1>
  <img src="../assets/ascii-logo.png" alt="ASCII logo">
  <p>Transform your pictures into ASCII art !</p>
</header>
</template>

<script>
export default {
  name: 'AsciiHeader'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  header {
    
    display:flex;
    flex-direction: column;
    justify-content: center;

    margin-top:5%;
  }

  h1 {
    margin-left:10%;
  }

  img {
    margin-left: -5%;
  }
</style>