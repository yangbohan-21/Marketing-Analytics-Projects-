# Marketing Analytics Projects

### 1. Project Overview
    This project aims to develop a forward-looking social media strategy for the newly appointed President of the University of Southern California (USC). By conducting a deep quantitative analysis of the former president's Instagram post data spanning the last six years, this project uncovers the underlying engagement preferences and behavioral patterns of the diverse campus community.
   In conclusion, the new president must abandon generic PR jargon and rigid schedules, leveraging 'Announcements' for reach while building an authentic, highly engaged Trojan community through behind-the-scenes interactions timed with the academic rhythm

### 2.Structure
    
    ## Notebook Structure & Methodology

This analytical notebook is structured into five core data processing and analytical modules:

**2.1 Data Cleaning & Preprocessing**
* Identified and dropped completely empty columns.
* Handled missing values systematically (e.g., imputing 'Unknown' for categorical fields and `0` for missing numerical metrics).
* Standardized the `Publish time` column into datetime objects for temporal analysis.
* Detected and removed duplicated records to ensure data integrity.

**2.2 Exploratory Data Analysis (EDA)**
* Generated descriptive statistics for key engagement metrics (Likes, Comments, Shares, Saves, Views, Reach, Follows).
* Visualized data distributions using Histograms (with KDE) and Box Plots.
* Identified severe right-skewed distributions and significant outliers, indicating a "long-tail" engagement pattern where a few viral posts drive the majority of interactions.

**2.3 NLP & Sentiment Analysis**
* Applied Natural Language Processing (NLTK) to preprocess post descriptions (tokenization, lowercase conversion, stop-word removal, and lemmatization).
* Performed Sentiment Analysis using the VADER lexicon to calculate compound sentiment scores.
* Extracted and visualized the Top 15 most frequent words using Bar Charts and a customized Word Cloud.

**2.4 Temporal Engagement Analysis (Time-Series)**
* Extracted granular time dimensions (`hour_of_day`, `day_of_week`, `month`) from the publish timestamps.
* Plotted line charts to track average engagement fluctuations across different times and seasons.
* **Adjusted Baseline Analysis:** Filtered out the extreme outliers by isolating the 20th–80th percentile of typical posts. This revealed the true underlying engagement rhythm free from the distortion of major viral announcements.

**2.5 Content-Type Performance**
* Aggregated and calculated average interaction metrics grouped by `content_type` (e.g., Announcement, Events & Activities, Networking).
* Utilized comparative bar charts to evaluate which specific content strategies yielded the highest Views, Reach, Follows, and core interactions.


### 3. Key Findings

Through deep mining of six years of social media engagement data, we uncovered the following counter-intuitive and highly actionable insights

**3.1 The Long-Tail & PR Jargon Trap 
    The data exhibits a severe right-skewed distribution, meaning the vast majority of daily posts receive extremely low engagement. Although word frequency analysis shows words like "great," "happy," and "student" appearing frequently, this merely reflects the former president's output habits rather than the audience's engagement preferences. Over-reliance on this perfectly safe but emotionally flat "PR jargon" resulted in mediocre daily interactions and failed to establish a distinct personal brand (IP).
    <img width="1024" height="683" alt="image" src="https://github.com/user-attachments/assets/f70af2b6-73bf-4b01-95dc-4bdde99fecff" />
    <img width="1024" height="683" alt="image" src="https://github.com/user-attachments/assets/ab10d425-4e12-4522-97b7-9a35fb22f4e3" />

**3.2 The "Announcement" Halo Effect
    Cross-analysis reveals that "Announcement" type content holds an overwhelming advantage in Likes, Comments, Shares, and especially "Saves" and "Reach." This proves that the audience views the president's account as the "ultimate source of truth" for authoritative information. The new president should heavily leverage this advantage as the core driver for expanding reach and growing the follower base.
    <img width="1782" height="1226" alt="image" src="https://github.com/user-attachments/assets/cc1cc7c5-3709-44bc-beb3-f4eacc5034f8" />
    <img width="1770" height="574" alt="image" src="https://github.com/user-attachments/assets/ae60927b-bc39-4fe7-8e2b-add20c498971" />

**3.3 Temporal Engagement Trends ("Anti-Workday" & Academic Cycles)
    To isolate the genuine rhythm of audience attention, we filtered the dataset to include only "typical" posts (the 20th to 80th percentile), effectively stripping away the extreme skew caused by rare, viral announcements. This adjusted time-series analysis confirms a strong "anti-workday" behavior pattern. The true baseline engagement consistently booms over the weekends (Saturday/Sunday) and peaks late in the evening (specifically around 7:00 PM and 11:00 PM). Furthermore, without the statistical distortion of massive one-off events (like May commencement), the filtered data reveals that typical daily engagement actually peaks during early summer (June) and the heart of the fall semester (September through November). This proves that the traditional "9-to-5" corporate posting schedule completely misses the natural activity windows of the campus community.
<img width="1768" height="814" alt="image" src="https://github.com/user-attachments/assets/99eb5234-2240-4778-84c4-92d2e7fdbaab" />
<img width="1778" height="834" alt="image" src="https://github.com/user-attachments/assets/3cf92756-0170-41bd-a86b-cb63c43e46b9" />

**3.4 Pivot from "Networking" to "Authentic Relatability"
        Traditional "Networking" (official meeting) photos rank at the absolute bottom for engagement. The data strongly urges the new president to abandon one-way official broadcasting and instead embrace a "behind-the-scenes" perspective grounded in authentic, granular details. Opening a two-way dialogue with the core audience (especially students) through questions and interactive features is highly recommended.

        

### 4. Data Schema
Data Availability Statement:
Due to data privacy and compliance policies, the raw social media dataset is not included in this repository. However, a detailed Data Schema and a sample structure are provided in the data/ folder to demonstrate the analytical framework and allow for code replication.

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

