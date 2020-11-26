<template>
  <div class="video">
    <H1 class="con">{{video}}</H1>
    <div class="video-wrap">
      <video-player class="vjs-custom-skin" :options="playerOptions"></video-player>
    </div>
  </div>
</template>

<script>
  // require styles
  import 'video.js/dist/video-js.css' // 引入样式
  import 'vue-video-player/src/custom-theme.css' // 引入样式
  // video-player
  import { videoPlayer } from 'vue-video-player'
  // rtmp video-flash
  import 'videojs-flash'
  export default {
    name: 'HelloWorld',
    data () {
      return {
        video: 'HELLO RTMP VIDEO',
        playerOptions: {
          sources: {
            type: 'rtmp/mp4',
            src: 'rtmp://172.17.207.240:1935/live/openUrl/RYnoGEU/'
          },
          techOrder: ['flash'],
          autoplay: true,
          height:600
        }
      }
    },
    components: {
      videoPlayer
    },
    mounted() {},
    methods: {}
  }
</script>

<style lang="less" scoped>
  .video {
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
  .con {
    width: 100%;
    height: 30px;
    line-height: 30px;
  }
  .video-wrap {
    width: 1000px;
    height: 600px;
    margin: 0 auto;
  }
  }
</style>
