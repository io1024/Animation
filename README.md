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
     
    动画效果不会改变控件的位置
        
  + 透明动画（AlphaAnimation）
  
          AlphaAnimation(float fromAlpha, //开始的透明度，取值0-1（0表示完全透明，1表示完全不透明）
                         float toAlpha)   //结束的透明度，取值0-1（0表示完全透明，1表示完全不透明）
  + 旋转动画（RotateAnimation）
  
          //该构造器方式：设置的旋转中心:是图片的左上角（0,0）的位置
          RotateAnimation(float fromDegrees, //开始角度
                          float toDegrees)   //旋转到的角度
          //该构造器方式：可以设置旋转中心
          RotateAnimation(float fromDegrees,
                          float toDegrees,
                          int pivotXType,    //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                          float pivotXValue,
                          int pivotYType,    //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                          float pivotYValue)
  + 位移动画（TranslateAnimation）  
  
          //toXValue：该参数表示的是：相对于参照物的宽度的倍数，慎用整数
          //toYValue：该参数表示的是：相对于参照物的高度的倍数，慎用整数
          TranslateAnimation(int fromXType,    //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                             float fromXValue, //相对于参照物的位置（0是参照物左边缘，1是参照物右边缘）
                             int toXType,      //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                             float toXValue,   //移动到什么位置：参照物宽度的多少倍
                             int fromYType,    //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                             float fromYValue, //相对于参照物的位置（0是参照物左边缘，1是参照物右边缘）
                             int toYType,      //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                             float toYValue)   //移动到什么位置：参照物高度的多少倍

         //float fromXDelta, float toXDelta：X轴的开始位置、X轴的结束位置（移动了多少像素：toXDelta - fromXDelta）
         //float fromYDelta, float toYDelta：Y轴的开始位置、Y轴的结束位置（移动了多少像素：toXDelta - fromXDelta）
         //X轴、Y轴的开始位置和结束位置都是相对于自身的位置去设定的，且值不限制正负。
         TranslateAnimation(float fromXDelta, float toXDelta, float fromYDelta, float toYDelta)
  
  + 缩放动画（ScaleAnimation）
  
         //参照物：Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
         ScaleAnimation(float fromX, float toX, //X轴:从几倍开始,缩放到几倍
                        float fromY, float toY, //Y轴:从几倍开始,缩放到几倍
                        int pivotXType,    //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                        float pivotXValue, //相对于参照物的位置（0是参照物左边缘，1是参照物右边缘）
                        int pivotYType,    //Animation.ABSOLUTE、RELATIVE_TO_SELF、RELATIVE_TO_PARENT
                        float pivotYValue) //相对于参照物的位置（0是参照物左边缘，1是参照物右边缘）
    
  + 组合动画（AnimationSet）
  
         组合动画 AnimationSet 设置 setRepeatCount 和 setRepeatMode 无效果，需要在每个动画中单独的设置。
                          

### 属性动画
>AnimPropertyActivity

    属性动画：会改变控件的位置！！（与补间动画最大的区别）

  + 获取属性动画对象（ObjectAnimator）
  
    //获取一个指定动画的对象：ObjectAnimator的静态函数
    ofFloat(Object target,       //执行的目标（谁执行动画）
            String propertyName, //指定动画的属性名称
            float... values)     //可变参数，表示移动到的位置
