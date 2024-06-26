## 合并栏

6.4版后，合并和配音支持直接选择文件操作

## 关于合并参数的说明

宽高：就是合成视频的分辨率，单位是像素，一般横版视频为1920x1080  竖版视频为1080*1920，这里的宽高和剪辑栏的分辨率作用差不多，区别就是这里的宽高是直接拉伸的效果，剪辑栏的分辨率直接直接拉伸，等比缩放和颜色填充

* 图片策略

输入数量：每次合并使用几张图进行合并成一个

单张时长：每张图片显示的时长，只能整数，单位是秒，不能写小数

生成数量：需要生成几个视频

动画效果：等同于视频的转场，勾选动画效果无法自定义单张图片的时长

* 视频策略

输入数量：每次合并使用几个视频进行合并成一个（如果是分镜合并，则表示从每个分镜中取几个视频）

生成数量：生成视频的数量（确保素材足够）

时长限制：比如设置每次5个视频合并，但是合并到3个时候已经达到了总时长，后面两个就不会再进行合并，作用一：提升速度，作用二：控制最大时长

随机截取：也针对添加的素材中的视频进行截取，比如填5，就是从视频中随机截取5秒，然后再进行合并

转场：视频之间添加转场效果，注意，添加转场后，视频的时长会变小，并且原视频声音会消失

视频过渡：每两个合并的视频的中间插入一个视频

过渡前置：这个效果看 [音乐盘点项目](https://qikistudio.gitee.io/#/project/4_yinyuePandian)

## 合并案例讲解

这里只演示一些合并及合并+bgm的案例，关于合并+配音的案例请在配音栏的教程中查看
如果素材的分辨率不一致，一定要填宽和高。为了教程更方便查看，每种案例都单独分开录制。

[合并栏参数讲解](https://qikistudio.top)

* 单图循环
	1. 单图 + 时长  [视频演示](https://www.qikistudio.top)
	2. 单图 + 配音mp3 [视频演示](https://www.qikistudio.top)
	3. 单图 + 时长 + bgm [视频演示](https://www.qikistudio.top)

* 多图合并
	1. 多图 +时长+输入数量 + 生成数量 [视频演示](hhttps://www.qikistudio.top/)
	2. 多图 + 时长+输入数量 + 生成数量 + 转场 [视频演示](https://www.qikistudio.top)
	3. 多图 + 时长+输入数量 + 生成数量 + 转场 + 配音mp3
	4. 多图 + 时长+输入数量 + 生成数量 + 转场 + bgm

* 视频合并
	1. 视频 + 时长限制 + 输入数量 + 生成数量[视频演示] (https://www.qikistudio.top)
	2. 视频 + 输入数量 + 生成数量 + 转场+ bgm[视频演示](https://www.qikistudio.top)
	3. 视频 +输入数量 + 转场 + 配音mp3
	4. 视频 +输入数量 + 生成数量 + 过渡
	5. 视频 +输入数量 + 生成数量 + 随机截取+过渡 [视频演示](https://www.qikistudio.top)
	6. 视频有序合并 [视频演示](https://www.qikistudio.top)
	
* 分镜合并
	1. 分镜合并[视频演示] (https://www.qikistudio.top)
	2. 分镜合并+txt配音+bgm [视频演示](https://www.qikistudio.top)
	3. 分镜合并+srt配音+bgm [视频演示](https://www.qikistudio.top)


## 关于生成数量的说明

> 一句话概括，不配音时，输出数量就是最终生成的数量，配音时，合成数量由文案或音频数量决定。

1. 单图循环
   1. 不填生成数量，有几张图就输出几个视频
   2. 填生成数量，填多少输出多少（数量不能超出图片总数）
   3. 如果勾选了配音，生成数量由文案或MP3决定
2. 图片合并
   1. 不填生成数量，输出一个视频
   2. 填生成数量，填多少输出多少
   3. 如果勾选了配音，生成数量由文案或MP3决定
3. 视频合并
   1. 不填生成数量，输出一个视频
   2. 填生成数量，填多少输出多少
   3. 如果勾选了配音，生成数量由文案或MP3决定
4. 分镜合并
   1. 不填生成数量，输出一个视频
   2. 填生成数量，填多少输出多少
   3. 如果勾选了配音，生成数量由文案或MP3决定

生成数量并不是填多少就一定能输出多少，会受限于素材数量，比如10个素材最多只能合成100个，那么填生成数量为200，也只能输出100个。分镜合并的数量计算：每个目录的视频数量相乘即为最大数量。

## 关于视频最终时长的问题

一共有`3种`方法来控制视频的时长

> 一句话概括，如果视频使用配音，则时长由配音决定，其他情况不会改变视频的时长

[视频演示讲解]()

1. 视频合并不配音，时长由输入数量决定，可以通过总时长进行控制
2. 视频+配音，或者其他模式的配音，时长都由配音的时长决定
3. 视频+MP3合成
   1. 如果想要以MP3的时长为准，则用配音中的MP3模式
   2. 如果想要以视频的时长为准，则用后期中的背景音乐方式添加

[合并输出最大值计算方法](https://www.qikistudio.top)

