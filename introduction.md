## GAIblog, update constantly :)  
> **讨论了游戏AI顶会论文归纳与分类，算法及其应用探讨**  
  
中文版，GAMEAI学习paper清单推荐和记录,不断更新，欢迎交流,请查看wiki页面~  
Some Recommanded and Marked paper for GAMEAI learning, The details are listed in wiki page  
:point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down:
<h1><a href="https://github.com/ls361664056/GameAI-paper-list/wiki">请诸位老爷移步Wiki 页面(Wiki Page) 欢迎补充</a></h1>  
:point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2::point_up_2:  
 
因为国内并没有发现公众号或是学校专门讲通用游戏算法这一块，笔者结合了自己的爱好建立了这个repo  

# 游戏领域的AI应用  
AI作为时下计算机算法的超级巨星，在例如CV、NLP、语音、机器人等诸多领域都有广泛的应用。 而在游戏领域，AI的应用往往被认为是类人玩家型AI，算法的第一印象也通常是强化学习。但实际当中，AI在游戏中的应用却不止于此。本文就来介绍一下游戏领域的AI应用与算法。  
  
首先摆在我们面前的是，**为什么要研究游戏AI呢？**  
> 游戏可以看做是对于现实问题的折射，研究游戏AI对我们解决现实中的问题可以提供有价值的样本。
> 此外，因为游戏领域的多样性，多种形式的AI方法可以分别或结合在不同的游戏中。
> 最后，和大部分其他领域的AI问题相比，游戏AI很有趣不是吗 :P  
  
引用Georgios N.Yannakakis and Julian Togelius **《Artificial Intelligence and Games》** 中的话  
> 自AI的想法诞生以来，游戏一直为AI的研究过程提供助力。游戏不仅提出有趣且复杂的问题来供AI解决————例如去精通一个游戏；它们也为（人类，甚至机器）用户能够体验到的创意以及表达提供了一个画布。因此可以说，游戏是罕见的，是科学（解决问题）与艺术相碰撞并相互作用的领域，而这些因素也让游戏对于AI的研究来说成为一个独特并且优秀的环境。然而不仅是AI在游戏中提升，游戏也在AI研究中得到了发展。
  
在游戏领域中，AI的应用其实并不仅仅是人们印象中的玩家型战斗AI。传统意义上的游戏制作融入了AI的方法之后在各个环节都催生了相应的应用与算法。如果我们将一款游戏拆开来看他的各个环节，这些AI的应用就变得直观起来。  
* **游戏画面生成**
在游戏制作的环节里，开发者需要制作相应角色的动画模型，来满足使用者在游戏内视觉上的需求，在传统的游戏制作上，通常需要一名专门游戏原画师来制作相应的内容，但是聚焦到游戏内角色们的表情与动作这些细节上时，动画的设计通常变得吃力不讨好起来，应用视觉AI可以将人们的动作投影到角色身上，生成相应的动作表情；而在环境的设计中，AI也可以起到相似的效果，通过输入现实的图片来得到相应的游戏画面。在这个问题上，CV中的机器学习方法例如**姿态识别，表情识别，GAN**等起到了关键性的作用  
<p align="center">
  <img src="image/1.gif" alt="animated" />
</p> 
<center><i>动作识别</i></center> 
<br/><br/>  

<p align="center">
  <img src="image/2.jpg" alt="animated" />
</p> 
<center><i>表情识别</i></center>  
<br/><br/>  

* **玩家型AI**
该类型应该是最被大众所熟知的游戏AI类型，2017年AlphaGo击败世界围棋冠军李世石，2019年OpenAI Five击败DOTA2世界冠军OG证明了AI在游戏上的表现可以超越人类。而此类AI问题本质上可以看成是路径规划问题，即根据当前的游戏状态生成相应的动作序列。典型的以**强化学习、深度强化学习**为代表的游戏AI目前在国内的游戏工业界已被大量研究，在某些游戏类型例如棋牌类、回合制策略游戏中，**蒙特卡洛搜索树（行为树）、演化算法、A***等在线学习算法也具有一定优势。  
<p align="center">
  <img src="image/OpenAI-Five-Dota-2.png" alt="animated" />
