<template>
<div id="main-div">
  <ascii-header></ascii-header>
  <!-- <cam-component></cam-component> -->
  <load-file @new-url="updateURL"></load-file>
  <ascii-display :imgURL="myUrl"></ascii-display>
  <download-file :img="myUrl"></download-file>
  <ascii-footer></ascii-footer>
</div>
</template>

<script>
import AsciiDisplay from './components/AsciiDisplay.vue'
import LoadFile from './components/LoadFile.vue'
import DownloadFile from './components/DownloadFile.vue'
// import CamComponent from './components/camComponent.vue'
import AsciiFooter from './components/AsciiFooter.vue'
import AsciiHeader from './components/AsciiHeader.vue'


export default {
  name: 'App',
  components: {
    LoadFile, // TODO définir une limite de taille d'image pour éviter les mauvaises surprises
    AsciiDisplay,
    // CamComponent,
    DownloadFile,
    AsciiFooter,
    AsciiHeader,
  },
  data(){
    return{
      myUrl:"" // TODO give not the url of the upload, but the result of the ascii conversion to the download component
    }
  },
  methods: {
    updateURL(newUrl) {
      this.myUrl=newUrl 
    },
},
}
</script>

<style>
  #main-div {
    font: 1.2em "Fira Sans", sans-serif;

    /* min-height:100vh; */

    display:flex;
    flex-direction:column;
    justify-content:stretch;
    align-items: center;
  }

  
  button {
    font-size: 1em;
    background-color: #e7e7e7;
    border: none;
    padding-top:3%;
    padding-bottom:3%;

    transition-duration: 0.4s;

  }

  button:hover {
    background-color: #555555;
    color:white;
  }


</style>
