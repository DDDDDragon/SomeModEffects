# SomeModEffects
一些常用效果的基类，要用的自取

* CameraModifiers文件夹与EffectPlayer文件是关于屏幕效果的一些代码，如果想要使用，可以在Mod目录下新建一个Effect文件夹，再把这两个下载到Effect文件夹中，然后这两个中所有的文件的命名空间ElementMachine改成你自己的Mod名字。其中包含两个效果：震屏效果和平滑移动屏幕效果。
* 如何使用：震屏效果按帧运行，运行时需要先创建一个PunchCameraModifier对象，然后Add到刚才下载的EffectPlayer.cs中的List<CameraModifiers>中。平滑移动屏幕效果同样需要创建一个RestrictCameraModifier对象，然后同样Add到List中。具体参数下面会讲解。
* 参数：PunchCameraModifier需要的参数有：startPosition(起始位置)，direction(震屏方向)，strength(强度)，vibrationCyclesPerSecond(每秒振动角度)，frames(震屏时间 按帧计算)，distanceFalloff(衰减距离 默认为-1f 不用改)，uniqueIdentity(标识名 可以填你震屏的boss名字或者武器名字 也可以不管它)
  注：震屏方向建议填这个：(Main.rand.NextFloat() * 6.2831855f).ToRotationVector2()
  
  RestrictCameraModifier需要的参数有：fromCenter(起点 填Main.ScreenCenter就行)，toCenter(终点 自己填)，amount(平滑移动分的份数)，Finish(指示屏幕移动到终点后能否结束的Func对象 填写() => 你的变量)，uniqueIdentity(同上)，reset(结束后是否会原路平滑返回)
  注：使用时尽量让人物保持静止！！！
