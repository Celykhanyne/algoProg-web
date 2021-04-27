<template>
<div>
  <load-file @new-url="updateURL"></load-file>
  <ascii-display :imgURL="myUrl"></ascii-display>
  <download-file :img="myUrl"></download-file>
</div>
</template>

<script>
import AsciiDisplay from './components/AsciiDisplay.vue'
import LoadFile from './components/LoadFile.vue'
import DownloadFile from './components/DownloadFile.vue'


export default {
  name: 'App',
  components: {
    LoadFile,
    AsciiDisplay,
    DownloadFile
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