</p> 
<center><i>深度强化学习</i></center>  
<br/><br/>  
  
<p align="center">
  <img src="image/3.jpeg" alt="animated" />
</p> 
<center><i>基于蒙特卡洛搜索树的深度强化学习</i></center>  
<br/><br/>  

<p align="center">
  <img src="image/7.jpg" alt="animated" />
</p> 
<center><i>演化算法</i></center>  
<br/><br/>  

<p align="center">
  <img src="image/4_2.gif" alt="animated" />
</p> 
<center><i>A*</i></center>  
<br/><br/>  


  
* **游戏内容生成**  
  在这一方面的AI应用常常不为人所知，通常被称为Procedural Content Generation(PCG)。在游戏内容（地图）的产出上，以魔兽争霸3为例，一方面依赖于游戏本体制作时开发者制作的地图；另一方面依赖于社区玩家的自定义地图，而社区玩家内容又更是由玩家数量所决定，丰富且可行的游戏内容是吸引玩家入坑的重要保障。利用AI去生成可行的游戏内容是非常值得研究的方向。目前该方向的主流算法包括**演化算法、GAN等**。  
![AI generator](image/5.jpg)
<center><i>AI generator</i></center>  
<br/><br/>  
  
<p align="center">
  <img src="image/6.jpg" alt="animated" />
</p> 
<center><i>GAN</i></center>  
<br/><br/>  
  
* **游戏初始化平衡AI**
  目前在卡牌类游戏中，为了初始化得到的卡牌或是环境相对平衡，在PVE游戏中体现为玩家可以战胜Bot，PVP游戏例如炉石传说、自走棋，防止出现双方卡牌差距过大导致输掉，可以利用AI来设计发牌的策略。该方向的主要算法为**演化算法**。  
  <p align="center">
  <img src="image/R-C.png" alt="animated" />
</p> 
<center><i>炉石中的演化算法平衡牌组</i></center>  
<br/><br/>  
  
* **游戏测试**
  在游戏制作完成后，开发者们需要测试游戏内存在的bug，这毫无疑问是重要的，如果一款游戏存在大量的bug，对该游戏的评价和收益都会造成巨大的影响。而测试游戏需要大量的时间，在这一方面，测试专用的agent可以被设计来面对这一挑战，目前这一块的算法主要为**蒙特卡洛搜索树、强化学习、深度强化学习**等。
<p align="center">
  <img src="image/9.png" alt="animated" />
</p> 
<center><i>深度强化学习自动测试agent</i></center>  
<br/><br/>  
  
* **用户画像**
  在游戏的运营过程中，玩家在游戏内的行为会产生丰富且复杂的数据，这些数据内折射了玩家的行为，分析并合理利用这些数据可以提炼出有价值的信息，这些信息可以用作促进游戏更新更多玩家喜欢的内容，预测玩家的行为和喜好，检测作弊外挂等。这一种游戏中的数据分析问题被称为用户画像问题，利用合理的**机器学习**算法可以极大提升玩家的游戏体验。  
<p align="center">
  <img src="image/Blog-Detail.png" alt="animated" />
</p> 
<center><i>用户画像分析</i></center>  
<br/><br/>  

---  

# 更详细的分类如下  
## 利用AI玩游戏（agent/bot）  
> 在游戏中建立bot。
### 应用为导向  
+ 与玩家对抗/协作
    > 依据数据和预算产生不同水平的agent，可以**与玩家共同匹配**或**作为PVE的NPC等**提高玩家体验水平。 
+ 游戏bug测试  
     > 在投入运行前，可以通过投入大量的有测试行为的agent进入游戏，根据其行动期间的log异常来**得到一些bug**，或是通过bot间的对战，依据一定的判定方法来**得到版本数值平衡性分析**。
+ 合成数据收集 
     > 在游戏投入运行得到一定的玩家数据前，可以**使用agent的行动来得到仿真的玩家数据**，例如阵型识别，胜率预测等数据。  
+ 产生更强力的agent  
     > 根据**共同演化**的方法，一系列基础的agent可以通过参数演化或者agent间对抗性的方法来**催生性能更好的agent**。  
