<template>
<div id="main-div">
  <ascii-header></ascii-header>
  <cam-component @cam-send="camUrlUp"></cam-component>
  <load-file @new-url="updateURL"></load-file>
  <ascii-display :imgURL="myUrl" :camLinkUrl="camLink"></ascii-display>
  <ascii-footer></ascii-footer>
</div>
</template>

<script>
import AsciiDisplay from './components/AsciiDisplay.vue'
import LoadFile from './components/LoadFile.vue'
import CamComponent from './components/camComponent.vue'
import AsciiFooter from './components/AsciiFooter.vue'
import AsciiHeader from './components/AsciiHeader.vue'


export default {
  name: 'App',
  components: {
    LoadFile,
    AsciiDisplay,
    CamComponent,
    AsciiFooter,
    AsciiHeader,
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
  #main-div {
    font: 1.2em "Fira Sans", sans-serif;

    display:flex;
    flex-direction:column;
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
