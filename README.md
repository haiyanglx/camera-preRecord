# camera-preRecord
qcom camera preRecord in Native framework
从android framework层，实现监控预录功能，原理就是从mediaCodecSource获取帧数据后，进行缓存，不直接写文件，等到正式录像开始后，就把缓存的数据一次性写入文件中。
