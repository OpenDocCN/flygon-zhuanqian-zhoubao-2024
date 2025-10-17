# Coze/扣子快速制作MVP产品：自动总结公众号内容，定时推送到微信（附8000字完整实操教程）

> 来源：[https://v0bko2tq65.feishu.cn/docx/FhA7d1HqYo2SqPxgz9KcLZ7un6c](https://v0bko2tq65.feishu.cn/docx/FhA7d1HqYo2SqPxgz9KcLZ7un6c)

大家好，我是拔刀刘，这次Coze提效大航海的教练。

目前带领2300多名船员，还在海上驰骋。我在这里也用自己的一个案例，为咱们不会技术的众多小伙伴打打气，在AI时代，借助工具，即使不会编程，也能快速制作出一款产品。

![](img/0bc51b70a17b9dd49a2d3ea9036ca608.png)

## 一、需求分析

其实这个需求主要来源于自己，平时看公众号内容比较多，但是随着订阅数量的增多，阅读公众号变成了一股无形的压力，总感觉不点进去看看，就会错过点什么。如果能有一款产品，可以自动总结订阅公众号的内容，看完总结再决定是否打开文章，应该可以节省不少的时间。

当然，如果能再聚合其他信息来源，比如：播客、微博、Twitter、星球、微信群的内容，定时汇总再推送到我的微信上，那就更爽了！

之前都是使用RSS来统一管理这些信息来源，但是缺少了一个总结的功能，总觉得差点意思。所以考虑用Coze做一个Bot，先从公众号内容做起，把核心流程跑通。

![](img/d865331bae5f140f4461e1d4e14c3a79.png)

## 二、最终效果展示

因为文章比较长，为了大家有动力看完文章，先展示一下最终的效果，有兴趣了解如何制作这样一个Bot的，下边章节8000字+60图是喂饭级的实操教程。懒得弄的，我打算开源整个工作流和提示词源码，可以拉到文章最后查看获取方式。

请忽略我的老年人字体和暗黑模式[捂脸][捂脸][捂脸]

## 三、工作流拆解

工作流主要提供的价值是：把重复的工作固化下来，提升工作效率。比如你原来想提取一条抖音文案，需要先复制抖音链接，打开微信搜索小程序，粘贴链接、等待转文字，复制文字，粘贴到文档中，这中间可能还得让你看条广告。每提取一条文案，都得重复这个过程。重复、流程化，这种工作就特别适合使用工作流解决。

那从你复制抖音链接开始，到粘贴文案到文档中，这个过程，其实就是工作流的主要路径。跟“把大象装冰箱，总共分几步”没啥本质区别。

![](img/dfdf7e36381fa26b935ca4435c9ddc49.png)

### 1、路径拆解

使用相同的方法，我们发现“自动总结公众号内容，定时推送到微信”，实际核心环节就三个：

1、抓取公众号的内容

2、对内容进行总结

3、汇总后定时推送到微信

### 2、元素拆解

我们再来看看这个流程中每一步都涉及到哪些核心要素：

1、抓取公众号内容：

首先先在平台搜搜有没有现成的插件，Coze平台确实有一些读取公众号内容的插件，但是都已经荒废了，用不了了。

![](img/b865a25621c114ba603a992518fc069f.png)

所以现在要么写爬虫自己抓（我不会啊……），要么就看看有没有现成的服务，可以通过API的方式直接调用。这时候想起来原来折腾RSS订阅的时候，有个平台叫「瓦斯阅读」，可以稳定的抓取公众号的内容，用这个先试试，成功获取生财有术公众号的内容！

![](img/ac58c132a46722e10fdd772cbd5863fd.png)

但是马上新的问题就出现了，平台上公众号也太不全了吧，我搜了10个，有7个都没有（晕倒），比如搜索Coze的官方账号就查无此人。

![](img/41c77fb57cd38bd4eaea66f6dfbff457.png)

看来还得找找其他的方案，功夫不负有心人，在GitHub上有个项目叫做WeWe RSS。这个工具可以通过微信读书的方式，订阅公众号，感觉可行！看着也挺优雅！

![](img/c4f9119ecb6959c1a40cc41824549309.png)

2、公众号内容总结：

这个主要就是依靠大模型的能力了，总结任务应该算是大模型最擅长的任务之一了吧，字节的豆包大模型应该就可以胜任。这步主要涉及一个批量化操作：批量对抓取到的公众号内容进行总结，可以使用「批处理」功能搞定，后边会有详细介绍。

![](img/9e1191b46ed0bb4d1093eef678610392.png)

3、定时推送到微信：

这里头有两个点：一个是定时，这个Coze平台的触发器可以实现；另一个是推送到微信，Coze平台没有这类的插件，看来还得找第三方API的方案解决。

![](img/8ac1d473ffc299a662f59fffecc3ef3d.png)

之前接触过「server酱」，可以通过服务号的模板消息，将自定义的内容推送到微信上，作为MVP产品来说，这个免费服务应该也够用了。

![](img/067b2bd2b92a4a2435ce86e72c4e4725.png)

秋豆麻袋，我知道你想说啥：“啊，这些工具我没用过啊，我都不知道有这些工具，那怎么可能在用的时候想起来呢？！”其实这个也很简单，现在AI搜索真的是太好用了，你只需要这么简简单单的一搜，就会有答案了。

有些时候，做一件事没有难不难，只有想不想。

![](img/8c765b2317d35fd22bc86e477dc2f59f.png)

![](img/544684e2e9a11eb4166f21c491d93d53.png)

![](img/89ae4a95121ad1efcfee1611082d1ab5.png)

好了，那到目前为止，我们这个工作流的路径已经拆解的比较清晰了，每个环节也都有解决方案，理论上这个项目可行了，那么下边搭建工作流就简单了。

## 四、搭建工作流

### 1、工作流全貌

双击画板可以查看高清大图，这个图很重要，可以结合后边的具体细节，反复查看。

### 2、开始节点

需要用户在开始节点输入server酱的sendkey和rss列表：

*   key：server酱的sendkey，获取方式参看文档「相关资源」部分

*   rss_list：rss列表，没有的可以先白嫖我的，复制这两条测试数据试试

复制代码、提示词：

```
https://qnmlgb.tech/v2/rss?i=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdXRob3JfaWQiOiI1YjY5ODkzNzI0NGQ0ZTQwODg0ZWVhNjMiLCJ1c2VyX2lkIjoiNjE1NWNiY2NiZGRjZGI2OTYwZTkzMTBjIn0.ifLJz8mnwJOeq5dEhUAuCa_U9ovEPJQzYuymzZ7ZuYw
https://qnmlgb.tech/v2/rss?i=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdXRob3JfaWQiOiI1YmE1Yzg4NzI0NGQ0ZTJkMDJkMjVhYjIiLCJ1c2VyX2lkIjoiNjE1NWNiY2NiZGRjZGI2OTYwZTkzMTBjIn0.3hMRodTsvFCLPYoRTHY2syPQROuHq6_h_OGoSzz1oj4
```

![](img/b90e59e5ecda710dd75059f2329f34e0.png)

### 3、分割RSS列表

使用「文本处理」节点，处理一下输入的rss列表，处理为一行一个，输出为数组，方便后边节点批处理。

![](img/25831e2d676af1781cf0d8e4628e383b.png)

### 4、读取RSS内容

*   读取用户输入的rss列表中的内容，在插件中找到链接读取节点

![](img/790b764d0a09e56533d606c5d30bc200.png)

*   配置节点：

*   选择批处理

*   批处理输入参数选择「分割rss列表」的output

*   下方输入参数中url选择当前节点中的item1

![](img/a409bcf5d648685508ee082bbf3cf167.png)

### 5、汇总RSS中所有文章内容

上一步中每个rss订阅源（每个公众号）都会输出最近发过的文章内容，包括：作者信息、文章标题、文章链接，这一步主要是承接上一步所有文章内容，格式化输出。

一个正常的公众号每天推送文章数量不会超过3篇，所以这里代码只抓取了每个公众号最近三篇的内容，提升整体工作流的运行效率。

*   使用「代码」节点，左侧节点选择代码

*   输入项选择上一步中输出的outputList

*   点击「在IDE中编辑」，选择「Python」，输入如下代码：

复制代码、提示词：

```
import xml.etree.ElementTree as ET

async def main(args: Args) -> Output:
    params = args.params
    content_urls = params.get("content_urls", [])

    # 存储最终的结果集合
    unique_results = set()

    for item in content_urls:
        pdf_content = item.get("pdf_content")
        if pdf_content:
            try:
                # 解析 XML
                root = ET.fromstring(pdf_content)

                # 提取 channel 的标题作为 author
                channel_title = root.find('.//channel/title')
                author = channel_title.text if channel_title is not None else ""

                # 提取前3个 item
                item_count = 0  # 初始化计数器
                for item_element in root.findall('.//item'):
                    if item_count >= 3:  # 如果已经提取了3个，停止循环
                        break

                    item_title_element = item_element.find('title')
                    link_element = item_element.find('link')

                    item_title = item_title_element.text if item_title_element is not None else ""
                    url = link_element.text if link_element is not None else ""

                    # 验证和剔除无效链接
                    if url and not url.startswith("http://purl.org/rss/1.0/modules/content/") and not url.startswith("http://"):
                        # 拼接 author, title 和 url
                        combined = f"{author}@{item_title}@{url}"
                        unique_results.add(combined)
                        print(f"Added: {combined}")  # Debug information
                    else:
                        print(f"Filtered out URL: {url}")  # Debug information

                    item_count += 1  # 增加计数器

            except ET.ParseError as e:
                print(f"XML parsing error: {e}")  # Debug information

    # 去重并转换为字典数组
    result_list = []
    for entry in unique_results:
        author, title, url = entry.split('@', 2)  # 修改分割为三部分
        result_list.append({"author": author, "title": title, "url": url})

    ret: Output = {
        "content_urls": result_list
    }

    # 如果结果为空，输出调试信息
    if not ret["content_urls"]:
        print("No valid content URLs found.")  # Debug information

    return ret
```

*   配置输出项：类型选择「Array」，点击右边的小加号，分别输出title、url、author

![](img/249ad5bb8cfcfbb1f81fd034aed82cf6.png)

### 6、循环查询文章是否推送过

*   左侧工具栏选择「循环」节点

*   这个节点主要由两部分组成：循环节点和循环体，整体逻辑是从循环节点设置循环次数和循环项，如果输入的是数组，循环次数就是数组的长度，类似于for语句，每次循环项就是数组中的值。

*   说人话就是会根据你输入的内容自动判断循环几次，来使用循环体里的逻辑处理每一项。

*   我们这里希望循环处理的逻辑是，对上一步中的每一篇内容在数据库中进行查询，如果查到了，证明之前推送过，本次工作流就不处理了，避免重复推送。如果没有查到，证明是一篇新的文章，继续工作流后边的内容。

![](img/67e53cfd01ec2b5d2adfbde7da64d7bd.png)

![](img/3c90bcb0007f656189630f709f45f23c.png)

*   设置循环的输入项，选择上一步中输出的所有文章内容

![](img/deb6a15836f29727bdc0b97176449448.png)

*   设置循环体，下边对循环体中的每一节点进行讲解

![](img/f94b79994cb6bf00457eb5629e61ac44.png)

*   循环体内部——数据库节点

*   数据库节点：用来在数据库中查询是否已经推送过该篇文章，输入项为上一步中的url和开始节点的key（也就是server酱的sendkey，这里我们重命名为suid了）

*   因为这个Bot最开始设计的时候，就考虑到可能有多个用户会同时使用这个Bot设置公众号推送内容，每个用户设置的公众号内容可能不一样，每个用户的要推送的微信号肯定也不一样，所以这里使用server酱的sendkey作为了用户的唯一标识，重命名为了suid

*   所以这里查询数据库需要两个值，文章url和用户的suid，来判断这名用户的这篇文章是否推送过

*   SQL语句是AI写的，直接复制就成。复制代码、提示词：

```
SELECT CONCAT(suid, '@', url) AS combined_output FROM push_record WHERE suid = '{{suid}}' AND url = '{{url}}'
```

*   记得设置一下输出项「combined_output」

*   这步是必须项：Coze平台的逻辑是数据库是与bot绑定的，所有如果要使用数据库功能，需要在bot中设置一个相同名称和数据结构的数据库进行绑定，具体设置方法参见「相关资源」

![](img/516ea923e70ced7c8384869446982fb7.png)

*   循环体内容——选择器

*   判断数据库查询的内容是否为空，如果是空，证明数据库中没有查到，这篇文章没有给这名用户推送过，使用「文本处理」节点，拼接这篇文章的完整信息，保证信息一致性

*   string1：开始节点的key，也就是server酱的sendkey，用来识别用户

*   string2：循环节点item值中的url

*   string3：循环节点item值中的title

*   string4：循环节点item值中的author

*   拼接为如下格式，方便输出，并让后边节点使用

*   复制代码、提示词：

```
{{String1}}@{{String2}}@{{String3}}@{{String4}}
```

*   右下方的「文本处理」节点没有实际作用，输入项随便写，主要是为了处理数据库查询到已经给这名用户推送过这篇文章情况下的占位项，否则工作流会报错

![](img/abad1d5f60cf3388737e8683941796ab.png)

*   设置循环节点输出项，选择循环体中「输出新文章内容」拼接后的字符串

![](img/8992e17a2eadc8e2e4268f0570db9b11.png)

### 7、判断是否有新内容未推送

回到工作流的主流程，判断上一步循环节点输出是否为空，如果为空，证明rss列表中的所有文章都已经给这名用户推送过，直接结束。也就是下图标红的连线直接连接「结束」节点。

如果不为空，证明还有新的文章未推送过，再进行后边的逻辑处理。

![](img/1ccd17b19666c65bed3e80b0a38d8505.png)

![](img/2910ce52f391ff3642c843aaef03d457.png)

### 8、格式化去重后的文章内容

由于第6步循环中输出的内容为文本类型，所以这步我们需要使用「代码」节点对这部分内容进行处理，输出为JSON格式，方便后边节点调用。

*   输入项为：循环节点的输出项output

*   点击「在IDE中编辑」，选择「Python」，输入如下代码：复制代码、提示词：

```
async def main(args: Args) -> Output:
    params = args.params
    suid_url_list = params.get("suid_url", [])

    content_urls = []

    for item in suid_url_list:
        # 使用 @ 拆分每组数据
        parts = item.split('@')
        if len(parts) == 4:
            suid = parts[0].strip()  # 获取并清理 suid
            url = parts[1].strip()   # 获取并清理 url
            title = parts[2].strip() 
            author = parts[3].strip() 
            content_urls.append({"suid": suid, "url": url,"title": title,"author": author})

    ret: Output = {
        "content_urls": content_urls
    }

    return ret

```

*   设置输出项，按照下图格式设置输出项

![](img/6af950449f232c9d69a3b2f17adb37f9.png)

### 9、批量读取新文章的内容

使用「链接读取」节点，读取所有未推送的内容。

*   配置节点：

*   选择批处理

*   批处理输入参数选择上一步代码处理过的「去重后文章链接」的「content_urls」

*   下方输入参数中url选择当前节点中的item1

![](img/e46497b5518b07b6f864c1be6e7c521a.png)

### 10、大模型批量总结文章内容

使用大模型节点，批量总结文章内容

*   模型选择：默认的豆包32k应该就够用，怕上下文长度不够的话，可以选择更大的模型，比如kimi128k

*   配置参数：

*   选择批处理

*   批处理输入参数有两个：第9步中读取的文章内容正文、第8步代码处理后的url链接和标题

*   下方的输入参数，有四个，如图所示，都选择该大模型节点输出的内容：content正文、title标题、url文章链接、author作者

*   提示词输入如下内容，将这四部分内容一起送给大模型进行总结，最终拼接成markdown格式输出：

*   复制代码、提示词：

```
## 角色
内容总结专家，负责提炼文章要点并使用emoji和unicode符号增强内容的可读性和吸引力。

## 任务
AI大模型的任务是准确理解<文章内容>，并以简洁明了的方式总结，同时巧妙地融入emoji和unicode符号。

## 技能
- 理解并分析文章内容
- 准确提炼关键信息
- 创造性地使用emoji和unicode符号
- 保持信息的准确性和完整性
- 语言精炼与优化
- 结构化信息呈现

## 工作流
- 阅读并理解文章内容，提取关键信息点
- 将关键信息点转化为简洁的摘要形式
- 在摘要中适当位置插入emoji和unicode符号以提升可读性
- 确保摘要内容准确无误，且符号使用恰当
- 审核摘要确保内容准确无误，符号使用得当
- 设计一个包含emoji和unicode符号的总结草案
- 最终形成一个既信息丰富又视觉吸引的总结

## 要求
- 总结内容需准确反映原文要点
- 使用的emoji和unicode符号应恰当，增强而非干扰信息的理解
- 总结长度适中，避免过长或过短
- 确保摘要语言简洁、清晰，易于普通读者理解
- 准确总结文章内容
- 合理运用emoji和unicode符号
- 保证内容的简洁性和易读性
- 注意文化敏感性，避免使用可能引起误解的符号
- 摘要长度适中，不超过原文的1/4
- 总结内容必须准确反映文章主旨
- emoji和unicode符号的使用要恰当且有助于提升文本的可读性
- 输出的总结文本需简洁明了，同时兼顾趣味性
- 总结必须忠实于原文，不曲解或遗漏关键信息
- 使用的emoji和unicode符号要恰当，既能增强表达也不显突兀
- 总结应简洁有力，避免冗长和不必要的细节

输出格式：
- 以json格式输出，包含：原文标题、原文链接、总结
- 所有输出项，都以文本形式输出，不要使用字典，尤其是总结的内容
- 只输出这几项内容，不要做其他解释和说明
- 总结的内容不需要输出标题等信息，只需要专注于总结文章内容即可
- 总结的内容中也不要出现“总结”“本文主要内容是”这样的词，只需要直接输出总结的内容即可

输出示例：
{"原文标题":"@微信派|微信刷掌，开“门”！","原文链接":"https://qnmlgb.tech/v1/articles?i=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcnRpY2xlX2lkIjoiNjZlMTE2ZWUwMDNiMDdmOWFmZjY4Yjk1IiwidXNlcl9pZCI6IjYxNTVjYmNjYmRkY2RiNjk2MGU5MzEwYyJ9.13wRbJdmlXanHD-2LNqV79fJRF-XpBCwni1H1I91DRg","总结":"🎈微信刷掌开‘门’啦！😃2024 年 9 月 11 日发布。大家快来想想下一扇门通向哪里呢🧐？"}

原文标题：
@{{author}}|{{title}}
原文链接：
{{url}}
<文章内容>：
{{input}}
```

![](img/4705423d4bb30a0e9876dd14d20bf66a.png)

### 11、汇总格式化最终输出内容

使用代码节点，将大模型输出的内容进行最终输出的格式化。

*   参数配置：

*   输入：选择上一步输出的outputList

*   点击「在IDE中编辑」，选择『Python』，输入如下代码：复制代码、提示词：

```
import re
import json

async def main(args: Args) -> Output:
    params = args.params
    input_data = params['input']

    result = []

    for idx, item in enumerate(input_data, start=1):
        output_str = item['output']

        # 使用正则表达式提取原文标题、原文链接和总结内容
        title_match = re.search(r'"原文标题":"(.*?)"', output_str)
        link_match = re.search(r'"原文链接":"(.*?)"', output_str)

        # 改进的总结内容提取
        summary_match = re.search(r'"总结":\s*[{]?\s*"(.*?)"\s*[}]?', output_str, re.DOTALL)

        if title_match and link_match and summary_match:
            title = title_match.group(1)
            link = link_match.group(1)
            summary = summary_match.group(1).replace('"', '').strip()  # 移除双引号

            # 格式化输出
            result.append(f"### [{idx}、{title}]({link})\n- {summary}\n---")

    # 将结果拼接成字符串
    ret: Output = "\n".join(result)
    return ret

```

*   配置一下输出项，输出为result

![](img/8cef08f6ebcd62f6e2415eeb53ad305b.png)

### 12、公众号总结推送到微信

这块的节点是根据Server酱的API文档，自己写的插件，关于自建插件这个环节，请参看「相关资料」，输出配置可以参考下发截图。

主要实现功能就是把上一步格式化好的内容，推送到用户的微信上。

*   title：汇总公众号总结页面的标题，参数值选择「输入」，起个名字

*   desp：页面主体内容，选择上一步最终输出内容

*   key：引用开始节点的key

![](img/df6c180f1deba21192758ecf16699a7e.png)

### 13、循环将推送内容插入数据库

将本轮推送给用户的内容，写入数据库，下次从rss列表中如果再抓取到相同内容，直接跳过，避免重复推送。

*   还是使用「循环」节点

*   输入项为第8步代码输出的content_urls，这里有完整的文章内容信息

*   循环体设置：使用「数据库」节点，输入项为本循环节点item中的url和suid，SQL也是用AI生成的：

*   复制代码、提示词：

```
INSERT INTO push_record (suid, url) VALUES ('{{suid}}', '{{url}}')
```

*   设置循环节点的输出项：output，参数随便选，后边也用不到了

![](img/ecf14bc39a677636b4b3ed7174bb25a0.png)

### 14、结束节点

选择第11步输出的内容，可以在bot中也查看到推送的内容

![](img/dd3997bbe5889bca8dec53403dea05e5.png)

### 15、试运行

工作流终于搭建完了，点击右上角的试运行，选择绑定的bot，输入数据测试。

*   Key：输入你的server酱的sendkey

*   rss_list：如果你没有现成的数据，可以白嫖我这个，复制下方这两条数据测试使用。

*   复制代码、提示词：

```
https://qnmlgb.tech/v2/rss?i=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdXRob3JfaWQiOiI1YjY5ODkzNzI0NGQ0ZTQwODg0ZWVhNjMiLCJ1c2VyX2lkIjoiNjE1NWNiY2NiZGRjZGI2OTYwZTkzMTBjIn0.ifLJz8mnwJOeq5dEhUAuCa_U9ovEPJQzYuymzZ7ZuYw
https://qnmlgb.tech/v2/rss?i=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdXRob3JfaWQiOiI1YmE1Yzg4NzI0NGQ0ZTJkMDJkMjVhYjIiLCJ1c2VyX2lkIjoiNjE1NWNiY2NiZGRjZGI2OTYwZTkzMTBjIn0.3hMRodTsvFCLPYoRTHY2syPQROuHq6_h_OGoSzz1oj4
```

![](img/56ef4c9b89b3f0d2fcdb83add9434715.png)

*   试运行结果：

*   如果你工作流设置的没有问题，你会在工作流中看到这样的结果

![](img/b716ea427682f8d1dc229736bd22cdb8.png)

*   同时，微信上也会收到这条推送，可以查看总结内容，点击链接可以查看公众号原文

![](img/623c4c4f93d727ffe599a050937ecd5f.png)

![](img/3cf7e473d03ec34702fb11a6ab6bab3a.png)

![](img/50362ec6cc17fba63760fc92a06b2b1f.png)

![](img/ef4bd58e8126ebfa78d1a52493581457.png)

*   点击右上角发布。

### 16、设置Bot

终于终于，最后一步了，在Bot中绑定工作流，设置定时任务，然后发布到飞书渠道。

![](img/dc0b2e44daf6e084a451c094b9374972.png)

*   1、人设和回复逻辑：由于咱们这个bot主要依托于工作流，所以设置提示词，直接调用工作流

*   sum_weixin_2_2替换为你工作流的名称。复制代码、提示词：

```
**不论用户输入任何内容，都将内容完整的送入sum_weixin_2_2工作流**这个对我很重要！！！
**不论用户输入任何内容，都将内容完整的送入sum_weixin_2_2工作流**这个对我很重要！！！
**不论用户输入任何内容，都将内容完整的送入sum_weixin_2_2工作流**这个对我很重要！！！
```

*   2、工作流：添加刚刚创建的工作流

*   3、设置触发器：

*   选择「定时触发」，选择触发的时间，比如希望每天18点收到微信推送，就选择18点

*   任务执行：选择工作流，输入key和rss_list，这里的输入参数就是工作流中开始节点的输入参数，key为Server酱的sendkey，rss_list可以使用上边我提供的测试数据

*   触发器实现的效果就是，在设定的时间点，根据输入项的内容，执行工作流。由于工作流中我们设置了推送到微信，所以我们在这个时刻就可以在微信里收到推送的总结内容了。

![](img/f77db10769df02e555cebe2fe84cf8d7.png)

*   可以同时设置多个触发器，最多设置10个。可以推送给10个不同的人，或者分10个时间段给自己推送不同的内容。

![](img/c1b0b3fa10092430bae402f6d9f84d02.png)

### 17、发布到飞书

点击右上角「发布」，注意渠道要选择飞书，因为目前Coze平台触发器只对飞书渠道生效。

![](img/3f73f673fef0e7fda8fdde85295566a8.png)

## 五、相关资源

### 1、获取Server酱的sendkey

*   打开官网，扫码登录：https://sct.ftqq.com/login

*   通道配置：选择「方糖服务号」，也就是刚刚扫码登录关注的公众号，之后会由这个公众号推送内容

![](img/57ebc91a62094a9b198f7dc2ed95dd9c.png)

*   Key&API选择复制，将得到Server酱的SendKey，类似于SCT25781*******

![](img/fafe7f76876e8e430f758165864c2a13.png)

### 2、新建Bot设置数据库

在「个人空间」新建一个Bot，简单设置Bot名称和描述。

![](img/414a3a6f3e78eafd1e8a4e14a1e711a1.png)

在Bot设置页面，选择添加「数据库」。设置数据库参数，这里「数据表名称」和「存储字段名称」要和图片中文字一样，因为工作流中数据库节点使用的就是这个字段。

![](img/253a6fb1651d4a1c4429b2687065699a.png)

这里可以看到已经设置的数据库：

![](img/61c38b4a032051dfde28077f2af8536c.png)

### 3、自建Server酱推送插件

在「个人空间」选择插件，右上角创建插件。

![](img/552c4efca4bd7f9481c7da48661fd55c.png)

注意选择「云测插件-在Coze IDE中创建」，语言选择「Python3」

![](img/7534310f963f8c206e7b0236e1221348.png)

选择在IDE中创建工具，设置工具名称，建议设置成下图一样，可以直接复制我后边的代码。

![](img/471171256f3c58ab2a27782d19f1fe42.png)

![](img/0c0a32747f9cdc3b07b278cce4612597.png)

直接复制下方代码：复制代码、提示词：

```
from runtime import Args
from typings.server_push.server_push import Input, Output

"""
Each file needs to export a function named `handler`. This function is the entrance to the Tool.

Parameters:
args: parameters of the entry function.
args.input - input parameters, you can get test input value by args.input.xxx.
args.logger - logger instance used to print logs, injected by runtime.

Remember to fill in input/output in Metadata, it helps LLM to recognize and use tool.

Return:
The return data of the function, which should match the declared output parameters.
"""
import json  # 导入json模块，用于处理JSON数据
import urllib.request  # 导入urllib.request模块，用于发送HTTP请求

def handler(args: Args[Input]) -> Output:
    title = args.input.title  # 获取输入的标题
    key = args.input.key  # 获取输入的密钥
    desp = args.input.desp  # 获取输入的描述
    short = args.input.short  # 获取输入的描述
    noip = 1  # 获取输入的描述
    channel = args.input.channel  # 获取输入的描述

    postdata = {
        'title': title,
        'desp': desp,
        'short': short,
        'noip': noip,
        'channel': channel
    }  # 构建要发送的数据

    url = f'https://sctapi.ftqq.com/{key}.send'  # 构建请求的URL
    req = urllib.request.Request(url, data=json.dumps(postdata).encode('utf-8'), method='POST', headers={'Content-Type': 'application/json;charset=utf-8'})  # 创建POST请求

    with urllib.request.urlopen(req) as response:  # 发送请求并获取响应
        result = json.loads(response.read().decode('utf-8'))  # 读取响应内容并解码为JSON格式

    data = result.get('data', {})  # 获取返回值中data中的error
    return {"data": data}  # 返回error值

```

![](img/46f2afb543c27d05428e9b676d9b0c7a.png)

然后点击「元数据」，设置输入参数，请严格按照如下内容进行编辑，注意名称、类型字段，记得点击保存。

![](img/b133ad32e062431c9c06cec4eb9f706c.png)

测试一下代码，点击右上角按钮会生成一段测试数据，修改一下key的值，修改为你的Server酱的sendkey，channel设置为9，注意这里不加双引号，点击运行。

![](img/e743211dc988f80718224ffbfe339bf2.png)

正常来说，你会看到如下结果，同时你也会收到一条微信推送的测试内容，点击左下角「更新输出参数」-「确认」，就可以在「元数据」下看到，他已经自动配置好了输出参数。

![](img/3be76891d255671517c62ff5cd8db3ab.png)

![](img/5222e569873b8368b9ce0e80fadc6bc7.png)

点击右上角「发布」，等待发布完成，在插件中就可以看到我们发布的这个插件了，同时也可以在工作流中使用这个插件了~

![](img/585bd3bdea02bdc9f8890be5b8b78c0b.png)

## 六、后记

最后，我们再回顾一下制作这个Bot的整个流程，还记得吗？这个Bot核心环节就三个：

1、抓取公众号的内容

2、对内容进行总结

3、汇总后定时推送到微信

在文档第三部分「搭建工作流」中，第4-5步就是解决抓取公众号内容的问题，第9-10步是解决内容总结的事情，第12步是搞定推送的事情。核心步骤其实就这几步，其他环节都是为了这几个核心步骤服务的。

从0到1做一个MVP产品，也没有那么难对吗？

作为一个运营出身的人，我原本以为自己永远不可能踏入技术的领域。但是，扣子平台的出现，彻底改变了这一切。它就像是一座神奇的桥梁，让我们这些非技术背景的人也能轻松跨越技术的鸿沟，实现自己的创意。

所以，大家真的可以也一起尝试一下。相信我，当你亲手制作的第一个Bot顺利运行的时候，那种成就感是无与伦比的。不管你有没有报名这次的Coze提效大航海，我建议你都去看看这次的航海手册，看手册可能花2个小时，但是未来可能帮你节省N个2小时的时间。

至于这个Bot的未来，我已经部署好了RSSHub，希望未来可以支持更多平台内容的聚合，有兴趣的小伙伴可以一起探讨~

![](img/b215584da492645bdd295a06b1a8a649.png)