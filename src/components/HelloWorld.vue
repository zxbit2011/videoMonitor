<template>
  <div class="video">
    <div style="width: 50%">
      <H1 class="con">{{video}}</H1>

      <div class="video-wrap">
        <video-player class="vjs-custom-skin" :options="playerOptions"></video-player>
      </div>
      <br>
      <H1 class="con">{{video2}}</H1>
      <div class="video-wrap">
        <video-player class="video-player vjs-custom-skin" :options="playerOptions2"></video-player>
      </div>
    </div>
    <div v-html="readme" class="markdown-body" style="width: 40%;text-align: left;margin: 0 auto"></div>
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
  import 'videojs-contrib-hls'
  import 'github-markdown-css'
  import readme from '../../README.md'
  export default {
    name: 'HelloWorld',
    data () {
      return {
        video: 'HELLO RTMP VIDEO',
        video2: 'HELLO HLS VIDEO',
        playerOptions: {
          sources: {
            type: 'rtmp/mp4',
            src: 'rtmp://172.17.207.240:1935/live/openUrl/8UEOtgY/'
          },
          techOrder: ['flash'],
          autoplay: true,
          height:600
        },
        playerOptions2: {
          playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度
          autoplay: true, //如果true,浏览器准备好时开始回放。
          controls: true, //控制条
          preload: 'auto', //视频预加载
          loop: false, //导致视频一结束就重新开始。
          language: 'zh-CN',
          aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
          fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
          sources: [{
            type: 'application/x-mpegURL',
            src: '/openUrl/1fpty3S/live.m3u8'
          }],
          poster: "https://avatar.csdnimg.cn/E/9/1/3_ffffffff8.jpg", //你的封面地址
          width: document.documentElement.clientWidth,
          notSupportedMessage: '此视频暂无法播放，请稍后再试' //允许覆盖Video.js无法播放媒体源时显示的默认信息。
        },
        readme:readme
      }
    },
    components: {
      videoPlayer
    },
    mounted() {
    },
    methods: {}
  }
</script>

<style lang="less" scoped>
  .video {
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
    display: flex;
  .con {
    width: 100%;
    height: 30px;
    line-height: 30px;
  }
  .video-wrap {
    width: 100%;
    height: 600px;
    margin: 0 auto;
  }
  }
</style>
