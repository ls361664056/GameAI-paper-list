# Introduction  
> 该repo聚焦于收集游戏领域的AI方法论文，分类归纳与总结。  
  
:point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down::point_down:
# **详情请查看[维基页面](https://github.com/ls361664056/GameAI-paper-list/wiki)**   
:point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up::point_up:
---  

# Game AI review  
> 本文参考Yannakakis, Georgios N., and Julian Togelius. 的《Artificial Intelligence and Games.》,对游戏领域的AI方法应用做个汇总
## 利用AI玩游戏（agent/bot）  
> 在游戏中建立bot。
### 应用为导向  
![application of using AI playing](./image/AIplayingapplication.png)  
<center>AI bot应用图[1].</center>  
<br/>  

+ 与玩家对抗/协作
    > 依据数据和预算产生不同水平的agent，可以**与玩家共同匹配**或**作为PVE的NPC等**提高玩家体验水平，由此引申的功能可以有**动态难度调节，游戏自动平衡**。 
+ 游戏bug测试  
     > 在投入运行前，可以通过投入大量的有测试行为的agent进入游戏，根据其行动期间的log异常来**得到一些bug**，或是通过bot间的对战，依据一定的判定方法来**得到版本数值平衡性分析**。
+ 合成数据收集 
     > 在游戏投入运行得到一定的玩家数据前，可以**使用agent的行动来得到仿真的玩家数据**，例如阵型识别，胜率预测等数据。  
+ 产生更强力的agent  
     > 根据**共同演化**的方法，一系列基础的agent可以通过参数演化或者agent间对抗性的方法来**催生性能更好的agent**。 
+ 寻路(Pathfinding)  
    >寻路规划可以被视为AI动作序列输出的一种特例。在某些游戏例如马里奥中，寻路算法本身就构成了AI player。  
### 方法为导向  
> 根据是否使用了游戏提供的仿真模型（即可根据目前的游戏状态 $\phi(t)$ 以及可执行动作 $a\in \Alpha$ 得到后续的帧的游戏状态 $\phi(t+1)$）可以将其分为Model-based与Model-free的agent。
+ Model Based（基于模型的agent）  
  +  Planning-based  
       + 最佳优先搜索（例如$A^*$） 
          ![Example of modern game using A*](./image/A_star_Examples_in_Mario.png) 
       + 蒙特卡洛树搜索（Monte Carlo Tree Search,MCTS）  
          ![Example of modern game using MCTS](./image/MCTS_Examples_in_totalwar.png) 
       + 演化规划（Evolutionary Planning）    
          ![Explaination of EA](./image/Evolutionary_Planning_Detail.png)
  + 基于模型的强化学习（Model-based reinforcement learning）
+ Model Free (无模型方法)  
  + 静态类方法  
      + 状态机  
      + 行为树
      + 基于效用（启发式）函数的AI方法 
  + planning-based  
     + STRIPS（符号化表示规划）  
  + 学习类方法  
    + 强化学习（Reinforcement Learning,RL，需要高度表格化表示）。  
         ![RL Problem](./image/Reinforcement_Learning_problem.png)
    + 深度强化学习（Deep Reinforcement Learning,DRL,  基于游戏图像，不需要标记数据，但需要有游戏实时的奖励设置）。  
         ![DRL overview](./image/DRL_development_to_2017.png)
    + 演化算法(Neuro Evolution，通过演化算法来更新神经网络结构和权重来达到最优化)。  
         ![NE as RL](./image/NeuroEvolution%20as%20a%20RL%20problem.png)  
         ![NE examples](./image/NeuroEvolution_examples.png)
    + 模仿学习（Imitation Learning,IL, 根据玩家的数据来学习游戏的策略，基于游戏图像，需要玩家数据）。  
    + 逆强化学习(Inverse Reinforcement Learning,IRL,根据策略来学习游戏中的奖励分布)。
### 关键问题  
* 游戏状态的表达（game state representation）  
* 游戏前向模型（Forward Model）
  * Fast and accurate  
* 训练时间（Training Time）
  * learning or search  
* 泛化性要求(Generalization)  
  * 不同种类的bot，不同的关卡，不同的任务  
    ![overview of methods to play games](./image/overview_of_methods_and_requirements.png)
