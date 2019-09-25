## Animation

### 帧动画
> AnimDrawableActivity

    帧动画：加载一系列的图片资源，一张一张的显示播放。
    代码实现步骤
        1. 在res/drawable目录下创建一个xml文件，根节点是<animation-list>；
            并可以配置oneshot属性表示动画是否播放一次活反复播放。
        2. 在xml文件内添加图片资源，以及设置图片播放的时长。
        3. 在Activity中为指定的ImageView设置背景资源，然后再获取背景并转换成AnimationDrawable并开启动画
        
### 补间动画
>AnimViewActivity
  + 透明动画（AlphaAnimation）
          AlphaAnimation(float fromAlpha, //开始的透明度，取值0-1（0表示完全透明，1表示完全不透明）
                         float toAlpha)   //结束的透明度，取值0-1（0表示完全透明，1表示完全不透明）

### 属性动画
>AnimPropertyActivity