### 方法为导向  
> 根据是否使用了游戏提供的仿真模型（即可根据目前的游戏状态 $\phi(t)$ 以及可执行动作 $a\in \Alpha$ 得到后续的帧的游戏状态 $\phi(t+1)$）可以将其分为Model-based与Model-free的agent。
+ Model Based（基于模型的agent）  
    + 最佳优先搜索（例如$A^*$）
    + 蒙特卡洛树搜索（Monte Carlo Tree Search,MCTS）  
    + 滚动地平线进化算法（Rolling Horizon Evolutionary Algorithms,RHEA）  
+ Model Free (无模型方法)  
  + 静态类方法  
     > + 状态机  
     > + 行为树
     > + 基于效用（启发式）函数的AI方法  
  + 学习类方法  
    >+ 强化学习（Reinforcement Learning,RL, 不适用于3D大型游戏，需要高度表格化表示）。
    >+ 深度强化学习（Deep Reinforcement Learning,DRL,  基于游戏图像，不需要标记数据，但需要有游戏实时的奖励设置）。 
    >+ 模仿学习（Imitation Learning,IL, 根据玩家的数据来学习游戏的策略，基于游戏图像，需要玩家数据）。
## 利用AI生成游戏内容(Procedural content generation,PCG)  
> 利用AI的方法去协助设计游戏系统，前置要求是**需要比较好的数据**（包括数据的质量，数据的代表方式，数据的数量）和**有代表性的评估方法**（包括美学，可玩性，新奇性）。具体的应用方法需要进一步查阅资料。  
### 应用为导向  
+ (辅助)生成游戏中的内容（影响规则）  
    > 关卡、地图、物品、武器、任务、人物、规则、音乐等。  
+ (辅助)生成游戏中的外观（不影响规则）  
    > 人物外观，表情，武器外观，音效等。  
+ 修复地图bug  
    > 对无法抵达的死角做检测与替换等。  
+ 数据压缩  
    > 将游戏数据压缩到更小的尺寸。  

### 方法为导向  
+ 机器学习方法(Procedural content generation via Machine Learning,PCGML)  
  + 神经网络
    + GAN  
    + AutoEncoder  
    + NeuroEvolution   
  + 概率模型  
  + 决策树  
  + Others  
+  基于搜索方法（通常为Evolutionary Algorithms,EA）  
    > 相较于机器学习的方法，搜索方法可以大大减少所需求的数据量。   
+  基于文法方法  
    > 定义一系列文法规则来生成内容。  
+ 元胞自动机  
    > 使用领域规则根据随机初始状态生成大量不规则图形，可用于热量、雨水、液体流动、压力爆炸等环境系统建模，也可以生成洞窟等小型地图，但**无法保证可控性**。  
## 利用AI为玩家建模(player modeling)  
> 利用游戏产生的数据来为玩家建立模型（包括其消费预测，游戏性行为预测，体验感预测）或是进一步利用该数据来更新与描述游戏（例如平衡性分析，游戏流派，提供给Agent更多的训练数据）  
### 应用为导向  
+ 理解玩家在游戏中的体验
    > + 可以根据玩家的体验感来**评测游戏各个组件与系统**;  
    > + 辅助更新新的游戏活动;  
    > + 辅助更新前两个AI系统。  
+ 理解玩家在游戏中的行为  
    > + 辅助分析游戏行为，例如发掘一些新的游戏玩法；
    > + 可以根据异常数据来判定**外挂**等作弊系统；
    > + 形成可观的游戏数据来支持新的游戏**AI迭代**；
    > + 辅助设计更具有公平性的**匹配系统**;
    > + **预测**玩家的行为。  
### 方法为导向  
+ 监督学习  
  > + 回归  
  > + 分类  
  > + 偏好学习
+ 强化学习  
  > + 模仿学习  
  > + 逆强化学习  
+ 无监督学习 
  > + 聚类  
  > + 频繁模式挖掘  

  
真心的期待更多的伙伴一起加入这个有意思的AI研究领域，探索更多的AI玩法。

