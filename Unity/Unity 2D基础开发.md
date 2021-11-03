# Unity 2D基础开发

## Tilemap的使用

* 切片
  * Windows中选中2D打开Pile Palette
  * 新建map
  * 选中需要切片的素材，在Inspector窗口设置Sprite Mode为Multiple
  * 在Inspector窗口打开Sprite Editor，选择slice
  * 更改type为Grid By Cell Size，填写像素大小
  * 再点击slice
  * 将切好的素材拖入Tile Palette中即可
* 切片间隙解决方法
  * 在Hierarchy中选中算需要修改的Tilemap（Grid），修改Cell Size至更小即可
* 摸索的技巧
  * 可以一层Tilemap做地面，另一层绘制背景，但需要注意两者之间的偏移量要保持一致，否则会出现错位。

## 图层

* 可以通过两个属性调整图层之间的显示状态
  * Sorting Layer
    * 创建图层，排序越下的越靠前。
  * Order In Layer
    * 排序越大，越靠前。

## 对象创建

* 直接在Hierarchy窗口右键new需要的对象。
* 选中对象，在Inspector中添加各式各样的组件或脚本。

## 动画

* 动画的创建
  * 为对象添加Animator组件，创建一个Animator文件加载进组件中。
  * 打开Animation窗口，新建一个Animation文件，将素材拖入，然后进行调试动画效果。

* 动画的切换
  * 打开Animator，为各个动画之间设置连线。
  * 在Parameters中添加类型。
  * 并选中连线，设置切换的类型条件。
  * 将Animator传入Script中，编写相应的代码达到切换。
* 技巧
  * 特殊函数（如死亡）需要在一个动画结束后调用，可以在动画结尾添加一个event，event调用Script中的函数。

## 镜头控制

* 简单粗暴法
  * 在Main Camera中编写Script，令其Transform的position中x,y轴与player的Transform中position中x,y轴相等。
* Cinemachine
  * 创建
    * 在Packages中下载Cinemachine（有旧版本时先移除）
    * 2021版本中，选中GameObject，选中Cinemachine，创建一个2D Camera。
    * 调整参数。
* 使用Cinemachine Confinger解决视角超过背景问题
  * 给背景添加Collider（多边形），设置边框。
  * 将Collider设置为Trigger，解决角色碰撞挤压。
  * 在Cinemachine中找到Extensions选项，选中添加Cinemachine Confinger
  * 将背景拖进Confinger中要求的Collider当中。
  * 勾选Confinger Screen Edges

## 音效

