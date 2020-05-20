<template>
  <div>
    <video id='myvideo' width=960 height=540 class="video-js vjs-default-skin" controls>
      <source src="http://192.168.15.101:28080/hls/live.m3u8">    
    </video>
  </div>
</template>

<script>
// @ is an alias to /src
import videojs from "video.js"
import "video.js/dist/video-js.css"
export default {
  name: 'About',
  mounted(){
    console.log("init")
    let play = videojs("myvideo",{},function(){
      console.log("vide init")
    });
    play.play();
  },
  components: {
  }
}
</script>
