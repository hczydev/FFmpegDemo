# 如果您觉得本项目对你有用，请随手star，谢谢

本人试了一下，一个大小为341M，时长为05：13的视频，压缩时间为9分钟，可以通过改变分辨率和码率来进行压缩，有进度条显示

如果觉得ffmpeg压缩比较慢，而对视频清晰度要求不是那么高的话，可以使用硬解码的android自带的压缩方法MediaCodec ，速度嗖嗖的，MediaCodec的demo地址：https://github.com/tangpeng/VideoCompressor

关于权限的问题，可以看我的一篇文章：https://www.jianshu.com/p/52795b5dab3a  
项目里面的权限判断使用的是朋友封装好的库，很方便，一句代码搞定 


```
    /**
     * @dec 一句代码搞定权限问题
     * @author apeng
     * @date 2018/10/31 10:54
     */
    public void getPermissions() {
        XXPermissions.with(this)
                .constantRequest() //可设置被拒绝后继续申请，直到用户授权或者永久拒绝
                .permission("android.permission.READ_EXTERNAL_STORAGE", "android.permission.WRITE_EXTERNAL_STORAGE")
                .request(new OnPermission() {
                    @Override
                    public void hasPermission(List<String> granted, boolean isAll) {
                    }

                    @Override
                    public void noPermission(List<String> denied, boolean quick) {

                    }
                });

    }
    ```
## Demo
![Demo](/pic/20181031154801.png)
