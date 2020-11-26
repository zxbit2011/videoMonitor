# video_monitor

> RTMP视频流播放

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

## 注意事项
* 安装完成后能在package.json里查看到版本号
````
    "vue-video-player": "^5.0.2",
    "videojs-flash": "^2.2.1",
````
* 引用包的先后顺序
````
  // require styles
  import 'video.js/dist/video-js.css' // 引入样式
  import 'vue-video-player/src/custom-theme.css' // 引入样式
  // video-player
  import { videoPlayer } from 'vue-video-player'
  // rtmp video-flash
  import 'videojs-flash'
````
* rtmp地址后面/斜杠问题
> 如rtmp://192.168.142.70:1935/Vehicle
  在项目中需要写成rtmp://192.168.142.70:1935/Vehicle/

## 预览效果
![预览效果](test.png)
