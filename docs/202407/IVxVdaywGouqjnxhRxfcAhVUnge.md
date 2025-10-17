# Coze实战|0基础新手如何用AI编程做抖音文案提取的程序

> 来源：[https://ngppuxr565.feishu.cn/docx/IVxVdaywGouqjnxhRxfcAhVUnge](https://ngppuxr565.feishu.cn/docx/IVxVdaywGouqjnxhRxfcAhVUnge)

# 1.前言

大家好。我是一泽。生财RPA航海教练，AI编程教练，6年程序员

目前自由职业，从事RPA定制和小红书运营，主要是RPA在小红书上的提效方案

最近Coze爆火，在各大自媒体平台（字节系）都有实例应用，如【抖音评论区自动回复】【飞书表格】等

就是提效的利器啊！

![](img/a9e945826473d6168156383c4bdf48e5.png)

今天就来分享下如何用AI编程结合Coze写出一个属于我们自己的应用程序

看文字觉得累的圈友可以看视频教程：

效果展示：

![](img/560efa4069b434fe79b279f1818a9130.png)

# 2.什么是Coze

字节的官方解释如下：

Coze 是新一代一站式 AI Bot 开发平台。无论你是否有编程基础，都可以在 Coze 平台上快速搭建基于 AI 模型的各类问答 Bot，从解决简单的问答到处理复杂逻辑的对话。并且，你可以将搭建的 Bot 发布到各类社交平台和通讯软件上，与这些平台/软件上的用户互动

我也看不懂

通俗来讲，你可以创造一个助理，这个助理有你想要的大模型功能

Coze这个产品，分别是国内版和海外版

*   国内版

*   网址：https://www.coze.cn

*   官方文档教程：https://www.coze.cn/docs/guides/welcome

*   海外版

*   网址：https://www.coze.com

咱们这次用国内版的就够了

# 3.第一个Coze

接下来我们来实现第一个Coze机器人，能够【扮演一个大厨，提供给我们各个菜的做法】

## 3.1 机器人创造流程

进入Coze网站 https://www.coze.cn/ 并注册

我们按照这个流程就可以创造我们的第一个Bot机器人

【创建 Bot】

【选择工作空间】

【填写Bot 名称】

【点击确认】

![](img/05f1f18fcaa69f9096ebd8613f8ad33e.png)

进来了这个编辑界面，这个编辑界面就是我们小助理的功能。

功能都包含在提示词里，所以你写一次提示词，就能塑造出小助理的功能了

![](img/1fb2646afd7d26f190172d1c50de153c.png)

## 3.2 界面介绍：

我们在功能区写好【小助理】的技能，如果需要高级技能得搭配模块区，成品在成品区查阅

### 3.2.2 功能区

在功能区里可以描述我们想要的功能。

先简单描述一个场景:【扮演一个厨师，能够给我提供各个菜的做法】

点击【优化】，此时会自动生成优化好的【prompt】

![](img/198d666a8710185dc8582b1b5082e226.png)

![](img/dcee94fe3ebc2c58963202f4aa3b8e55.png)

### 3.2.3 模块区

需要高级应用场景时（如图片操作、调用别人写好的模块等）

可以在【功能区】增加描述调用【模块区】的代码

我们第一个Coze机器人不需要调用，直接以大模型对话就够了

### 3.2.4 成品区

在优化好提示词【prompt】后，我们可以在成品区来验证，此时我们输入【牛肉的制作方式】，点击发送。

即可看到我们的第一个Coze机器人做出来了，可以在【成品区】验证下

![](img/7bf6bce460fda2de484972d1c8b60097.png)

### 3.2.5 改名

我们已经训练好这个【第一个Coze机器人】后，肯定是要保存下来，接下来代码里就是调用这个保存好的机器人

在标题这边可以更改我们的机器人名字为【一泽的大厨师】

![](img/5e8cdea2256b1fc363242baa687a43c2.png)

![](img/7b41b64c71ef8de75f74c66ce3746713.png)

![](img/cfa9147a70b5ec72816c119499ad488b.png)

### 3.2.6 发布

改完名后我们要点击右上角【发布】，等待Bot机器人帮我们写好介绍后，点击【确认】

![](img/9a7bcf6d91bc021c6bac20ffd848478e.png)

![](img/5ea51ccb2f59bcf4e147ff00c1a91746.png)

发布出去后我们在哪里能够找到它呢？

| 在这里都能找 | 有什么功能？ |
| 【扣子Bot商店】 | 用户在Bot商店搜索【一泽的大厨师】可以找到我 |
| 【抖音评论区】 | 用户在指定抖音作品下评论想知道xx的做法时， |
| 等等 |  |
| 【Bot as API】 | 我们可以自己写一个exe实现【一泽的大厨师功能】，不用依赖Coze网页，这样我们就可以商用了 |

![](img/062f77a67e05a6a8014f98e26a4948c6.png)

我们的目的是让python能够访问到这个大厨，这个是官方不支持的平台

所以【Bot as API】前面要勾选起来，点发布才有意义

# 4.AI编程实现

## 4.1 Api介绍

众所周知，pycharm是个桌面应用程序。Coze是个网页，那么我们怎么能让【pycharm】和【Coze】勾搭起来呢？

我们需要一个叫【API】的工具，让它帮我们传小纸条

那么这个【API】在哪里？要怎么用？

这个是Cozi官方提供的API文档，介绍了怎么使用这个api

https://www.coze.cn/docs/developer_guides/coze_api_overview

好了，辣眼睛，一堆专业名词

![](img/9188f8ce7387939e94da73b214dc6777.png)

我们点击【发起对话】--- 还是一堆乱七八糟的，

![](img/f609fb95b9f1c7f452286b6669d43432.png)

ok。我们把这部分内容丢给kimi，让它帮我们分析：

1.丢给kimi我复制的文本

2.帮我写一个代码，用来跟coze通信交互

![](img/a44acf104d856824c1b426434f33b036.png)

![](img/7e0effee233c5abc68166f1c5594f381.png)

kimi生成的代码块如下：

```
import requests
import json

# 配置 Coze API 接口信息
api_url = 'https://api.coze.cn/open_api/v2/chat'
headers = {
    'Authorization': 'Bearer YOUR_PERSONAL_ACCESS_TOKEN',  # 替换为你的个人访问令牌
    'Content-Type': 'application/json',
    'Connection': 'keep-alive',
    'Accept': '*/*'
}

# 配置请求体
data = {
    'bot_id': 'YOUR_BOT_ID',  # 替换为你的 Bot ID
    'user': 'user_example',
    'query': '你好，Coze!', # 替换为你的问题
    'stream': False
}

def coze_chat():
    # 发起对话请求
    response = requests.post(api_url, headers=headers, json=data)

    # 检查响应状态码
    if response.status_code == 200:
        # 解析响应内容
        response_data = response.json()
        print("Response from Coze:")
        print(json.dumps(response_data, indent=2, ensure_ascii=False))
    else:
        print("Failed to connect to Coze API:", response.status_code)

# 调用函数
coze_chat()
```

简单看了下，kimi需要我们在代码里提供2个东西

1.个人访问令牌

2.bot id

![](img/a8932a626cc7d2026c18fb22d13ed1f1.png)

那么，这2个东西是什么呢，又是哪里来的呢？

男大和女大，通过别人介绍的话，得知道对方的学校、学号吧？不然靠漂流瓶联系？

ok。我们再回过头看这个【API】说明书，API说明书里说了

【令牌】就是【谁开发的】，

【Bot ID】就是【第一个机器人还是第二个机器人】

![](img/9fe94d7a0243659ea2810ed3b7153f4c.png)

【令牌】我们上述讲了，在创建空间的时候要以一个合法的【身份】行走江湖

【Bot ID】就是我们机器人页面网址的后缀，在这个项目中就是【7385099152600121363】

![](img/a0c4c762251a43aaddabd42decefe7f3.png)

同时我们也注意到，我们要跟Coze对话，就要有输入的对话内容。

所以我们要把【query】字段改为要问的菜名

![](img/aac956ede393b3919d08cadc57fd49ba.png)

对话结果：

![](img/e7c0d6399f1b9bfcd9a8495ec68a3003.png)

## 4.2 目标

用AI编程+pycharm来实现一个脱离Coze平台的exe

![](img/f1942e8e8d3ff452e90c91f0d516f517.png)

## 4.3 界面介绍

咱们先不管这个Coze的事情，要做成可执行程序exe，让别人丝滑用起来，需要一个UI界面。

这个目标有以下4个元素：

1.用的是pyside6的UI框架 （不用这个框架也行，只要能生成UI界面的都行）

2.需要一个log日志输出框

3.需要一个文本输入框，并给我们一个输入提示词：请输入你想要吃的菜

4.有一个确定按钮

![](img/d4b2c4452717ca2c7aebdce1d3ee96db.png)

## 4.4 AI编程生成UI框架

我们先实现这个的AI 打开大模型对话【gpt】【kimi】等等均可

输入提示词：

【kimi】的示例提示词

帮我写一个pyside6的代码，要有一个log日志输出框，一个文本输入框（有提示词：请输入你想要的菜的做法），一个确定按钮

没错，就是这么简单粗暴

![](img/57fcc14ec01e1b279fac735c7f62ebed.png)

UI框架的代码：

```
import sys
from PySide6.QtWidgets import QApplication, QWidget, QVBoxLayout, QHBoxLayout, \
    QPushButton, QTextEdit, QLineEdit, QLabel

class MainWindow(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        # 设置窗口标题和初始大小
        self.setWindowTitle("PySide6 应用示例")
        self.setGeometry(100, 100, 400, 300)

        # 创建布局
        layout = QVBoxLayout()

        # 创建日志输出框
        self.log_edit = QTextEdit()
        self.log_edit.setReadOnly(True)
        layout.addWidget(self.log_edit)

        # 创建输入框和提示词
        self.input_edit = QLineEdit()
        self.input_edit.setPlaceholderText("请输入你想要的菜的做法")
        layout.addWidget(self.input_edit)

        # 创建确定按钮
        self.confirm_button = QPushButton("确定")
        self.confirm_button.clicked.connect(self.on_confirm_clicked)
        layout.addWidget(self.confirm_button)

        # 将布局添加到窗口
        self.setLayout(layout)

    def on_confirm_clicked(self):
        # 当点击确定按钮时，将输入框的内容添加到日志框
        text = self.input_edit.text()
        self.log_edit.append(text)

if __name__ == '__main__':
    app = QApplication(sys.argv)
    mainWin = MainWindow()
    mainWin.show()
    sys.exit(app.exec())
```

大家放到pycharm里，缺少的库自己记得pip install 安装一下

UI框架的效果：

![](img/5a9185c5d4a75dcb7fde50d69e9b0e24.png)

## 4.5 pycharm跟Coze通信

替换掉【令牌】和【Bot ID】后，把这2个代码文件丢给AI，让它帮我们优化：

帮我基于这2个python代码优化。实现如下功能：

按下确定键后，把我输入框的内容发送给coze，并分析其返回的结果

![](img/de31a76816121565546df3d1c5af3df5.png)

把AI生成的代码复制到pycharm中，运行，发现原先设置的UI界面被改了。但是不影响。

## 4.6 完整代码：

```
import sys
import requests
import json
from PySide6.QtWidgets import QApplication, QWidget, QVBoxLayout, QHBoxLayout, \
    QPushButton, QTextEdit, QLineEdit, QLabel

class MainWindow(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        # 设置窗口标题和初始大小
        self.setWindowTitle("Coze Chat Interface")
        self.setGeometry(100, 100, 400, 300)

        # 创建日志输出框
        self.log_edit = QTextEdit()
        self.log_edit.setReadOnly(True)
        self.log_edit.setPlaceholderText("Coze 的回复将显示在这里")

        # 创建输入框和提示词
        self.input_edit = QLineEdit()
        self.input_edit.setPlaceholderText("请输入你的问题")

        # 创建确定按钮
        self.confirm_button = QPushButton("确定")
        self.confirm_button.clicked.connect(self.on_confirm_clicked)

        # 创建布局并添加控件
        layout = QVBoxLayout()
        layout.addWidget(self.input_edit)
        layout.addWidget(self.confirm_button)
        layout.addWidget(self.log_edit)

        self.setLayout(layout)

    def on_confirm_clicked(self):
        # 获取用户输入
        user_input = self.input_edit.text()
        if not user_input:
            self.log_edit.append("请输入问题")
            return

        # 发送请求到 Coze API
        self.send_to_coze(user_input)

    def send_to_coze(self, query):
        api_url = 'https://api.coze.cn/open_api/v2/chat'
        headers = {
            'Authorization': 'Bearer 456',  # 替换为你的个人访问令牌
            'Content-Type': 'application/json',
            'Connection': 'keep-alive',
            'Accept': '*/*'
        }
        data = {

            'bot_id': '123',  # 替换为你的 Bot ID
            'user': 'user_example',
            'query': query,
            'stream': False  # 根据 Coze API 的要求设置
        }

        try:
            response = requests.post(api_url, headers=headers, json=data)
            response.raise_for_status()  # 如果响应状态不是 200，将抛出异常
            response_data = response.json()

            # 显示 Coze 的回复
            self.display_response(response_data)
        except requests.exceptions.RequestException as e:
            self.log_edit.append(f"请求 Coze API 时发生错误: {e}")

    def display_response(self, response_data):
        # 这里我们假设 Coze API 返回的是非流式响应
        if 'messages' in response_data:
            for message in response_data['messages']:
                if message['role'] == 'assistant' and message['type'] == 'answer':
                    self.log_edit.append(message['content'])

if __name__ == '__main__':
    app = QApplication(sys.argv)
    mainWin = MainWindow()
    mainWin.show()
    sys.exit(app.exec())
```

执行下，输入【菜名】点击【确定】

【注意事项】：由于Coze交互需要一点时间，所以点击确定后会导致该程序无响应5-10秒，这个没事，等待一小会就行

![](img/85b2aa0cab475a18deaa52a4a9ef96be.png)

## 4.7 生成可执行文件exe

想要脱离pycharm环境，在另一台电脑独立运行怎么办？

1.在pycharm的下方或者左下方找到你的【Terminal】

2.输入命令：pyinstaller -F -w 大厨.py

3.在执行完毕之后，该文件路径下的dist文件夹下有个exe，就是打包好的可执行程序

【注】pyinstaller 打包命令

-F 单个文件打包

-w 不输出调试窗口信息

大厨.py python的代码文件

如果没有安装pyinstaller工具，可以参考以下命令安装：

pip install pyinstaller -i https://pypi.tuna.tsinghua.edu.cn/simple

![](img/35aabfe1f18b7c7d4c4ab22e86b2e37f.png)

![](img/7fa244be24ddff7edce37ca3cfc681a7.png)

![](img/4d296f8d43e3f0aa1777ec3daaadc105.png)

![](img/c68473e875e689a036b9cc21fd5cc248.png)

# 5.AI编程实现抖音文案采集

## 5.1 抖音文案需求描述

接下来来到我们最熟悉的场景：【抖音文案采集&仿写】

我们基于【大厨】这个机器人要怎么做优化实现抖音文案采集呢？

老规矩，我们来看下UI：

![](img/58a5cda9cd8b9870ee75528712d31b66.png)

这点UI框架跟【大厨】机器人其实是差不多的

那么核心的是什么？就是Coze上的功能修改

## 5.2 文案修改

我们在功能区的描述要改下

将用户提供的抖音链接传递至工作流，并输出工作流输出的文档

当然了还得经过【优化】

![](img/a10f8396163d025474178b47bf8abf5f.png)

## 5.3 插件修改

除了功能区的修改，现在还缺【干活的大冤种】-把视频提取出文案，所以我们需要一个【工作流】来干活

### 5.3.1【方法一】巧用他人作品

我们在【工作流市场】中，找找有没有人已经把抖音视频转文案的插件做出来了

![](img/b2edfca531f30d27aa145fad77ff1799.png)

![](img/987781003313fd57d6456cd7705bb8fb.png)

![](img/40fd3e6a8c1e2101fba62b7293ef1887.png)

在搜索工作流的时候我们找到了好多个。选择一个满足你需求的功能就行，然后点击【复制并添加】

如果找不到可以参考这个：【douyin_video_to_text_summary】

![](img/c3628d0f2f838485216e6b8eb7ffb4db.png)

### 5.3.2 【方法二】自己写

![](img/9acd32a0a82b0f2835ff84a2af9fdb66.png)

![](img/d94280c7a471f93392339dda4c5ba69c.png)

进入界面后有2个模块：【开始】+【结束】

中间就是我们要操作的内容。

想实现抖音文案提取并改写，我们需要以下路径

插件流程图如下：

【开始】- 设置输入：抖音链接

![](img/d0d743f33ae7080962ca9e2e7c39a474.png)

搜索插件【LinkReaderPlugin】

![](img/5f1998c726c35af98a74283e4aeb4193.png)

【提取抖音视频文本】 - 依赖插件：【LinkReaderPlugin】，令url链接为【开始的输入】

![](img/f050af23a0ef684991a65437250c3501.png)

【输出】

设置输出内容为提取模块输出的【content】

![](img/67ac3f3468fbed0e9361f63ebe61fff4.png)

## 5.4 pycharm代码改动

代码的逻辑部分不用改动 ，

回到我们原来的UI界面。此时我们要输入的是抖音的链接，让它帮我们生成文案

![](img/bcc9cf36f19e8e81b9b012e9c6d8dac5.png)

等待生成结束就是这样：

![](img/45a7f45e1e8674f8741785b444603583.png)

## 5.5 生成可执行文件

参考4.7

## 5.6 可优化的点

### 5.6.1 卡顿

从程序的角度出发，点击【确定】后，程序会阻塞住，出现【无响应】现象-在等待coze返回对话结果

那么怎么解决呢？

------ 招个打黑工的 这样一个UI界面在等待你的点击，打黑工的在后台吭哧吭哧干活

专业术语：开个线程

### 5.6.2 提示词

程序员不是工具人，在对话框提示的时候，加一些人性化提示词&过程提示词：

![](img/c46f8ad79bf826f16697b002ccb4b0e2.png)

### 5.6.3 优化后的完整代码

```
import sys
from PySide6.QtWidgets import QApplication, QWidget, QVBoxLayout, QTextEdit, QLineEdit, QPushButton
import requests
import re
import json
import threading

class LogApp(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()
        self.headers=''
        self.payload=''
        self.captureStat = 0

    def initParam(self,link):
        personal_access_token = 'YOUR_PERSONAL_ACCESS_TOKEN'
        # 替换为你的Bot ID
        bot_id = 'YOUR_BOT_ID'
        # 构造请求头
        headers = {
            'Authorization': f'Bearer {personal_access_token}',
            'Content-Type': 'application/json',
            'Accept': '*/*',
            # 'Host': 'api.coze.cn',
            'Connection': 'keep-alive'
        }

        # 构造请求体
        payload = {
            "bot_id": bot_id,
            "user": "29032201862555",
            "query": link,
            "stream": False,
        }
        self.payload = payload
        self.headers = headers

    def initUI(self):
        # 创建布局
        layout = QVBoxLayout()

        # 创建文本编辑框，用于显示日志
        self.logTextEdit = QTextEdit()
        self.logTextEdit.setReadOnly(True)  # 设置为只读
        layout.addWidget(self.logTextEdit)

        # 创建文本输入框
        self.inputLineEdit = QLineEdit()
        self.inputLineEdit.setPlaceholderText('请输入抖音链接')
        layout.addWidget(self.inputLineEdit)

        # 创建确定按钮
        self.confirmButton = QPushButton('确定')
        self.confirmButton.clicked.connect(self.on_confirm_click)
        layout.addWidget(self.confirmButton)

        # 设置布局
        self.setLayout(layout)
        self.setWindowTitle('一泽的抖音文案提取大师')  # 设置窗口标题
        self.setGeometry(300, 300, 400, 300)  # 设置窗口位置和大小

    def log(self, message):
        """将消息添加到日志文本框"""
        self.logTextEdit.append(message)

    def is_douyin_link(self,url):
        # 定义抖音链接的正则表达式
        pattern = r'https://www\.douyin\.com/[a-zA-Z0-9]+'
        # 使用正则表达式匹配链接
        if re.match(pattern, url):
            return True
        else:
            return False

    def on_confirm_click(self):
        """确定按钮点击事件处理"""
        if self.captureStat == 0:
            self.captureStat = 1
            self.log(f'一泽的coze采集大师...')
            self.log(f'让我瞅瞅怎么个事...')
            process_thread = threading.Thread(target=self.capture)
            # 启动线程
            process_thread.start()
        else:
            self.log(f'别催了别催了，在看了')

    def capture(self):
        link = self.inputLineEdit.text()
        stat = self.is_douyin_link(link)

        if stat == False:
            self.log(f'手欠，链接输入错了')
            self.captureStat = 0
            return 0

        self.initParam(link)
        # 发送POST请求
        response = requests.post(
            'https://api.coze.cn/open_api/v2/chat',
            headers=self.headers,
            json=self.payload  # 注意这里使用的是json参数而不是data
        )

        # 打印响应内容
        if response.ok:
            print('请求成功，返回数据：')
            # print(response.json())
            self.log(f'\n等久了吧，我来了\n')
            response_data = response.json()
            print(response_data)
            if 'messages' in response_data:
                for message in response_data['messages']:
                    if message['role'] == 'assistant' and message['type'] == 'answer':
                        self.log(message['content'])
        else:
            print('请求失败，状态码：', response.status_code)
            print('错误信息：', response.text)
        self.captureStat = 0
        user_input = self.inputLineEdit.text()
        # self.log(f'用户输入: {user_input}')

def main():
    app = QApplication(sys.argv)
    ex = LogApp()
    ex.show()
    sys.exit(app.exec())

if __name__ == '__main__':
    main()
```

### 5.6.4 流式输出代码（边生成边输出）

![](img/d15c3f2a215f0e3b667c504db78bdf59.png)

```
import sys
import requests
import json
from PySide6.QtWidgets import QApplication, QWidget, QVBoxLayout, QPushButton, QTextEdit, QLineEdit
from PySide6.QtCore import QThread, Signal
import threading

class CozeAPIThread(QThread):
    response_signal = Signal(str)

    def __init__(self, api_url, headers, data):
        super().__init__()
        self.api_url = api_url
        self.headers = headers
        self.data = data
        self.active = True

    def run(self):
        try:
            with requests.post(self.api_url, headers=self.headers, json=self.data, stream=True) as response:
                response.raise_for_status()
                for line in response.iter_lines():
                    if line:
                        self.response_signal.emit(line.decode('utf-8'))
        finally:
            self.active = False

    def stop(self):
        self.active = False

class MainWindow(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()
        self.querystat = 0

    def initUI(self):
        self.setWindowTitle("Coze Chat Interface")
        self.setGeometry(100, 100, 400, 300)

        self.log_edit = QTextEdit()
        self.log_edit.setReadOnly(True)
        self.log_edit.setPlaceholderText("Coze 的回复将显示在这里")

        self.input_edit = QLineEdit()
        self.input_edit.setPlaceholderText("请输入你的问题")

        self.confirm_button = QPushButton("确定")
        self.confirm_button.clicked.connect(self.on_confirm_clicked)

        layout = QVBoxLayout()
        layout.addWidget(self.log_edit)
        layout.addWidget(self.input_edit)
        layout.addWidget(self.confirm_button)

        self.setLayout(layout)
        self.api_thread = None

    def on_confirm_clicked(self):
        if self.querystat == 0:
            self.querystat = 1
            self.log_edit.append("开始处理")
            process_thread = threading.Thread(target=self.capture)
            process_thread.start()
        else:
            self.log_edit.append("在处理了")

    def capture(self):

        query = self.input_edit.text()
        if query:
            self.start_coze_api_thread(query)

    def start_coze_api_thread(self, query):
        api_url = 'https://api.coze.cn/open_api/v2/chat'
        headers = {
            'Authorization': 'Bearer YOUR_PERSONAL_ACCESS_TOKEN',  # 替换为你的个人访问令牌
            'Content-Type': 'application/json',
            'Connection': 'keep-alive',
            'Accept': '*/*'
        }
        data = {
            'bot_id': 'YOUR_BOT_ID',  # 替换为你的 Bot ID
            'user': 'user_example',
            'query': query,
            'stream': True
        }

        if self.api_thread is not None and self.api_thread.isRunning():
            self.api_thread.stop()
            self.api_thread.wait()

        self.api_thread = CozeAPIThread(api_url, headers, data)
        self.api_thread.response_signal.connect(self.display_response)
        self.api_thread.start()

    def display_response(self, line):
        # 检查是否包含 "data:" 前缀，并去除它以及随后的空格
        if line.startswith("data:"):
            # 去除 "data:" 和可能的空格，然后解析外部的 JSON 对象
            line = line[5:].strip()
            try:
                # 解析 JSON 数据
                data = json.loads(line)
                event = data.get('event')
                # 检查是否是消息事件
                if event == 'message':
                    # 获取消息内容
                    message = data.get('message', {})
                    content = message.get('content', '')
                    content = content.replace('\\n', '\n').replace('\\', '')
                    # 打印 'content' 字段的内容
                    print(content)
                    self.log_edit.append(content)
                elif event == 'done':
                    self.querystat = 0
                    self.log_edit.append("本次结束")
                    return
            except json.JSONDecodeError as e:
                # 如果解析 JSON 失败，记录错误信息
                self.log_edit.append(f"解析 JSON 错误: {e} - 原始行: {line}")
        else:
            # 如果行格式未知，打印提示
            self.log_edit.append(f"未知格式的行: {line}")

if __name__ == '__main__':
    app = QApplication(sys.argv)
    mainWin = MainWindow()
    mainWin.show()
    sys.exit(app.exec())
```

# 6.常见问题

圈友【大麦】整理的常见问题

1、先得安装库：pip install PySide6，比较慢，花了半个多小时，这时候可以换成清华源下载

pip install PySide6 -i https://pypi.tuna.tsinghua.edu.cn/simple

2、在发布之前要先创建一个api，否则发布时没有【Bot as api】的选项

3、生成个人令牌时，要记得保存下来，它只显示一次，第一次生成时没注意，只好删除重新生成一个新的。

4、用案例里的代码时，替换自己的个人令牌和Bot_id，要注意在令牌前加上Bearer，它是一个标识，表示“Bearer Token”，这样就能顺利运行了。

5、运行时，输入关键词，点确定后会卡几秒钟，等一会结果就会显示了。

这个是因为只有一个打工仔在干活，它在等待coze的返回就没法去处理你的UI点击事件，可以开一个线程（再找一个打工仔）实时等待你的UI。5.6.3的完整链接把这个加进去了

# 7.结束语

这次的分享就到这里。Coze还有更多可能性等待大家去挖掘,大家有什么建议也可以提出来

我是一泽，欢迎链接V: z8401483498