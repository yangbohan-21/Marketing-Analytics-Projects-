# 南加州大学（USC）校长社交媒体策略分析 ✌️✌️
<div align="right">
  <a href="./README.md">English</a> | <strong>简体中文</strong>
</div>



## 👥 项目团队 (Project Team)

*M.S. in Marketing Analytics, University of Southern California (USC)*

* **[Bohan]**
* **[Wenkai]**
* **[Haoxing]**
* **[Chenyi]**
      
## 1. 项目概述 
本项目旨在为新上任的南加州大学（USC）校长制定一项具有前瞻性的社交媒体战略。通过对前任校长过去六年间的 Instagram 发文数据进行深度的量化分析，本项目揭示了多元化校园社群潜在的互动偏好与行为模式。

基于分析，新任校长必须摒弃缺乏新意的“公关套话”与死板的发布时间表，在利用“重大宣布”类内容扩大影响力的同时，通过契合学年节奏的幕后真实互动，建立一个真实且高度参与的特洛伊（Trojan）社群。

## 2. 项目结构 
Notebook 结构与分析方法 (Notebook Structure & Methodology)
本分析 Notebook 分为五个核心的数据处理与分析模块：

### 2.1 数据清洗与预处理 (Data Cleaning & Preprocessing)

识别并删除了完全为空的列。

系统性地处理缺失值（例如：将分类字段的缺失值填充为“Unknown”，将数值型指标的缺失值填充为 0）。

将 Publish time（发布时间）列标准化为 datetime 对象，以便进行时间序列分析。

检测并移除重复记录，以确保数据完整性。

### 2.2 探索性数据分析 (EDA)

为核心互动指标（点赞、评论、分享、收藏、浏览量、触达量、新增粉丝数）生成描述性统计数据。

使用直方图（结合 KDE 核密度估计）和箱线图将数据分布情况可视化。

识别出严重的右偏态分布与显著的异常值，这表明了一种“长尾”互动模式，即极少数的“爆款”帖子贡献了绝大多数的互动量。

### 2.3 自然语言处理 (NLP) 与情感分析

应用自然语言处理技术 (NLTK) 对帖子文案进行预处理（包括分词、转小写、去除停用词和词形还原）。

使用 VADER 词典进行情感分析，计算复合情感得分。

提取出现频率最高的前 15 个词汇，并使用柱状图和定制词云进行可视化。

###2.4 时间序列互动分析 (Temporal Engagement Analysis)

从发布时间戳中提取更细粒度的时间维度（一天中的小时、一周中的星期、月份）。

绘制折线图以追踪不同时间与季节的平均互动量波动。

调整后的基准线分析： 通过筛选出第 20 至第 80 百分位的典型帖子，过滤掉极端异常值。这揭示了不受重大“爆款”宣布内容扭曲的真实潜在互动节奏。

### 2.5 内容类型表现 (Content-Type Performance)

根据 content_type（内容类型，如：重大宣布、活动与事件、官方交际等）进行分组，汇总并计算平均互动指标。

使用对比柱状图来评估哪些特定的内容策略带来了最高的浏览量、触达量、新增粉丝数及核心互动量。

## 3. 核心洞察 (Key Findings)
通过对六年社交媒体互动数据的深度挖掘，我们得出了以下几个反直觉且极具指导意义的核心洞察：

### 3.1 极端长尾效应与“官腔”陷阱 (The Long-Tail & PR Jargon Trap)
数据呈现出严重的右偏态分布，这意味着绝大多数日常帖子的互动率极低。虽然词频分析显示“great”、“happy”和“student”等词汇频繁出现，但这仅仅反映了前任校长的输出习惯，而非受众真实的互动偏好。过度依赖这种绝对安全但缺乏情感共鸣的“公关套话（PR jargon）”，导致了账号日常互动的平庸，且未能建立起鲜明的个人品牌（IP）。
<img width="1024" height="683" alt="image" src="https://github.com/user-attachments/assets/f70af2b6-73bf-4b01-95dc-4bdde99fecff" />
<img width="1024" height="683" alt="image" src="https://github.com/user-attachments/assets/ab10d425-4e12-4522-97b7-9a35fb22f4e3" />

