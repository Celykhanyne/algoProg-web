<template>
<div>
  <cam-component></cam-component>
  <load-file @new-url="updateURL"></load-file>
  <ascii-display :imgURL="myUrl"></ascii-display>
  <download-file img=""></download-file>
</div>
</template>

<script>
import AsciiDisplay from './components/AsciiDisplay.vue'
import LoadFile from './components/LoadFile.vue'
import DownloadFile from './components/DownloadFile.vue'
import CamComponent from './components/camComponent.vue'


export default {
  name: 'App',
  components: {
    LoadFile,
    AsciiDisplay,
    DownloadFile,
    CamComponent
  },
  data(){
    return{
      myUrl:""
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
