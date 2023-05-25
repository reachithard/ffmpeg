# FFmpeg开源库学习

本文章研究的ffmpeg代码为`4.2.9`，稍微有点出入，本人没使用tag包。

FFmpeg是一套可以用来记录、转换[数字音频](https://baike.baidu.com/item/数字音频/5942163?fromModule=lemma_inlink)、视频，并能将其转化为流的开源计算机[程序](https://baike.baidu.com/item/程序/13831935?fromModule=lemma_inlink)。采用[LGPL](https://baike.baidu.com/item/LGPL/10583469?fromModule=lemma_inlink)或[GPL](https://baike.baidu.com/item/GPL/2357903?fromModule=lemma_inlink)许可证。它提供了录制、转换以及流化音视频的完整解决方案。它包含了非常先进的音频/视频编解码库libavcodec，为了保证高[可移植性](https://baike.baidu.com/item/可移植性/6931884?fromModule=lemma_inlink)和编解码质量，libavcodec里很多code都是从头开发的。

[多媒体视频](https://baike.baidu.com/item/多媒体视频/1153166?fromModule=lemma_inlink)处理工具FFmpeg有非常强大的功能包括[视频采集](https://baike.baidu.com/item/视频采集/3430654?fromModule=lemma_inlink)功能、[视频格式转换](https://baike.baidu.com/item/视频格式转换/9399376?fromModule=lemma_inlink)、视频[抓图](https://baike.baidu.com/item/抓图/317285?fromModule=lemma_inlink)、给视频加水印等。



## 数据流

```
 _______              ______________
|       |            |              |
| input |  demuxer   | encoded data |   decoder
| file  | ---------> | packets      | -----+
|_______|            |______________|      |
                                           v
                                       _________
                                      |         |
                                      | decoded |
                                      | frames  |
                                      |_________|
 ________             ______________       |
|        |           |              |      |
| output | <-------- | encoded data | <----+
| file   |   muxer   | packets      |   encoder
|________|           |______________|

```



## 项目目录结构

可看后面英文的详细解释

```
.
├── compat
├── doc
├── ffbuild
├── fftools // 这里放的ffplay ffmpeg ffprobe工具
├── libavcodec // encode/decode库 encoding/decoding library
├── libavdevice // 设备的mux和demux库 special devices muxing/demuxing library
├── libavfilter // 图向的frame编辑库 graph-based frame editing library
├── libavformat // 输入输出的mux/demux库 I/O and muxing/demuxing library
├── libavutil // 公共函数库 common utility library
├── libpostproc // 后处理库 post processing library
├── libswresample // 音频重采样、格式转换和混音 audio resampling, format conversion and mixing
├── libswscale // 颜色转换和缩放库 color conversion and scaling library
├── presets
├── tests
└── tools
```

其余文件见项目。



## IBP帧



## DTS和PTS



## frame rate帧率