<center>AI方法以及前置要求概念图.[1]</center>  
<br/>  

 - 一些方法不需要学习游戏知识，但是需要前向模型 (tree search)
 - 一些方法不需要前向模型，但是需要学习从游戏状态到动作的策略 (model-free reinforcement learning)
 - 一些方法即需要前向模型也需要训练时间 (model-based reinforcement learning and tree search with adaptive hyperparameters).

## 利用AI生成游戏内容(Procedural content generation,PCG)  
> 利用AI的方法去协助设计游戏系统，前置要求是**需要比较好的数据**（包括数据的质量，数据的代表方式，数据的数量）和**有代表性的评估方法**（包括美学，可玩性，新奇性）。具体的应用方法需要进一步查阅资料。  

![PCG overview](./image/PCG_industry.png)  
<center>PCG 概念图.[2]</center>  
<br/>  

![cost of AAA games](./image/cost_of_a_AAA_game.png)  
<center>3A作品制作成本图.[2]</center>  
<br/>  

### 应用为导向  
+ (辅助)生成游戏中的内容（影响规则）  
    > 关卡、地图、物品、武器、任务、人物、规则等。  
+ (辅助)生成游戏中的外观（不影响规则）  
    > 人物外观，表情，武器外观，音效等。  
+ 辅助设计  
     ![helping designer](./image/PCG_designer_assisted.png)
+ 修复地图bug  
    > 对无法抵达的死角做检测与替换等。  
+ 数据压缩   
    > 将游戏数据压缩到更小的尺寸。  
+ 图例   
    ![PCG content](./image/PCG_content.png)  
    ![PCG content1](./image/PCG_content_examples1.png)  
    ![PCG content7](./image/PCG_content_examples7.png)  
    ![PCG content8](./image/PCG_content_examples8.png)  
    ![PCG content9](./image/PCG_content_examples9.png)  
### 方法为导向  
 ![PCG main approach](./PCG_main_approach.png)  
+ 元胞自动机  
    > 使用领域规则根据随机初始状态生成大量不规则图形，可用于热量、雨水、液体流动、压力爆炸等环境系统建模，也可以生成洞窟等小型地图，但**无法保证可控性**。  

      ![Cellular](./image/Cellular_Automata_detail.png)  
      ![Cellular Example](./image/Cellular_Automata_Examples.png) 
      ![Cellular Example2](./image/Cellular_Automata_Examples2.png)   
+  基于文法方法  
    > 定义一系列文法规则来生成内容。  

      ![Grammar](./image/PCG_Grammars_detail.png)  
      ![Grammar example1](./image/PCG_Grammars_Example1.png)  
      ![Grammar example2](./image/PCG_Grammars_Example2.png)  
      ![Grammar example3](./image/PCG_Grammars_Example3.png)  
      ![Grammar example4](./image/PCG_Grammars_Example4.png)  
+  基于搜索方法（通常为Evolutionary Algorithms,EA）  
    > 相较于机器学习的方法，搜索方法可以大大减少所需求的数据量，关键问题有例如需要确定较好的内容表示形式，需要有一种较好的评估手段。  
    + EA类算法：遗传算法，演化策略，演化编程  
    + EA like 算法： 粒子群演算法，差分进化算法   
    + content representation:
        ![content representation](./image/PCG_representation.png)  
    + 评估方法
        ![content evaluation](./image/PCG_search_evaluation3.png)  
        + 直接评估 (通过某种函数去约束评估生成的内容)  
            + Theory-driven: 基于理论模型的评估函数  
            + Data-driven: 基于经验模型的评估函数  
    
        + 基于仿真 (利用bot AI去进行游戏来评估游戏的内容)  
            + 静态评估: 评估函数不会随着时间改变  
            + 动态评估: 评估函数会随着时间改变  
  
        + 互动评估 (实时评估，通过人类玩家的体验)  
            + 隐式评估: 通过玩家玩游戏产生的数据来分析内容好坏  
            + 显式评估: 玩家直接评分  
    + 例子    
      + 结合文法的EA  
        ![search-based examples1](./image/PCG_search_evaluation_Examples.png)  
        ![search-based examples2](./image/PCG_search_evaluation_Examples2.png)  

