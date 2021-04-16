<template>
<div>
  <load-file @new-url="updateURL"></load-file>
  <ascii-display :imgURL="myUrl"></ascii-display>
</div>
</template>

<script>
import AsciiDisplay from './components/AsciiDisplay.vue'
import LoadFile from './components/LoadFile.vue'

export default {
  name: 'App',
  components: {
    LoadFile,
    AsciiDisplay

  },
  data(){
    return{
      myUrl:""
    }
  },
  methods: {
    updateUrl(newUrl) {
      this.myUrl=newUrl
    },
},
}
</script>

<style>
</style>
