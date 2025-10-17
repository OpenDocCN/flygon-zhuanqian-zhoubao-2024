# 153个公众号AI KOL十万加文章采集与分析

> 来源：[https://ia0969wpr2.feishu.cn/docx/VF9xdLsdQoTjqWxTM2PcszOqnPb](https://ia0969wpr2.feishu.cn/docx/VF9xdLsdQoTjqWxTM2PcszOqnPb)

前两天亦仁发了一篇超级标的文章，提出了一个AI赛道的一个新风向标，那就是做垂直类的AI资讯或者工具，最终接商单或者其他变现。

那我就在想，能不能先做个调研，看下现在成功的AI KOL的运作模式，这样或许可以更好地把握超级标的机会。为了更深入地理解这个概念，我进行了一次数据驱动的分析，尝试能否还原AI KOL自媒体的成功路径，从而带来一些参考。

第一步我想着先收集目前所有平台的AI关键词的一手资讯、工具介绍，和目前知名的AI KOL的所有历史文章和作品，首先把这些都先采集下来分析一下，全面了解AI自媒体的现状和趋势。

那就先从公众号的AI KOL开始，目前完成了下面的工作：

1.  采集了153 个公众号AI垂类排行榜靠前KOL的所有历史文章。总数超过7万条，包括原始链接、阅读量、点赞数、发布时间等。

1.  使用AI对文章摘要分析和软文识别等。

1.  对每个公众号维度进行趋势分析，包括爆发时间点、阅读量趋势等。此外还使用Claude制作了可视化图表，方便观察每个公众号的阅读量变化趋势和爆款文章，生成公众号分析报告。

接下来我会分享包括采集到的7万条AI KOL的所有原始公众号文章数据、Ai分析提示词等给大家，方便大家研究公众号AI垂类赛道，后续我也会继续实时采集全网如小红书抖音推特等热门KOL的所有作品并持续同步。

我们以卡兹克公众号为例，首先根据采集到的数据统计基本信息，包括发表文章数、阅读数等基本信息、不同分类的文章等。

![](img/5f842cdd71920f5872b4e694cf9e7989.png)

我们按照文章阅读数排序，可以看到卡兹克是24年1月10号一篇介绍magnificAI首次阅读十万加，二月份sora的文章再次十万加，这次彻底破圈，随后再接下来半年多的时间内，疯狂斩获了11篇超级爆款，这些爆款分别为：

![](img/43f37a29cfef98813fc7f0420c2c161d.png)

通过阅读数和时间变化关系，我们可以看到在第一篇十万加前，2023年12月6号的一篇关于pika达到了历史最高，为7.8万阅读：【全网首发】PIKA1.0上手评测：https://mp.weixin.qq.com/s?__biz=MzIyMzA5NjEyMA%3D%3D&mid=2647660666&idx=1&sn=0e9e2a11d5c06cd512479d35ca84bf3f，在此之前，最高阅读数为4万。下面是整体的趋势图：

![](img/df7b3a61456167c99cd2c5663b9fb92b.png)

文章阅读数和篇数分布图：

![](img/46644643223447b5370e4ce4cec67ea1.png)

下面以月为单位对文章阅读和点赞数进行分析，可以看到卡兹克的整体流量攀升大概是在24年1月份，自此以后始终维持在一个高点。

![](img/f817e9b50eb5167081646bfa708bbb9c.png)

我们把数据信息扔给claude，可以总结卡兹克公众号整体突破的时间节点：

1.  早期积累阶段（2023.2-2023.12.5）：最高阅读量为4万，持续输出高质量内容，积累种子用户。

1.  爆发期（2023.12.6-2024.2）：

*   2023年12月6日：关于Pika的评测文章获得7.8万阅读，创下当时记录。

*   2024年1月和2月：分别以magnificAI和Sora为主题的文章突破10万+阅读，实现真正破圈。

1.  持续高产期（2024.2-）：持续输出AI应用的内容，总共11篇文章突破10万+阅读。主题涵盖AI工具测评、技术突破解读、行业应用案例等。

上面是使用AI对采集到的公众号维度的数据分析。下面是整个过程分享，方便同样对AI数据分析感兴趣的同学参考。

首先我们在新榜找到了AI 账号榜单，地址是：https://www.newrank.cn/rankai/gongzhonghao，这里可以看到AI领域比较有名的公众号，我们接下来的先后采集AI日榜和月榜，合并去重后共153个账号，接下来就以下面的153个账号作为对标对象，采集所有的文章信息。

![](img/6d1ea28392972327e73283abee0147d1.png)

我们需要导出榜单，但是发现只能导出前20条，不过问题不大，我们可以使用影刀可以两行代码搞定，首先获取到当前标签页，然后选择批量数据抓取，数据采集，相似元素拿到所有的表格数据并手动导出，这时候我们就拿到了所有的表格信息，可以用于公众号数据采集。

![](img/8e65ee234137a205829e31e679deb19d.png)

具体采集部分大家各显神通，这里就不多介绍了，直接上数据，地址： 飞书多维表格对数据条数应该有限制，条数过多上传会失败，这是原始的excel：

以上是采集完成的公众号文章，大概7万篇左右，把公众号上AI领域比较有名的KOL的文章基本都已经采集了，还有一些在持续更新。拿到这部分数据之后我们就要开始可视化地分析了，毕竟一大坨数据我们无从着手，看起来也不方便。我们直接问claude 可以从哪些方面针对这些数据进行可视化和处理。

我收集了一系列微信公众号文章的公开数据，我想对这些数据进行深入分析，以评估账号的受欢迎文章、账号特点、随时间阅读数的趋势和整体影响力，从而学习账号的增长和运营策略等吸引同类用户群体，从多维度分析公众号的阅读趋势和用户行为，从而获取深度洞察。具体需求如下：

1.  数据可视化：

*   创建交互式仪表板，展示关键指标的时间序列趋势。

*   设计多样化的图表类型，包括但不限于折线图、柱状图、热力图和散点图。

*   实现数据分层和钻取功能，允许从宏观趋势深入到具体文章级别的分析。

1.  多维度分析：

*   阅读量趋势：按日、周、月展示文章阅读量的变化。

*   互动率分析：计算并可视化点赞数、评论数与阅读量的比率。

*   发布时间影响：分析发文时间与阅读量之间的相关性。

1.  报告生成：

*   自动生成包含关键发现和建议的周期性报告。

*   支持自定义报告模板和导出功能。

我的数据库表结构如下：CREATE TABLE `wechat_articles` (

`id` int NOT NULL AUTO_INCREMENT,

`user_name` varchar(255) COLLATE utf8mb4_general_ci DEFAULT NULL,

`nick_name` varchar(255) COLLATE utf8mb4_general_ci DEFAULT NULL,

`original_article_count` varchar(255) COLLATE utf8mb4_general_ci DEFAULT NULL,

`original_content_str` text COLLATE utf8mb4_general_ci,

`title` text CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci,

`digest` text COLLATE utf8mb4_general_ci,

`show_desc` text COLLATE utf8mb4_general_ci,

`item_index` varchar(255) COLLATE utf8mb4_general_ci DEFAULT NULL,

`url` varchar(255) COLLATE utf8mb4_general_ci DEFAULT NULL,

`is_original` tinyint(1) DEFAULT NULL,

`read_view` int DEFAULT NULL,

`like_count` int DEFAULT NULL,

`send_time` datetime DEFAULT NULL,

`collect_time` datetime DEFAULT NULL,

PRIMARY KEY (`id`),

UNIQUE KEY `url` (`url`)

) ENGINE=InnoDB AUTO_INCREMENT=18252 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

请提供一个能够满足以上需求的数据可视化解决方案，包括推荐的工具、技术栈和实现步骤。请你的实现尽可能简单，目的是帮我尽快生成相关的报告。

![](img/c1b9ca29b9de87a7bac57e9180035550.png)

![](img/671403ca4c24bf1bd7d6ec02689df56a.png)

cursor顺利生成可执行的代码，但是操作起来是还比较复杂，我希望能够一键自动生成可视化图表并导出报告

尽可能简单，使用一个脚本搞定

![](img/81d392d91931fd41494d2f8c93765b3b.png)

![](img/4cab3c7ab6e52f172891b83f30547965.png)

第二次生成的代码已经完整地实现了需求，但是cursor误把表中所有数据当成了一个公众号，我们适当提醒他，并且明确一下关键指标项：

我的数据中有超过100个不同的公众号，请你对所有账号进行逐个分析最终输出报告，每个独立的公众号需要有公众号名称（nickname）、最早的文章日期、最新的文章日期、评论阅读数、平均点赞数、文章总数、原创数（isorigin）。还要帮我列出阅读数最高的20篇文章、画出阅读数随时间的变化趋势图、文章阅读数分布图、以月为单位的阅读/点赞数趋势图。

这时再次执行，已经完整地输出了每个公众号的分析报告，但是还是不完美，我希望能合并输出一个PDF即可，方便阅读

![](img/6888fe0208392b0643809ef84012ea06.png)

![](img/7d50635e32b1b37997ec046ab207099e.png)

![](img/b78b333de4172e4c4c5ce6cb76548e88.png)

![](img/76cce99e47107586265ba2363217b863.png)

![](img/7ff5936a689d7da1be8a6e8c4f5f91e3.png)

请直接生成一个总的PDF即可，请注意帮我生成公众号目录，方便我直接点击跳转到对应公众号

![](img/af421c6bd4c11b56f051bfbf84d14f11.png)

![](img/3a3a93b45e591a9ff635834e356e30ac.png)

![](img/0bef3a96ae8019804d248f6fb2cce570.png)

最终生成的PDF如下：

下面是完整的代码，AI生成并一次通过：

```
import pandas as pd
import matplotlib.pyplot as plt
from sqlalchemy import create_engine
from matplotlib.backends.backend_pdf import PdfPages
import seaborn as sns
import os
import matplotlib as mpl
from reportlab.pdfgen import canvas
from reportlab.lib.pagesizes import letter
from reportlab.pdfbase import pdfmetrics
from reportlab.pdfbase.ttfonts import TTFont
from PyPDF2 import PdfMerger, PdfReader, PdfWriter
from io import BytesIO

# 设置中文字体
mpl.rcParams['font.sans-serif'] = ['SimHei']  # 指定默认字体为黑体
mpl.rcParams['axes.unicode_minus'] = False  # 解决保存图像时负号'-'显示为方块的问题

# 注册中文字体
pdfmetrics.registerFont(TTFont('SimHei', 'SimHei.ttf'))

# 连接数据库并读取数据
engine = create_engine('mysql+pymysql://username:password@host/wechat_article')
query = "SELECT * FROM wechat_articles"
df = pd.read_sql(query, engine)

# 数据预处理
df['send_time'] = pd.to_datetime(df['send_time'])
df['collect_time'] = pd.to_datetime(df['collect_time'])

# 创建输出目录
output_dir = 'wechat_analysis_reports'
os.makedirs(output_dir, exist_ok=True)

# 创建一个PDF合并器
merger = PdfMerger()

# 创建目录
toc = []

# 对每个公众号进行分析
for i, nickname in enumerate(df['nick_name'].unique(), 1):
    account_df = df[df['nick_name'] == nickname]

    # 创建临时PDF文件
    temp_pdf = BytesIO()
    with PdfPages(temp_pdf) as pdf:

        # 1\. 公众号基本信息
        plt.figure(figsize=(12, 6))
        info = {
            '公众号名称': nickname,
            '最早文章日期': account_df['send_time'].min().strftime('%Y-%m-%d'),
            '最新文章日期': account_df['send_time'].max().strftime('%Y-%m-%d'),
            '平均阅读数': f"{account_df['read_view'].mean():.2f}",
            '平均点赞数': f"{account_df['like_count'].mean():.2f}",
            '文章总数': len(account_df),
            '原创文章数': account_df['is_original'].sum()
        }
        plt.text(0.1, 0.1, '\n'.join([f'{k}: {v}' for k, v in info.items()]), {'fontsize': 12})
        plt.axis('off')
        plt.title(f'公众号基本信息 - {nickname}')
        pdf.savefig()
        plt.close()

        # 2\. 阅读数最高的20篇文章
        top_articles = account_df.nlargest(20, 'read_view')[['title', 'read_view', 'like_count', 'send_time']]
        plt.figure(figsize=(12, 10))
        plt.barh(top_articles['title'], top_articles['read_view'])
        plt.title(f'阅读数最高的20篇文章 - {nickname}')
        plt.xlabel('阅读数')
        plt.tight_layout()
        pdf.savefig()
        plt.close()

        # 3\. 阅读数随时间的变化趋势图
        plt.figure(figsize=(12, 6))
        account_df.set_index('send_time')['read_view'].plot()
        plt.title(f'阅读数随时间的变化趋势 - {nickname}')
        plt.ylabel('阅读数')
        pdf.savefig()
        plt.close()

        # 4\. 文章阅读数分布图
        plt.figure(figsize=(12, 6))
        sns.histplot(account_df['read_view'], kde=True)
        plt.title(f'文章阅读数分布 - {nickname}')
        plt.xlabel('阅读数')
        pdf.savefig()
        plt.close()

        # 5\. 月度阅读数和点赞数趋势图
        monthly_stats = account_df.set_index('send_time').resample('M').agg({
            'read_view': 'mean',
            'like_count': 'mean'
        })

        fig, ax1 = plt.subplots(figsize=(12, 6))
        ax2 = ax1.twinx()

        ax1.plot(monthly_stats.index, monthly_stats['read_view'], 'g-')
        ax2.plot(monthly_stats.index, monthly_stats['like_count'], 'b-')

        ax1.set_xlabel('日期')
        ax1.set_ylabel('平均阅读数', color='g')
        ax2.set_ylabel('平均点赞数', color='b')

        plt.title(f'月度平均阅读数和点赞数趋势 - {nickname}')
        plt.tight_layout()
        pdf.savefig()
        plt.close()

    # 将临时PDF添加到合并器
    temp_pdf.seek(0)
    merger.append(temp_pdf)

    # 添加到目录
    toc.append((nickname, i))

    print(f"已生成 {nickname} 的报告")

# 创建目录页
toc_pdf = BytesIO()
c = canvas.Canvas(toc_pdf, pagesize=letter)
c.setFont("SimHei", 14)
c.drawString(100, 750, "目录")
y = 700
for name, page in toc:
    c.setFont("SimHei", 12)
    c.drawString(100, y, f"{name}")
    c.drawString(400, y, f"{page}")
    y -= 20
    if y < 50:
        c.showPage()
        y = 750
c.save()

# 将目录添加到合并器的开头
toc_pdf.seek(0)
merger.merge(0, toc_pdf)

# 保存最终的PDF
final_pdf_path = os.path.join(output_dir, 'wechat_analysis_report.pdf')
merger.write(final_pdf_path)
merger.close()

print(f"总报告已生成：{final_pdf_path}")
```

虽然生成了报告，但是我想继续优化界面美观度，并且能够动态切换等，这时候就只能写个前端页面了，我们继续让cursor根据需求生成视觉效果和交互体验更佳的页面。

这部分因为cursor 超过了500条限制，重新注销后丢失了提示词，我就直接粘贴所有代码在下面了，这部分实现的是整体的界面优化，最终实现的就是开头截图的效果：

```
'use client';

import { useEffect, useState } from "react";
import { LineChart, Line, XAxis, YAxis, CartesianGrid, Tooltip, Legend, BarChart, Bar, ScatterChart, Scatter } from 'recharts';
import {  TooltipProps } from 'recharts';
import { NameType, ValueType } from 'recharts/types/component/DefaultTooltipContent';
import { useCallback } from 'react';
import WordCloud from 'react-d3-cloud';

import {WechatArticle} from "@/app/types/wechatarticle"
export default function Wechat() {

  const [selectedUsername, setSelectedUsername] = useState('gh_57bbdcde9820');
  const [isLoading, setIsLoading] = useState<boolean>(false);

  const publicAccounts = [

  ];
  interface ApiResponse {
    code: number;
    message: string;
    data: WechatAccount[];
  }
  interface WechatAccount {
    nickname: string;
    username: string;
    createTime: string;
    fetchTime: string | null;
  }
  interface WechatAnalyticsProps {
    chartData: {
      readViewTrend: Array<{ sendTime: string; readView: number }>;
      readViewDistribution: Array<{ label: string; count: number }>; // 修改这里

      readLikeScatter: Array<{ readView: number; likeCount: number }>;
      monthlyStats: Array<{ month: string; avgReadView: number; avgLikeCount: number; articleCount: number }>;
    };
  }
  interface WechatAnaInfo {
    data: {
      data: {
        stats: {
          wechatNickname: string;
          earliestArticleDate: string;
          latestArticleDate: string;
          averageReadCount: number;
          averageLikeCount: number;
          totalArticles: number;
          totalOriginalArticles: number;
        };
        viralArticles: WechatArticle[];
        surgeArticles: WechatArticle[];
        topLikedArticles: WechatArticle[];
        topReadArticles: WechatArticle[];
        earliestArticles: WechatArticle[];
        latestArticles: WechatArticle[];
        aboveAverageReadArticles: WechatArticle[];
        allArticles: WechatArticle[];
        chartData: WechatAnalyticsProps['chartData'];
      };
    };
  }

const [wechatarticleInfo, setWechatarticleInfo] = useState<wechatarticle>([]);
const [wechatanaInfo, setWechatanaInfo] = useState<wechatanainfo null="">(null);
const [stats, setStats] = useState<any>(null);
const [activeTab, setActiveTab] = useState<string>("最新文章");
const [activeAccounts, setActiveAccounts] = useState<wechataccount>([]);

const fontSizeMapper = useCallback((word: { value: number }) => Math.log2(word.value) * 5 + 16, []);

const generateWordCloudData = (articles: WechatArticle[]) => {
  const wordCount: { [key: string]: number } = {};
  articles.forEach(article => {
    const words = article.title.split(/\s+/);
    words.forEach(word => {
      if (word.length > 1) {  // 忽略单个字符
        wordCount[word] = (wordCount[word] || 0) + 1;
      }
    });
  });
  return Object.entries(wordCount).map(([text, value]) => ({ text, value }));
};
const getActiveAccounts = async () => {
  setIsLoading(true);
  try {
    const uri = "/api/wechat/keyword";

    const response = await fetch(uri, {
      method: "POST",
    });
    if (response.ok) {
      const result: ApiResponse = await response.json();
      if (result.code === 0 && Array.isArray(result.data)) {
        setActiveAccounts(result.data);
        if (result.data.length > 0) {
          setSelectedUsername(result.data[0].username);
        }
      } else {
        console.error("获取活跃公众号失败:", result.message);
        setActiveAccounts([]);
      }
    } else {
      console.error("获取活跃公众号失败: 服务器响应错误");
      setActiveAccounts([]);
    }
  } catch (error) {
    console.error("获取活跃公众号失败:", error);
    setActiveAccounts([]);
  } finally {
    setIsLoading(false);
  }
};
 const getWechatInfo = async () => {
  try {
    const uri = "/api/wechat_info";
    const params = {
      "keyword":"username"
    };
    const resp = await fetch(uri, {
      method: "POST",
      body: JSON.stringify(params),
    });
    if (resp.ok) {
      const res = await resp.json();
      console.log("开始设置咯", res)
      setWechatarticleInfo(res)
    }
  } catch (e) {
    console.log("insert failed: ", e);
  }
 }

 const getWechatAna = async (username: string) => {
  setIsLoading(true);
  try {
    const uri = "/api/wechat/ana";
    const params = {
      "username": username
    };
    const resp = await fetch(uri, {
      method: "POST",
      body: JSON.stringify(params),
    });
    if (resp.ok) {
      const res = await resp.json();
      console.log("开始设置ana咯", res);
      setWechatanaInfo(res);
      setSelectedUsername(username);
    }
  } catch (e) {
    console.log("获取数据失败: ", e);
  } finally {
    setIsLoading(false);
  }
}

 useEffect(() => {
  if (selectedUsername) {
    getWechatAna(selectedUsername);
  }
}, [selectedUsername]);

useEffect(() => {
  getActiveAccounts();
}, []);

  const renderStats = () => {
    if (!wechatanaInfo || !wechatanaInfo.data || !wechatanaInfo.data.data) return null;

    const { stats, viralArticles, allArticles, topLikedArticles, topReadArticles, earliestArticles, latestArticles, aboveAverageReadArticles, chartData } = wechatanaInfo.data.data;

    return (

# 公众号名称：{stats.wechatNickname}

          最早文章日期
          {new Date(stats.earliestArticleDate).toLocaleDateString('zh-CN')}

          最新文章日期
          {new Date(stats.latestArticleDate).toLocaleDateString('zh-CN')}

          平均阅读数
          {stats.averageReadCount}

          平均点赞数
          {stats.averageLikeCount}

          文章总数
          {stats.totalArticles}

          原创文章数
          {stats.totalOriginalArticles}

       setActiveTab("所有文章")}>所有文章
           setActiveTab("爆款文章")}>爆款文章
           setActiveTab("最新文章")}>最新文章🔥
           setActiveTab("阅读最高")}>阅读最高
           setActiveTab("点赞最高")}>点赞最高
           setActiveTab("最早文章")}>最早文章
           setActiveTab("高于平均阅读")}>高于平均阅读

        {activeTab === "所有文章" && renderArticleTable("所有文章", allArticles)}
        {activeTab === "爆款文章" && renderArticleTable("爆款文章", viralArticles)}
        {activeTab === "点赞最高" && renderArticleTable("点赞最高的文章", topLikedArticles.slice(0, 10))}
        {activeTab === "阅读最高" && renderArticleTable("阅读最高的文章", topReadArticles.slice(0, 20))}
        {activeTab === "最早文章" && renderArticleTable("最早发布的文章", earliestArticles.slice(0, 10))}
        {activeTab === "最新文章" && renderArticleTable("最新发布的文章", latestArticles.slice(0, 10))}
        {activeTab === "高于平均阅读" && renderArticleTable("高于平均阅读数的文章", aboveAverageReadArticles)}

    );
  };

  const renderArticleTable = (title: string, articles: WechatArticle[]) => {
    return (

## {title}

          {articles.map((article, index) => (

          ))}

             标题 |
               阅读数 |
               点赞数 |
               发布时间 |
               链接 |

| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

               {article.title} |
               {article.readView} |
               {article.likeCount} |
               {new Date(article.sendTime).toLocaleDateString('zh-CN')} |
                                []({article.url}) 
               |

    );
  };

  const renderChart = () => {
    if (!wechatanaInfo || !wechatanaInfo.data || !wechatanaInfo.data.data) return null;
    const { allArticles, chartData } = wechatanaInfo.data.data;

    if (!chartData) return null;

    const wordCloudData = generateWordCloudData(allArticles);

    const CustomTooltip = ({ active, payload, label }: TooltipProps<valuetype nametype="">) => {
      if (active && payload && payload.length) {
        return (

{`阅读数范围: ${label}`}

{`文章数量: ${payload[0].value}`}

        );
      }

      return null;
    };

    return (

        <chartsection title="阅读数随时间变化趋势"><linechart width="{800}" height="{400}" data="{chartData.readViewTrend}"><xaxis datakey="sendTime" name="时间"><yaxis><cartesiangrid strokedasharray="3 3"></cartesiangrid></yaxis></xaxis></linechart></chartsection> 

        <chartsection title="文章阅读数分布"><barchart width="{800}" height="{400}" data="{chartData.readViewDistribution}"><xaxis datakey="label"><yaxis><cartesiangrid strokedasharray="3 3"><tooltip content="{<CustomTooltip">} />
          <legend><bar datakey="count" name="文章数量" fill="#8884d8"></bar></legend></tooltip></cartesiangrid></yaxis></xaxis></barchart></chartsection> 

        <chartsection title="月度统计"><linechart width="{800}" height="{400}" data="{chartData.monthlyStats}"><xaxis datakey="month"><yaxis yaxisid="left"><yaxis yaxisid="right" orientation="right"><cartesiangrid strokedasharray="3 3"></cartesiangrid></yaxis></yaxis></xaxis></linechart></chartsection> 

        <chartsection title="阅读数与点赞数关系"><scatterchart width="{800}" height="{400}"><xaxis datakey="readView" name="阅读数"><yaxis datakey="likeCount" name="点赞数"><tooltip cursor="{{" strokedasharray:=""><scatter name="阅读-点赞" data="{chartData.readLikeScatter}" fill="#8884d8"></scatter></tooltip></yaxis></xaxis></scatterchart></chartsection> 

        {/* <chartsection title="文章标题词云">

        </chartsection> */}

    );
  };
  const ChartSection = ({ title, children }: { title: string, children: React.ReactNode }) => (

## {title}

      {children}

  );
  return (

        {activeAccounts.map((account, index) => (
          setSelectedUsername(account.username)}
          >
            {account.nickname || account.username} 
        ))}

      {isLoading ? (
        加载中...
      ) : (
        <>
          {renderStats()}
          {renderChart()}
        >
      )}

  );
}</valuetype></wechataccount></string></any></wechatanainfo></wechatarticle></boolean> 
```

Next实现的API

Route:

```
import { respData, respErr } from "@/app/utils/resp";

import { analyzeWechatAccount } from "@/app/models/wechatinteract";

export async function POST(req: Request) {
  const { username } = await req.json();

  const articles = await analyzeWechatAccount(username)

  return respData(articles);
}

```

API：

```
import mysql, { FieldPacket } from 'mysql2/promise';
import { WechatArticle } from '@/app/types/wechatarticle';
import { RowDataPacket } from 'mysql2';

// 数据库连接配置
const dbConfig = {
  your host address
};

// 获取数据库连接
async function getDbConnection() {
  return await mysql.createConnection(dbConfig);
}

async function getWechatArticlesByUsername(username: string): Promise {
  const conn = await getDbConnection();
  try {
    const query = `
      SELECT 
        id, user_name, nick_name, title, digest, url, 
        is_original, read_view, like_count, send_time
      FROM wechat_articles 
      WHERE user_name = ? 
      ORDER BY send_time DESC
    `;
    const [rows] = await conn.execute<rowdatapacket>(query, [username]);

    return rows.map(row => ({
      id: row.id,
      userName: row.user_name,
      nickName: row.nick_name,
      title: row.title,
      digest: row.digest,
      url: row.url,
      isOriginal: Boolean(row.is_original),
      readView: row.read_view,
      likeCount: row.like_count,
      sendTime: new Date(row.send_time)
    }));
  } finally {
    await conn.end();
  }
}

// 获取公众号文章数据

async function fetchData(userName: string): Promise <wechatarticle>{
  const conn = await getDbConnection();
  try {
    const [rows] = await conn.execute<mysql.rowdatapacket>(
      'SELECT * FROM wechat_articles WHERE user_name = ? order by send_time desc',
      [userName]
    );
    const articles = rows.map(row => ({
      id: row.id,
      userName: row.user_name,
      nickName: row.nick_name,
      title: row.title,
      digest: row.digest,
      url: row.url,
      isOriginal: Boolean(row.is_original),
      readView: row.read_view,
      likeCount: row.like_count,
      sendTime: new Date(row.send_time)
    }));

    // 计算原创文章数量
    const originalArticleCount = articles.filter(article => article.isOriginal).length;

    // 将原创文章数量添加到每个文章对象中
    return articles.map(article => ({
      ...article,
      originalArticleCount
    }));
  } finally {
    await conn.end();
  }
}

// 预处理数据
function preprocessData(articles: WechatArticle[]): WechatArticle[] {
  return articles.sort((a, b) => a.sendTime.getTime() - b.sendTime.getTime());
}

// 计算统计信息
function calculateStats(articles: WechatArticle[]) {
  return {
    wechatNickname: articles[0].nickName,
    earliestArticleDate: articles[0].sendTime,
    latestArticleDate: articles[articles.length - 1].sendTime,
    averageReadCount: Math.round(articles.reduce((sum, article) => sum + article.readView, 0) / articles.length),
    averageLikeCount: Math.round(articles.reduce((sum, article) => sum + article.likeCount, 0) / articles.length),
    totalArticles: articles.length,
    totalOriginalArticles: articles[0].originalArticleCount

  };
}

// 分析爆款文章
function analyzeViralArticles(articles: WechatArticle[]): WechatArticle[] {
  const threshold = articles.reduce((sum, article) => sum + article.readView, 0) / articles.length * 2;
  return articles
    .filter(article => article.readView > threshold)
    .sort((a, b) => b.readView - a.readView)
    .slice(0, 5);
}

// 分析阅读量增长
function analyzeReadViewGrowth(articles: WechatArticle[]): WechatArticle[] {
  const growthRates = articles.map((article, index) => {
    if (index === 0) return 0;
    return (article.readView - articles[index - 1].readView) / articles[index - 1].readView;
  });

  const meanGrowth = growthRates.reduce((sum, rate) => sum + rate, 0) / growthRates.length;
  const stdDevGrowth = Math.sqrt(growthRates.reduce((sum, rate) => sum + Math.pow(rate - meanGrowth, 2), 0) / growthRates.length);
  const growthThreshold = meanGrowth + 2 * stdDevGrowth;

  return articles.filter((_, index) => growthRates[index] > growthThreshold);
}

// 获取点赞最高的十篇文章
function getTopLikedArticles(articles: WechatArticle[], limit: number = 10): WechatArticle[] {
  return [...articles].sort((a, b) => b.likeCount - a.likeCount).slice(0, limit);
}

// 获取阅读量最高的十篇文章
function getTopReadArticles(articles: WechatArticle[], limit: number = 20): WechatArticle[] {
  return [...articles].sort((a, b) => b.readView - a.readView).slice(0, limit);
}

// 获取最早的十篇文章
function getEarliestArticles(articles: WechatArticle[], limit: number = 10): WechatArticle[] {
  return [...articles].sort((a, b) => a.sendTime.getTime() - b.sendTime.getTime()).slice(0, limit);
}

// 获取最新的十篇文章
function getLatestArticles(articles: WechatArticle[], limit: number = 10): WechatArticle[] {
  return [...articles].sort((a, b) => b.sendTime.getTime() - a.sendTime.getTime()).slice(0, limit);
}

// 获取高于平均阅读数的所有文章
function getAboveAverageReadArticles(articles: WechatArticle[]): WechatArticle[] {
  const averageReadCount = articles.reduce((sum, article) => sum + article.readView, 0) / articles.length;
  return articles.filter(article => article.readView > averageReadCount);
}

// 新增函数用于生成图表数据
function generateChartData(articles: WechatArticle[]) {
  // 阅读数随时间变化趋势
  const readViewTrend = articles.map(article => ({
    sendTime: article.sendTime.toISOString().slice(0, 10),
    readView: article.readView
  }));

   // 动态生成阅读量分布区间
   function generateReadViewRanges(articles: WechatArticle[]): { min: number; max: number; label: string }[] {
    const readViews = articles.map(a => a.readView);
    const minReadView = Math.min(...readViews);
    const maxReadView = Math.max(...readViews);

    // 确定基础单位（1000, 5000, 10000 等）
    let baseUnit = 1000;
    if (maxReadView > 100000) baseUnit = 10000;
    else if (maxReadView > 50000) baseUnit = 5000;

    const ranges = [];
    let currentMin = 0;
    while (currentMin < maxReadView) {
      let currentMax = currentMin + baseUnit - 1;
      if (currentMax > maxReadView) currentMax = maxReadView;

      let label = `${currentMin}-${currentMax}`;
      if (currentMin === 0) label = `0-${currentMax}`;
      if (currentMax === maxReadView) label = `${currentMin}+`;

      ranges.push({ min: currentMin, max: currentMax, label });
      currentMin = currentMax + 1;

      // 动态调整基础单位
      if (currentMin >= baseUnit * 10) baseUnit *= 2;
    }

    return ranges;
  }

  const readViewRanges = generateReadViewRanges(articles);

  const readViewDistribution = articles.reduce((acc, article) => {
    const range = readViewRanges.find(r => article.readView >= r.min && article.readView <= r.max);
    if (range) {
      acc[range.label] = (acc[range.label] || 0) + 1;
    }
    return acc;
  }, {} as Record<string number="">);

  // 阅读数与点赞数关系
  const readLikeScatter = articles.map(article => ({
    readView: article.readView,
    likeCount: article.likeCount
  }));

  // 月度统计
  const monthlyStats = articles.reduce((acc, article) => {
    const month = new Date(article.sendTime).toISOString().slice(0, 7);
    if (!acc[month]) {
      acc[month] = { readView: 0, likeCount: 0, count: 0 };
    }
    acc[month].readView += article.readView;
    acc[month].likeCount += article.likeCount;
    acc[month].count++;
    return acc;
  }, {} as Record<string readview:="" number="" likecount:="" count:="">);

  const monthlyStatsArray = Object.entries(monthlyStats).map(([month, stats]) => ({
    month,
    avgReadView: Math.round(stats.readView / stats.count),
    avgLikeCount: Number((stats.likeCount / stats.count).toFixed(1)),
    articleCount: stats.count
  }));

  return {
    readViewTrend,
    readViewDistribution: Object.entries(readViewDistribution).map(([label, count]) => ({ label, count })),

    readLikeScatter,
    monthlyStats: monthlyStatsArray
  };
}

// API函数
async function analyzeWechatAccount(userName: string) {
  try {
    const articles = await fetchData(userName);
    const processedArticles = preprocessData(articles);

    const stats = calculateStats(processedArticles);
    const viralArticles = analyzeViralArticles(processedArticles);
    // const surgeArticles = analyzeReadViewGrowth(processedArticles);

    const topLikedArticles = getTopLikedArticles(processedArticles);
    const topReadArticles = getTopReadArticles(processedArticles);
    const earliestArticles = getEarliestArticles(processedArticles);
    const latestArticles = getLatestArticles(processedArticles);
    const aboveAverageReadArticles = getAboveAverageReadArticles(processedArticles);

     // 生成图表数据
     const chartData = generateChartData(processedArticles);

    return {
      status: 'success',
      data: {
        stats,
        viralArticles: viralArticles.map(article => ({
          title: article.title,
          readView: article.readView,
          likeCount: article.likeCount,
          sendTime: article.sendTime,
          url: article.url
        })),
        topLikedArticles: topLikedArticles.map(article => ({
          title: article.title,
          readView: article.readView,
          likeCount: article.likeCount,
          sendTime: article.sendTime,
          url: article.url
        })),
        topReadArticles: topReadArticles.map(article => ({
          title: article.title,
          likeCount: article.likeCount,
          readView: article.readView,
          sendTime: article.sendTime,
          url: article.url
        })),
        earliestArticles: earliestArticles.map(article => ({
          title: article.title,
          readView: article.readView,
          likeCount: article.likeCount,
          sendTime: article.sendTime,
          url: article.url
        })),
        latestArticles: latestArticles.map(article => ({
          title: article.title,
          readView: article.readView,
          likeCount: article.likeCount,
          sendTime: article.sendTime,
          url: article.url
        })),
        aboveAverageReadArticles: aboveAverageReadArticles.map(article => ({
          title: article.title,
          readView: article.readView,
          likeCount: article.likeCount,
          sendTime: article.sendTime,
          url: article.url
        })),
        allArticles: articles.map(article => ({
          title: article.title,
          readView: article.readView,
          likeCount: article.likeCount,
          sendTime: article.sendTime,
          url: article.url
        })),
        chartData
      }
    };
  } catch (error) {
    return {
      status: 'error',
      message: error instanceof Error ? error.message : '发生未知错误'
    };
  }
}

async function getActiveWechatAccounts(): Promise<array nickname:="" string="" null="" username:="" createtime:="" date="" fetchtime:="">> {
  const conn = await getDbConnection();
  try {
    const query = `
      SELECT nickname, username, create_time, fetch_time
      FROM wechat_keyword

      ORDER BY create_time DESC
    `;
    const [rows] = await conn.execute<rowdatapacket>(query);

    return rows.map(row => ({
      nickname: row.nickname,
      username: row.username,
      createTime: new Date(row.create_time),
      fetchTime: row.fetch_time ? new Date(row.fetch_time) : null
    }));
  } finally {
    await conn.end();
  }
}

// 导出函数
export {
  getWechatArticlesByUsername,
  analyzeWechatAccount,
  getActiveWechatAccounts
};</rowdatapacket></array></string></string></mysql.rowdatapacket></wechatarticle></rowdatapacket> 
```

正如亦仁所言，现在正是开始行动的最佳时机。希望这份数据分析能为大家提供一些有价值的参考，帮助对AI自媒体感兴趣的圈友。