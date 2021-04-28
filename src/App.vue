<template>
<div>
  <ascii-header></ascii-header>
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
import AsciiFooter from './components/AsciiFooter.vue'
import AsciiHeader from './components/AsciiHeader.vue'


export default {
  name: 'App',
  components: {
    LoadFile, // TODO définir une limite de taille d'image pour éviter les mauvaises surprises
    AsciiDisplay,
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
</style>