+ 机器学习方法(Procedural content generation via Machine Learning,PCGML)[3] 
    > PCG研究的一个新方向是在现有内容上训练生成器，以便能够产生更多相同类型和风格的内容。这是受最近的深度神经网络研究结果的启发，其中生成式对抗网络和变异自动编码器等网络架构在学习生成卧室、猫或人脸等图像方面取得了很好的效果，同时也受到了早期研究结果的启发，其中较简单的学习机制如马尔科夫链和较复杂的架构如递归神经网络都在一些语料库的训练后学习生成文本和音乐。
  + **神经网络**  
    + **GAN**  
    + **AutoEncoder**  
    + **NeuroEvolution**  
    + many others  
      > 举些例子  
        ![NN examples1](./image/PCG_NN_Examples1.png)  
        ![NN examples2](./image/PCG_NN_Examples2.png)  
        ![NN examples3](./image/PCG_NN_Examples3.png)  
  + **概率模型**  
  + **决策树**  
  + **Others**  
  + 大致的**PCGML**数据代表方式与训练方法总结如下：  
    1. 数据representation：
     * Sqquences: 利用顺序的向量来作为输入(输出)数据  
     * Grid: 使用2D的网格结构来作为输入(输出)数据  
     * Graph： 使用原始图像作为输入(输出)数据  
    
    2. PCGML训练方法：  
     * Backpropagation: 利用反向传播作为训练NN的方法来  
     * Evolution: 使用演化计算方法来训练NN或是直接生成结果  
     * Frequency Count：使用统计学与马尔科夫链变种来计算概率  
     * Expectation Maximization: 利用EA算法来训练无监督学习模型  
     * Matrix Factorization： 矩阵因子化是一种数学方法来将输入的矩阵分解到更低维度的方法  
+ **EDPCG**(Expierience-driven PCG)  
    > 将游戏生成内容与玩家体验结合  
    + **Overview**:  
       ![EDPCG overview](./image/EDPCG_overview.png)  
       **EDPCG** 包括了三个核心方面: **情绪激发、情绪检测和情绪表达**。 
        - **情绪激发**: 游戏为激发情感提供了出色的背景构件，因为刺激是变化的，来自不同的来源，如图像、声音、故事等等。  
        - **情绪检测**: 游戏用户（玩家）通常更愿意提供更多的多模态性质的输入（通过传感器），只要这将导致体验的增强。从某种意义上说，玩家是情感计算和多模态交互研究的最佳用户。  
        - **情绪表达**: 
          - 用户在游戏中自愿经历一系列的体验：这些体验从非常积极的到非常消极的都有。
          - 游戏中的情感体验是受玩家影响的! 因此，玩家习惯于并在很大程度上对基于情感的表达持开放态度!  
    + experience 定义： 
        > collection of 情感模式(**affective patterns**), 认知过程(**cognitive process**) and 行为特征(**ehavioral traits**)   
    + 玩家体验模型  
      > 通过传感器来从玩家的experience中评估玩家的体验的好坏   
    + 内容质量评估(参考上文)   
    + 内容presentation(参考上文)  
    + 内容生成  
      >理论上，EDPCG在体验（如挫折）、内容（如地图）和玩家行为的表现之间保持一种映射关系。鉴于这种映射的存在，任何优化方法都能够改变内容参数，以便为特定的玩家优化特定的体验，从而通过内容生成实现个性化的互动。 
## 利用AI为玩家建模(player modeling)  
> 利用游戏产生的数据来为玩家建立**体验**或**行为**模型（包括其消费预测，游戏性行为预测，体验感预测）或是进一步利用该数据来更新与描述游戏（例如平衡性分析，游戏流派，提供给Agent更多的训练数据）   
 
![why PM](./image/PM_example1.png)  
> 图片:潜行恐怖游戏《Hello Neighbor》中的玩家建模例子。在这款游戏中，AI会从你的每一个动作中学习。邻居会一直跟踪玩家，并从你的错误中吸取教训。反过来，你的邻居将教会人工智能如何打败你。  
 