### 3.2 “重大宣布”的光环效应 (The "Announcement" Halo Effect)
交叉分析表明，“重大宣布（Announcement）”类内容在点赞、评论、分享、特别是“收藏（Saves）”和“触达量（Reach）”上占据压倒性优势。这证明受众将校长账号视为获取权威信息的“最终真实来源”。新任校长应大力利用这一优势，将其作为扩大影响力和增加粉丝的核心驱动力。
<img width="1782" height="1226" alt="image" src="https://github.com/user-attachments/assets/cc1cc7c5-3709-44bc-beb3-f4eacc5034f8" />
<img width="1770" height="574" alt="image" src="https://github.com/user-attachments/assets/ae60927b-bc39-4fe7-8e2b-add20c498971" />

### 3.3 时间互动趋势：“反工作日”与学年周期 (Temporal Engagement Trends)
为了分离出受众注意力的真实节奏，我们对数据集进行了筛选，仅保留“典型”帖子（即第 20 至第 80 百分位的数据），从而有效剔除了极少数爆款宣布内容带来的极端偏态干扰。调整后的时间序列分析证实了强烈的“反工作日”行为模式。真实的基准互动量在周末（周六/周日）持续爆发，并在晚间达到峰值（特别是在晚上 7:00 和 11:00 左右）。此外，在排除了诸如 5 月毕业典礼等大型一次性事件的数据扭曲后，筛选后的数据揭示出，典型的日常互动实际上在初夏（6 月）以及秋季学期的核心阶段（9 月至 11 月）达到顶峰。这证明，传统的“朝九晚五”企业化发布时间表完全错失了校园社群自然活跃的时间窗口。
<img width="1768" height="814" alt="image" src="https://github.com/user-attachments/assets/99eb5234-2240-4778-84c4-92d2e7fdbaab" />
<img width="1778" height="834" alt="image" src="https://github.com/user-attachments/assets/3cf92756-0170-41bd-a86b-cb63c43e46b9" />

## 3.4 从“官方交际”向“真实共情”转型 (Pivot from "Networking" to "Authentic Relatability")
传统的“官方交际（Networking）”会晤照片在互动量上绝对垫底。数据强烈建议新任校长放弃单向的官方播报，转而拥抱基于真实细节的“幕后视角”。强烈建议通过提问和互动功能，与核心受众（尤其是学生）开启双向对话。

### 4. 数据结构 (Data Schema)
Data Availability Statement:
数据可用性声明：
出于数据隐私与合规性考量，本仓库不包含原始的社交媒体数据集。

| Column Name | Data Type | Description | Example |
| :--- | :--- | :--- | :--- |
| `Post ID` | string | Unique identifier for the post | `17912345666` |
| `Account ID` | string | Unique identifier for the account | `12345678` |
| `Account username` | string | System username of the account | `uscpresident` |
| `Account name` | string | Display name of the account | `USC President` |
| `Description` | string | Text content/caption of the post | `"Welcome class of 2027! ✌️"` |
| `Duration (sec)` | float | Video duration (usually 0 or blank for images/carousels) | `15.5` |
| `Publish time` | datetime | Exact publishing timestamp | `2023-08-15 10:30:00` |
| `Permalink` | string | Permanent URL of the post | `https://instagram.com/p/xxx/` |
| `Post type` | string | Media format (e.g., Image, Video, Carousel) | `Image` |
| `Data comment` | string | Additional notes from the data source (often blank) | `NaN` |
| `Date` | date | Extracted publishing date | `2023-08-15` |
| `Views` | integer | Total number of views/plays | `25400` |
| `Reach` | integer | Number of unique accounts reached | `18900` |
| `Likes` | integer | Total likes | `1250` |
| `Shares` | integer | Total shares/forwards | `120` |
| `Follows` | integer | New followers gained directly from the post | `15` |
| `Comments` | integer | Total comments | `45` |
| `Saves` | integer | Total saves (specific to Instagram) | `30` |
| `content_type` | category | **[Manually Tagged]** The core theme/category of the post | `Announcement` |
