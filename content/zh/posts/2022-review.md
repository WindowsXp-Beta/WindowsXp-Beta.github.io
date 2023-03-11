---
title: "再见2022 & 你好，22"
date: 2023-01-17T20:49:57+08:00
draft: False
toc: true
---

> 本来标题是再见2022，然后跨年的时候发，结果那几天录video essay & 对着~~csranking查faculty主页~~chatGPT写why school写到自闭然后啥事也不想干，过了跨年之后更没动力了，而且网申也没交完 & 调[penglai](https://github.com/Penglai-Enclave/Penglai-Enclave-sPMP) & 毕设开题……
>
> 终于赶在22岁之前把这些事都搞定了，于是拿起~~笔~~键盘，回忆一下2022 & 我的 21。

## prologue
2022的开头非常凄凉，由于大三上一系列作死的操作导致成绩出来之后我的ranking直接double了，但当时似乎也没有特别难过（心真大……）

回家之后开始找实习 & 准备寒假之后的GRE，意识到在家里这种低效的环境下这两件事是都做不好的。

于是大概初七就回了学校开始刷leetcode & 背单词。单词背着背着因为苏州疫情把我的GRE取消了，于是转到了4月份的上海（也彻底不学英语了）。之后开始一轮轮面试，详见[22暑期实习](../22暑期实习)。最后决定先去[RisingWave Labs]((https://www.risingwave.com/))(pre-S社)做日常，然后暑假看情况去MS还是Bytedance还是留S社。于是开启了每周一三五赶一个半小时 * 2的地铁去上海广场实习的生活。

## lockdown
本以为这学期都要这样了，于是下了好多书打算在地铁上看，结果刚去了一周，在一个周三醒来的早上（3.9），早八归来的室友说上网课了。当时没有人知道，下一次出校门竟然是6.20。
年终总结就不写那些消极的东西了，而且我觉得疫情对我的影响不大，因为本来也没空去浪。但整个大环境人心惶惶而且还要和室友match作息还是有点影响。

摸了很多鱼
1. 给设备升了个级🐶。
    <img src="https://s1.ax1x.com/2023/01/18/pS3B5nS.jpg" style="zoom:50%;display: block;margin-left: auto;margin-right: auto;">
2. 超市开始抢号了之后和室友写了个[脚本](https://github.com/Vladimirovich2019/COVID-2022)，部署在交大云上（ping预约的服务器只要1ms），多线程并发请求😎😎😎
    <details>
        <summary>结果</summary>
        一次都没抢到🤡，所以那个link你们应该打不开，实在不好意思open-source
    </details>
3. 投诉最爆炸那会儿在柠檬体验了几天站内管理员，发现想要维护一个论坛是真难呀，各种各样奇怪的举报和投诉，然后你删评 & 下架又会得罪新的人。respect to所有站内的同学。
4. 追完了勇士的整个季后赛。“这一冠，再无遗憾。”

写了一点代码
1. OS课终于见识到了传说中的[chcore](https://gitee.com/ipads-lab/chcore-lab-v2)，非常好的lab，强烈安利。
2. 云计算课在队长cyx和队友gzd的强力carry下撸了一个[k8s](https://github.com/Kuberboat)。
3. 在S社学Rust & 写issue。可惜由于封校一直remote，错过了所有的happy hour😭😭😭。但还是收到了端午礼包🥰🥰🥰
   <img src="https://s1.ax1x.com/2023/01/18/pS3Bbhn.jpg" style="zoom:15%;display:block;margin-left:auto;margin-right:auto;">

然后就上完了最后一节专业课，考完了最后一场试。

## Summer
> 和一些学长聊了聊并且去地里[问了问](https://www.1point3acres.com/bbs/thread-858280-1-1.html)之后还是决定投入big name的怀抱。于是在finish了S社的最后一个task之后入职了离我寝室直线距离不到1.7km的Microsoft。

暑假主要干了三件事，打德扑，背单词，实习（sort by priority🐶）。

### 德扑
在大公司实习有个好处在于有很多intern。在MS我就认识了很多非常厉害的同学（我就不把你们的linkedin都贴一遍了😂），和找工作的同学聊了聊真切感受到了寒意逼人，也认识了几个23fall的同学。我也~~尽地主之谊带着他们游览魔都~~发现自己只对交大周围那一圈熟悉🥲🥲🥲。这里德扑是个泛指，因为我们周五下班后的主要娱乐活动之一就是打德扑（my favorite），其他的还有诸如恰饭，唱歌，桌游之类的传统艺能。

### 背单词
GRE这个考试毫无用处，V所需的单词佶屈聱牙，根本就不是日常生活中会用的，Q的数学题只有初中难度，主要考察是否能读懂题目。作文更是离谱，我考前看了两节网课一篇没练，拿着两年没写英语作文的水平也有4.0。详见[GT分手日记](../gt分手日记/#gre)

因此我大部分的备考时间都在挣扎这种东西
```
轻视，蔑视，鄙视，嘲笑:
slight, disparage, defiant/defy, discount, flout, disregard, disdain, opprobrium, scorn, deride/derision, mockery, ridicule, contempt, debase(贬低), slur, aspersion
批评:
lambaste, rant, polemic(猛烈抨击), admonish, animadversion, castigate, chastise, denounce, opprobrium, censure, condemn, decry, impugn, invective, indict(控告), deprecate, detract, admonish, diatribe
```
而GRE考试就是个心酸的故事了。我从2月的苏州，4月的上海，7月的上海，8月的苏州一路被奥密克戎精准狙击，最后发现满老师在公司考~~这招不错~~被坑惨了，于是报了8.23的家考。结果那天选的会议室的灯在检测不到人的活动后会自动熄灭，于是我每隔一段时间就得拖拖椅子表明我的存活。。。还断了一次网。。。

考完喜提“再来一次”。

### MS
MS的暑期实习是开盲盒，HR对着（我觉得也不一定对着）你的简历把你分配到某个组。于是乎我看着其他同学写Rust，写distributed file system，hack linux kernel，写Spark同时，写了一个暑假.NET后端，顺便复习了一下MVC😇😇😇
> 以后绝对不当CRUD boy，就算搞infra没钱途也要搞infra。

### MISC
1. 7月份做了件非常有意思的事情，当了回bestman😎😎
   <img src="https://s1.ax1x.com/2023/01/18/pS3BHts.jpg" style="zoom:30%;display:block;margin-left:auto;margin-right:auto;">
2. 报名了[GAU](https://mp.weixin.qq.com/s/UFYKMDS784P8B6hOYAznpg)，结果第一志愿和第二志愿都把我desk reject😭，还好孟仔大大捞了我。

## 申请季

### GRE
第一次GRE挂了之后约了江苏南通的线下考，从微软离职后过去刚好。事情自然不会这么一帆风顺，先是南通考点要求7天行程码无省外，于是只能跟mentor & manager说提前离职，去南通住一周。再是学校开学第一天就混检阳然后封校了，经历了上半年lockdown已经PTSD的我肯定不敢回学校，于是更提前了离职，连夜跑路。
   <img src="https://s1.ax1x.com/2023/01/18/pS3B7kj.png" style="zoom:50%;display:block;margin-left:auto;margin-right:auto;">

仓皇的后果是在高铁上丢了身份证，问了问考点说临时身份证可以用，于是第二天台风天我妈开车带我回了闵行补办了身份证🤡🤡🤡。晚上做高铁去了南通，祈祷七天之后我的行程码上只有江苏的轨迹。

顺便远程签了放弃推免。
   <img src="https://s1.ax1x.com/2023/01/18/pS3BhX8.jpg" style="zoom:30%;display:block;margin-left:auto;margin-right:auto;">
> 现在想来要读PhD的话留在ipads绝对是最优解，稳定的产出，熟悉的环境，非常好的老师，其实大概5月份的时候斌哥还问我要不要去THU读博，看了看那个老师的主页发现发顶会发得也很猛。纠结了一番之后还是不想读博，详见[~~Why not a Ph.D.~~](../why-not-phd)（还没写完）。而如果是硕士的话国内读硕士的时间成本太高了，在微软和一些秋招的同学聊，也愈发认识到学历只是一个门槛，如果你有更能证明你实力的东西，比如open-source，顶会论文，solid的项目等等，它们往往比一纸文凭更有用，而除了顶会论文，我觉得其他两者不需要读master，甚至读master还会占用你的时间。

在南通的全季待了七天，背单词之余远程指导ws学弟把NFC给跑通了，顺带水了5k的结题报告，终于和PRP说再见了。9.23上考场，V158+Q170+AW4.0顺利杀G（能申Yale了，开心开心）。考完发现微软的小伙伴们组织恰饭，于是从南通回了上海。
   <img src="https://s1.ax1x.com/2023/01/18/pS3BI0g.jpg" style="zoom:50%;display:block;margin-left:auto;margin-right:auto;">

### TOEFL
学校还封着，于是直接回家，然后开始准备TOEFL。期间乏善可陈，详见[GT分手日记](../gt分手日记)。
- 报了一场家考，结果只准备了一个周末，直接白给。
- 苏州的线下又被取消（和这座城市是无缘了。。。）
- 发现江西南昌不用7天省内，于是报了10.29的。

110(R30+L29+S23+W28)卡线分手，开心开心。

### Research
> 我也是个做过research的人了🐶

暑假的时候tiger老师组织了一个分享会，邀请了一些软院在北美的学长学姐分享他们的成功人生。
> 在Google的SDE们普遍对形式还挺乐观的，反复跟我们说相信自己，交大的同学肯定是找得到工作的。虽然他们>5年前就去并且都有卡了。。。

然后暑假快结束的时候，我在苦思冥想找谁写推荐信，想着能不能要到一封海外的信。想着要不套个~~暑~~秋冬研，翻开csranking刷faculty列表直接自闭，算了算了我也不申PhD。突然想到分享会上好像有位NEU的ap，于是微信上connect了一下，约了个面试，确定跟他，[Prof. Tan](https://www.khoury.northeastern.edu/people/cheng-tan/)，做一段research。

这段research做得非常愉快，老师非常supportive，我们每周都sync，讨论一下进度，遇到的问题然后规划一下接下来干什么。有了清晰的任务后，即使和写文书，TOEFL并行，我也可以安排时间，同时推进这三个工作。其次skillset比较熟悉，python写起来非常舒适，Kubernetes之前也搞过。

运气也还不错，中间碰到的各种奇奇怪怪的问题最后都解决了，也跌跌撞撞的赶上了OSDI'23。所以这段工作不仅给我带来了一封RL，还有一篇顶会的submission，开心开心。

### 申请
> 选校的考量，咋写SoP，怎么要RL等等详见[~~23fall美国MSCS申请纪实~~](../23fall-application)(WIP)

尘埃落定后的bg：
```
GPA: 91+/100 or 3.96/4.30, 几个算法里最好看的ranking 3/97。
T: 110(S23) G: 328+4.0。
实习：4个月数据库startup，3个月Microsoft
科研：一段校内PRP，一段NEU。一篇OSDI一作在投。
```
> PS: 由于我系 & CS, i3e, AI 给分的disparity，这个GPA整个sjtu 23fall EECS来看的话应该进不了前十。。。

文书

SoP重写了好多遍 & GAU的组内互改被怼了好几轮，又找了好多人帮我看。最后总算梳理出一条还算make sense的逻辑。
   <img src="https://s1.ax1x.com/2023/01/18/pS3Bo7Q.png" style="zoom:100%;display:block;margin-left:auto;margin-right:auto;">
thanks to all of you sincerely

选校

选校一时爽，文书火葬场。。。
最后基本能申的都申了。。。申请费 + 送分交了快2W。。。

彩票：CMU MSCS/MCDS; Cornell Ithaca/Tech CS Meng; UPenn MCIS; UT-Austin ECE; Yale MSCS;（HMPYS剩下的省申请费吃海底捞）

主申：CMU MSIN/MITS/SE-SV; Berkeley EECS; UCSD CS75; Columbia MSCS; Gatech MSCS; UMich MSCSE; UIUC MCS; Brown Sc.M.

（看今年的情况不一定）保（得住的）底：USC CS28; UW-Madison PMP; UCSD EC79;

## epilogue
整个2022的核心应该就是申请了吧。扪心自问，我觉得我best effort了，毕竟最后那一页纸CV上的大部分内容，都发生在2022。

我觉得这是我第一次选择自己的人生，选择到底想成为什么样的人，想过什么样的生活。所以我觉得申请本身也是有意义的，一如地里的这段话
>“我是谁”，“我做了什么”，“我要做什么”这几个问题早晚都是要想清楚的。当你深夜孤灯思考人生，回顾大学3年自己的奋斗，热血与梦想，总结自己一路走来的得失，然后将点滴生活与思考用逻辑串联，这可能会让你自己都热泪盈眶，同时收获成长。悟已往之不谏，知来者之可追。

2023有超多想做的事，不求好运降临，只希望一切顺遂。