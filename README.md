# videojs_learn

+ RTMP with flash
+ hls
## ffmpeg 推流 rtsp -> rtmp
```
 ffmpeg -rtsp_transport tcp -i "rtsp://admin:Aa123456@192.168.15.193:554/h265/ch1/main/av_stream" -f flv -r 25 -s 1920x1080 -an rtmp://localhost:1935/myapp/live
```

## ffmpeg 推流 rtsp -> hls
```
ffmpeg -rtsp_transport tcp -i "rtsp://admin:Aa123456@192.168.15.193:554/h264/ch1/main/av_stream" -strict -2 -c:v libx264 -c:a aac -f hls /nginx/www/hls/live.m3u8
```

## 播放
```
视频播放使用videojs组件

rtmp：
    播放依赖 flash
    画质一般
    延迟低 大概2s左右

hls：
    播放不依赖 flash
    画质较好
    延迟高，服务器目前大概在25s+
```

## 服务器环境
```
依赖 nginx-rtmp-module 需使用自编译nginx
```