### 应用为导向  
+ 理解玩家在游戏中的体验
     + 可以根据玩家的体验感来**评测游戏各个组件与系统**;  
     + 辅助更新新的游戏活动;  
     + 辅助更新前两个AI系统。  
+ 理解玩家在游戏中的行为  
     + 辅助分析游戏行为，例如发掘一些新的游戏玩法；
     + 可以根据异常数据来判定**外挂**等作弊系统；
     + 形成可观的游戏数据来支持新的游戏**AI迭代**；
     + 辅助设计更具有公平性的**匹配系统**;
     + **预测**玩家的行为；  
     + 对玩家**社交群体分类**；
     + 分析玩家的**性格**。
+ 一些图例   
   ![PM example1](./image/PM_example2.png)   
### 方法为导向  
+ Experience vs Behavior  
    + Experience: how you **feel** during play
      + 一系列(合成的)感受、认知、行为状态
      + 或是其他的用户状态
      + Emotions: Appraisal theory, …
      + Cognition/Behavior: several models (e.g. BDI,…)  

    + Behavior: what you **do** during play  
+ 高级概念分类  
  + model-based（理论驱动）
    > 从一些列玩家心理学、认知学的研究中得到一些玩家对应游戏的模型，来自上而下的设计游戏 
  + model-free（数据驱动）  
    > 不利用之前的学科研究来对玩家进行自下而上的建模
    + 可视化（例如热力图来衡量玩家的活动频率，轨迹图，）    
  + 图示  
    ![PM high level](./image/PM_model.png)  
      
    ![PM high level2](./image/PM_model_graph4.png)
+ 监督学习  
    > 玩家建模包括寻找一个函数，将玩家的一组可测量的属性映射到特定的玩家状态。按照监督学习的方法，这是通过机器学习或自动调整模型的参数来实现的，以适应包含一组输入样本的数据集，每个样本与目标输出配对。输入样本对应于可测量的属性（或特征）列表，而目标输出对应于我们有兴趣学习预测的每个输入样本的玩家状态的注释。如前所述，注释可以从行为特征，如关卡或玩家原型的完成时间，到玩家经验的估计，如玩家的挫折感等。   
    >流行的监督学习技术，包括人工神经网络（浅层或深层结构）、决策树和支持向量机，可以在游戏中用于分析、模仿和预测玩家的行为，以及对游戏经验的建模。注释的数据类型决定了模型的输出，反过来也决定了可以应用的机器学习方法的类型。从数字（或区间）、名义和序数注释中学习的三种监督学习方法分别是：回归、分类和偏好学习.  
    ![player modelling supervised learning](./image/PM_model_supervisedlearning.png)
    + 回归  
    + 分类  
    + 偏好学习  
+ 强化学习  
     + 模仿学习  
     + 逆强化学习  
+ 无监督学习 
    > 很多时候，我们面临的数据集是没有关于玩家行为或经验状态的目标输出。在这种情况下，玩家的建模必须依靠无监督学习。无监督学习的重点是通过发现输入的关联，在没有获得目标输出的情况下，将模型与观察结果相匹配。输入通常被视为一组随机变量，通过观察输入向量之间的关联来建立模型。  
    > 应用于玩家建模的无监督学习包括聚类和关联挖掘等任务。
     + 聚类  
     + 频繁模式挖掘  

## Reference
[1]Georgios N. Yannakakis and Julian Togelius. Lecture. Slide 3. **Playing Games**. [Online].http://gameaibook.org/lectures/   

[2]Georgios N. Yannakakis and Julian Togelius. Lecture. Slide 4. **Generating Content**. [Online].http://gameaibook.org/lectures/   

[3]Summerville, Adam, Sam Snodgrass, Matthew Guzdial, Christoffer Holmgård, Amy K. Hoover, Aaron Isaksen, Andy Nealen, and Julian Togelius. "**Procedural content generation via machine learning (PCGML).**" IEEE Transactions on Games 10, no. 3 (2018): 257-270. [[pdf](https://arxiv.org/abs/1702.00539)]  

[4]Georgios N. Yannakakis and Julian Togelius. Lecture. Slide 5. **Modeling Players**. [Online].http://gameaibook.org/lectures/   
