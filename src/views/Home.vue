<template>
  <div class="home">
    <video id='myvideo' width=960 height=540 class="video-js vjs-default-skin" controls>
      <!-- RTMP直播源地址-->
      <source src="rtmp://192.168.15.101:21935/myapp/live">    
      <!-- <source src="rtmp://192.168.15.101:21935/live/room">    -->
    </video>
  </div>
</template>

<script>
// @ is an alias to /src
import video from "video.js"
import "videojs-flash"
import "video.js/dist/video-js.css"
export default {
  name: 'Home',
   mounted(){
    console.log("init")
    let play = video("myvideo",{},function(){
      console.log("vide init")
    });
    play.play();
  },
  components: {
  }
}
</script>
