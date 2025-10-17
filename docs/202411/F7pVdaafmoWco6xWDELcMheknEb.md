# AI视频用到的工具

> 来源：[https://gida8fb9mrg.feishu.cn/docx/F7pVdaafmoWco6xWDELcMheknEb](https://gida8fb9mrg.feishu.cn/docx/F7pVdaafmoWco6xWDELcMheknEb)

# 提示词

## Kimi

kimi是国产的一款AI软件，访问地址：kimi官网

优点：国产的AI软件，不需要魔法，只需要一个手机号码。

缺点：需要有一定的提问技巧。

```
##角色:
你是一个精通文生视频提示词的专家,拥有丰富的艺术、视觉影像、文学与心理学常识,能准确使用影视行业的专有名词。现在，你需要把用户输入的文本标题卡(Text Title Cards)和其他需求(other requirements),扩展为高质量的、细节丰富的一段提示词,用于生成高质量的视频。

##目标:
1.根据用户输入的文本标题卡和其他需求,编写一段文生视频用的英文提示词,使用这样的结构:[camera movement]:[establishing scene].[additional details]。
2.将用户输入的文本标题卡加入到[establishing scene]的描述中,并将用户输入的其他需求融入到[camera movement]或[additional details]的描述中，发挥你的想象力。
3.[camera movement]和[additional details]两部分请参考下面给的扩展思路来扩展

##注意:
1.扩展后的提示词必须包含用户输入的文本标题卡,且满足用户输入的其他需求。
2.扩展后的提示词需合乎逻辑，不能自相矛盾，比如camera movement不能同时出现Low angle和High angle。
3.扩展的提示词由词组或短句构成，切勿冗长，不要超过100个单词。

##扩展思路:
***[camera movement]***
1.从Camera Styles来扩展,参考关键词为:Low angle,High angle,Overhead,FPV,Hand held,wide angle,Close up,Macro cinematography,Over the shoulder,Tracking,Establishing wide,50mm lens 50 mm, Snorricam, Realistic documentary, Camcorder.

***[additional details]***
1.从Lighting Styles来扩展,参考关键词为:Diffused lighting,Silhouette,Lens flare,Back lit, side lit, gel lighting, Venetian lighting.
2.从Movement Speeds来扩展，参考关键词为:Dynamic motion, slow motion,Hyperspeed,Timelapse.
3.从Movement Types来扩展,参考关键词为:Grows,Emerges,Explodes,Ascends,Undulates,Warps,Transforms, Ripples, shatters, Unfolds, vortex.
4.从Style and Aesthetic来扩展,参考关键词为: Moody, Cinematic, Iridescent, Home video VHS,Glitchcore.
5.从Text styles来扩展,参考关键词为:Bold,Graffiti,Neon,Varsity,Embroidery.

##示例:
***用户输入的文本标题卡为:Runway,用户输入的其他需求为:Dynamic motion.
扩展后的提示词为:A title screen with dynamic movement: The scene starts at a colorful paint-covered wall. Suddenly, black paint pours on the wall to form the word"Runway". The dripping paint is detailed and textured, centered, superb cinematic lighting.

##输出格式:
根据您输入的文本标题卡和其他需求，
1.为您扩展后的提示词为:xxx
2.翻译成中文为:xxx

##初始化:
请您输入文本标题卡:{};请您输入其他需求:{}
```

当我们没有思路的时候，可以让kimi帮我们给一些思路，不一定要用提示词。

## gpts

gpts是chatgpt的插件商店，和kimi不同，商店有很多别人调试好的插件：chatgpt官网

这里推荐三个插件：

1.  Video shooting script

1.  Midjourney v6.1 Prompt Generator

1.  Luma/Gen-3/Kling promt enchancer

优点：有别人写好的智能体，不需要很高的技巧也能得到较好的答案

缺点：需要魔法，需要账号

### Video shooting script：是用来生成分镜头的

![](img/6f2412bea03d82299906c9c7965492c6.png)

### Midjourney v6.1 Prompt Generator：用来为每个分镜头写具体的提示词

![](img/c552f90bf6cefdfe0c074634465d9e04.png)

### Luma/Gen-3/Kling promt enchancer：上传两张图生成首尾帧提示词

![](img/64d9f15d1fc11f38af58e51dc5f8eca6.png)

# 文生图

## 即梦：即梦官网

即梦AI是字节跳动旗下剪映推出的一站式AI创作平台。

优点：

1.  每日都有免费额度，每张图片需要的额度都很少，一天可以生成很多图。

1.  中文友好，可选择生图模型，自定义图片大小，支持垫图。

图片生成

![](img/196322d9d77aeeccf03479962217466a.png)

参考图

![](img/255f238d30a033ee37a424399d5e1c70.png)

智能画布：抠图、拓图、局部重绘

![](img/983d6bff00e6dc0d377b1e0f978c7dd9.png)

## 秒画：官网地址

秒画是商汤科技推出的一款基于自研Artist作画大模型的AI绘画创作平台。

官方飞书文档：

优点：

1.  有免费额度，支持自定义的参数很多

1.  有灵感广场，可以直接制作同款

1.  有局部重绘，图片拓展功能

![](img/a0cd34c9393e76524a44ef7aae106ebb.png)

灵感广场，可以很方便的生成同款图片

![](img/80a30174e1893eda96c045fa70c9e70b.png)

## 悠船：悠船官网

悠船是由Midjourney官方推出的国内中文版AI图像生成工具，它允许用户通过文字描述来生成图像

优点：中文友好，功能齐全，图生图、风格参照、角色参照，人物一致性。

![](img/10f4769f04615fa029927b2ff32bc11c.png)

![](img/63608afe23d4406f1c2c1a51ded931fb.png)

## 吐司：吐司官网

吐司是国产的一个AI绘画模型分享社区和在线生图平台。

优点：

1.  中文友好，每日都有免费额度，每张图片需要的额度都很少，一天可以生成很多图。

1.  小白友好，有很多别人做好的工具和工作流，只需要点进去就可以运行了。

1.  大佬友好，支持模型训练。

1.  能反解析出图片的提示词。

![](img/62c3c2a0fd548d07239bddb6c49a763f.png)

![](img/8c8ec1ccb895483826a48abd020d0599.png)

![](img/22214d1256b35b6c2de08ca334e27c91.png)

![](img/5068d3c3e89d7659ad5883cdd83b669f.png)

## 可灵：官方地址

优点：中文友好，操作简单，支持文生图，图生图，每天有一定量的额度, 图片可以生成很多张

缺点：免费的只能生成几条视频，而且最近视频生成有时候会报错，提示免费通道有限。

![](img/d3d4c7878e12fb4cd231df4c87fe83f1.png)

## Runninghub：官网地址

Runninghub是无需本地安装的在线创作环境，comfy UI托管网站，上面托管很多别人做好的图片流

openart有很多的工作流，但不可以执行。

哩布哩布也可以用，不过有次数限制。

优点：中文友好，免费、无限次使用，可以直接运行。

首页会有很多工作流

![](img/2b17868b410b1aa40c41eb047812b300.png)

点进去之后，看起来复杂，不过只需要替换图片，然后点击右上角运行即可

![](img/3487ca3ec7cbeb6b4eff38cc61164e81.png)

## KRER：官网地址

krer是国外的产品，所以是英文友好，界面是英文的，输入的提示词也必须是英文的。

优点：图片增强、 图片区域修改，图片融合、 图片丝滑转换成视频

![](img/2ac5370b55ba7976ce4336a0e64a07e8.png)

![](img/0d50e72d951807f6bbebbe3e963b7e8a.png)

## Midjourney官网：

优点：绘图界扛把子，生图质量好

缺点：需要魔法，价格较贵

## Stable Diffusion & Comfy ui：

优点：免费、可以免费部署，不用排队

缺点：需要自己部署，过程繁杂，并且图片生成速度依赖本地硬件

## 平面转3D：官网地址

操作简单，上传图片然后生成即可

![](img/f32b5ca98bb99397ecd2151d90a8454a.png)

# 音乐

## Mubert：https://mubert.com/

优点：

1.  根据提示词生成音乐

1.  根据图片生成音乐

1.  根据歌曲链接仿生成新的歌曲

缺点：歌曲中混杂有mubert歌词，估计开了会员才能去除

![](img/c10234baf1854f9a06cefc51ba9242aa.png)

## Soundraw：https://soundraw.io/

免费制作，导出收费

特点是能自己改变节拍

![](img/ef4188533772736cc41f66d546dbfd64.png)

## 网易天音：https://tianyin.music.163.com/#/

1.  支持多种方式制作歌曲

1.  网易ai作词支持实时修改歌词，修改歌手，修改风格

1.  同时制作的歌曲还能上传到网易上产生收益

![](img/0e796ef558cec866d61265a8ebe2e90f.png)

![](img/5a841d3bf9ff8630d3f24006eb349fbc.png)

![](img/75b42d1f96f632e66c8d3e9fc4f5c670.png)

## Suno：https://suno.com/

每天有50积分，可以制作十首2-3分钟的歌曲，歌词可以用kimi写

![](img/23c0e37d4a9709e154bfe927c069d01b.png)

![](img/2e2297f4033836f9aa13936bb5d69bc1.png)

## Udio: https://www.udio.com/home

每天有10积分，可以制作5首歌

![](img/51223614c0f10331dad082d082352952.png)

## 海绵音乐: https://www.haimian.com/featured

没有看到充值入口，并且会生成一张封面图，导出的时候封面图也会一起导出

![](img/b04271bce256e866537044ee28aa933e.png)

## BGM猫: https://bgmcat.com/home

根据标签生成轻音乐，操作简单

![](img/045faa866a43ab0575faf44072246656.png)

# 图生视频

Prompt精确公式= 要创建的主要表现物 + 场景空间 + 运动 /变化 + 镜头运动 + 美感氛围

例如:

一对情侣坐在公园的长椅上交流，镜头维持固定拍摄情侣，画面色调偏暖，氛围温馨

一只小羊在一片草地里低头吃草，镜头缓缓推进小羊，画面色调自然写实

一个身穿西装的男人面色凝重地在面馆里吃面, 镜头逐渐拉远展示面馆的吵闹环境，画面色调自然

## 海螺AI：官网地址

优点：界面简单，支持导出，目前是免费的，但是需要排队

缺点：有明显的水印

![](img/d90f1aedf88415a2cd689d7ea8d837b9.png)

## 可灵：官网地址

优点：每天有一定量的免费额度，支持文生视频、图生视频、并且有很多自定义参数

缺点：免费生成的视频数量很少，并且免费额度容易遇到问题

![](img/78533ca5542d1f53bb1efeeba5542b6a.png)

## 即梦：即梦官网

优点：功能齐全：支持文生视频，图生视频，对口型，首尾帧

![](img/7ca94de53cc1f9804cc37f3444f8db14.png)

## Luma：官网地址

优点：每个月30次视频生成，操作简单，支持无水印导出

缺点：在晚上适用人数多的时候，免费的无法使用

![](img/288dfb67d714dcf10b6ca9ece17d49c9.png)

## Runway：官网地址

特点：支持视频转绘、艺术字视频，最后一帧特效添加

![](img/bd3f472adc6fd6124c82879656999cae.png)

![](img/e3e359a9d7da8b7da7bbb323b5ff49f2.png)

![](img/e820af6fbe8bf2f0d2266b785bd9ac46.png)

## Pika: 官网地址

有内置的一些效果，比如爆炸，融化

![](img/8b78b7556ca1a906b3fa9a023f422c51.png)

## Domoai：官方地址

视频转绘：就是将真实视频的动作转换成动漫风格的

不过有点贵

![](img/b71a00cac73bc1571af89d7e7adddd6e.png)

## deforum：官网地址

搭配gpts：deforum animator

能很简单的制作出炫酷，卡点的AI视频，不过比较贵，并且没有免费额度

![](img/e59442d0f34957a458deea20e11f58be.png)

# 剪映

不管是那个AI平台，即便是付费的，也只能生成几秒的视频，因此如果发布较长的视频，就需要用到传统的工具进行合成，用的比较多的是剪映。

除了视频拼接，用得比较多的还有这几个功能。

音乐 + 音效

![](img/4c1435e25dad04bb02c2d1006a584b2c.png)

文字 + 朗诵

![](img/06e8d4592202bbcd07b09475a6e484b8.png)

变速

![](img/920ad9f0c205b55c3b63ecd9df0dacaa.png)