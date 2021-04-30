<template>
<div >
    <button v-on:click="startWebcam()">Start WebCam</button>
    <button v-on:click="stopWebcam()">Stop WebCam</button> 
    <button v-on:click="snapshot()">Take Snapshot</button> 
    <a class="startHidden"></a>
    <video v-on:click="snapshot()" width=400 height=400 id="video" controls autoplay></video>
    <canvas  id="myCanvas" width="400" height="350"></canvas> 
</div>
</template>

<script>
      var video;
      var webcamStream;
      var canvas, ctx;
      navigator.getUserMedia = ( navigator.getUserMedia ||
                navigator.webkitGetUserMedia ||
                navigator.mozGetUserMedia ||
                navigator.msGetUserMedia);
export default {
    emits:["camSend"],
    mounted:function(){
        this.init()
  },
    methods:{
      startWebcam() {
        if (navigator.getUserMedia) {
           navigator.getUserMedia (

              // constraints
              {
                 video: true,
                 audio: false
              },

              // successCallback
              function(stream) {
                video = document.querySelector('video');
                video.srcObject = stream;
                video.play();
              },

              // errorCallback
              function(err) {
                 console.log("The following error occured: " + err);
              }
           );
        } else {
           console.log("getUserMedia not supported");
        }  
      },
      stopWebcam() {
          webcamStream.stop();
      },
      //---------------------
      // TAKE A SNAPSHOT CODE
      //---------------------
      init() {

        canvas = document.getElementById("myCanvas");
        ctx = canvas.getContext('2d');
      },
      snapshot() {
         // Draws current image from the video element into the canvas
        ctx.drawImage(video, 0,0, canvas.width, canvas.height);
        canvas.toBlob(function(blob){
            var a = document.querySelector('a');
            a.href =URL.createObjectURL(blob);
            document.body.appendChild(a);
        },'image/png');
        var a = document.querySelector('a');
        this.$emit('camSend', a.href);
      }
    }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .startHidden{
        visibility: collapse;
    }
</style>