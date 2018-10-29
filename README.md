# camera-preRecord
0701更新：
qcom camera preRecord in Native framework
从android framework层，实现监控预录功能，原理就是从mediaCodecSource获取帧数据后，进行缓存，不直接写文件，等到正式录像开始后，就把缓存的数据一次性写入文件中。


0913更新：
添加文件分段功能，从framework 层进行文件分段，不停止cameraSource，只停止 mpeg4Writer,目前测试两个相邻文件差距不到0.1s（source数据不丢帧）

1029更新：
1，因为某些机器音频一直开着会导致没有音频数据输出，所以再分段结束时，停止音频，再开启音频
2，因为某些播放器不支持播放的第一帧为非关键帧，导致黑屏，添加保证第一帧为关键帧
