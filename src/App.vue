<template>
<div>
  <cam-component @cam-send="camUrlUp"></cam-component>
  <load-file @new-url="updateURL"></load-file>
  <ascii-display :imgURL="myUrl" :camLinkUrl="camLink"></ascii-display>
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
      myUrl:"",
      camLink:""
    }
  },
  methods: {
    updateURL(newUrl) {
      this.myUrl=newUrl
    },
    camUrlUp(camUrlSend)
    {
      this.camLink = camUrlSend
    }
},
}
</script>

<style>
</style>
