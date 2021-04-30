<template>
    <footer>
        <p id="authors">Made by Jules Chapelle and Emma Ledru</p>
        <p>IEM (Cnam-Enjmin) web project, april 2021</p>
    </footer>
</template>

<script>
export default {
  name: 'AsciiFooter'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  footer {
    display: flex;
    flex-direction: row;
    justify-content: end;
  }

  #authors {
    margin-right: 3%;
  }
</style>