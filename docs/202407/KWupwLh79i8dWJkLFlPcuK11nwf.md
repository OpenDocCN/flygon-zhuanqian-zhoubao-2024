# 剪映图文AI自动创作影刀RPA机器人，智能创作手到擒来

> 来源：[https://kwut14otear.feishu.cn/docx/RzBMdbsyZosL1vxCDRmclw0onOc](https://kwut14otear.feishu.cn/docx/RzBMdbsyZosL1vxCDRmclw0onOc)

一、机器人介绍

名称：剪映图文AI自动创作影刀RPA机器人

作用：

1.批量读取本地文案txt，进行图文成片

2.选择本地封面

3.自动出片

生成效果：

二、准备

软件：影刀RPA软件

官网：www.yingdao.com

三、流程

1.选择素材文件夹

（1）每个txt是文案

（2）每个txt同名称封面图

2.启动影刀

3.启动剪映图文成片

4.选择本地素材

5.导入封面图，拖动至音频一样长度

6.设置导出名称，导出路径

7.完成输出

四、实现代码

主流程

![](img/22e113477d4648d827dfc3a9cd4fd283.png)

![](img/e0ce714712fe4adecbe22ffba9bd4b8d.png)

![](img/7fd4dd210b7653b9e576a0ff9bec9e88.png)

A.读取文件夹下的txt.flow

![](img/11ba579ae609b18c683aa634e6203d91.png)

![](img/81225862c68cd435203c48832bb87838.png)

B1.开始剪映创作流程.flow

![](img/ca16747cb1a5e59f896c57163cc583a1.png)

![](img/ee9d4dfa8bd4b57564abe0f52d7fc42c.png)

![](img/4d7a08ace2708bbc78d9fccd5e0239c0.png)

![](img/7428455958d3fbb4faa516cc76b4966e.png)

![](img/9dbf368304b0af586fb2329f2b4cc982.png)

![](img/8a04b50f881bcbc4d061f2819f3c7d9f.png)

![](img/28f308617dc1ea68b3ab690bcb92ac0a.png)

![](img/07b723600d2a1d1fe1d4217acb635e25.png)

![](img/0fba0652f86d24cdee378054e5ff5a92.png)

![](img/11edfae4a3d92bfd7615a25ecde8d8e5.png)

![](img/316aae446def1edc72252613b7ec7c4d.png)

![](img/fb5e7e304c76b9b95e428acccceb3631.png)

![](img/dee5e0bd9dc404642bd1b96cd651a548.png)

G1.关闭图文成片窗口.flow

![](img/2d75684695485b5497a76ef5f60adeff.png)

G2.关闭剪映.flow

![](img/488ed9afe04e0ac6fe5d4fe9f461c0e2.png)

G3.启动剪映.flow

![](img/2d1f59579d1ec5dd36a0836edb7f1c85.png)

G4.当前进度.flow

![](img/3896c2675a2f0e9ec3c63f6709746229.png)

![](img/4daa39c7ec4787aedf140055ff5a44f7.png)

![](img/cb5dbd016f8083aad6ef6fde9035724b.png)

![](img/136b545d3e915e76a09b5b7d2538669d.png)

![](img/ff942cf234dc9c762c3b561cd2047c5b.png)

G6.时间轴拉长图片.flow

![](img/0a56d345d461fa74e463a1e1c0e147e7.png)

![](img/364c20ec23c7db065bb36a0e1fa26b02.png)

G7.删除草稿.flow

![](img/df9ae25a7388197620dadf00fac88ad5.png)