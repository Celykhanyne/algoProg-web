<template>
    <footer>
      <div id="authors">
        <p>Made by </p>
        <p>Jules Chapelle & Emma Ledru</p>
      </div>
      <div id="school">
        <img src="../assets/cnam-logo.jpg" alt="Cnam-ENJMIN logo">
        <p>STMN web project</p>
        <p>april 2021</p>
      </div>
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
    margin-top:4%;

    background-color: #e7e7e7;
    border-radius: 4px;

    display: flex;
    flex-direction: row;
    justify-content: flex-end;
  }

  img {
    width: 70px;
    height: 50px;

    margin-right:3%;
    margin-top: 5%;
  }

  #authors {
    margin-right: 10%;
    margin-left: 3%;
  }

  #school {
    margin-top:3%;

    display: flex;
    flex-direction: row;
  }


</style>