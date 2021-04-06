**hydro-dl-basic**
=====

**人工智能（Artificial Intelligence, AI）理论基础学习**
------

本repo主要是记录以深度学习、强化学习、迁移学习为重点的各类学习算法的日常积累，为xxxx.，先做一些知识铺垫，以下将从基础知识出发剖析不同算法之间的区别与联系，对各类学习算法有更加清晰的认识。

#**Part Ⅰ 基础知识 **


###人工智能（Artificial Intelligence, AI）

**人工智能**是计算机科学的一个分支，它企图了解智能的本质，并产生出一种新的能以人类智能相似的方式作出反应的智能机器，是研究、开发用于模拟、延伸和扩展人的智能的理论、方法、技术及应用系统的一门新的技术科学,包括**弱人工智能**、**强人工智能**、**超级人工智能**三种形态，目前的科研工作主要集中在弱人工智能这部分，并且已经取得了一系列的重大突破。

##机器学习（Machine Learning,ML）

**弱人工智能**是如何实现的，**智能**又从何而来呢？这主要归功于一种**实现人工智能的方法**——**机器学习**。

###机器学习定义一：**机器学习的第一类定义**是IBM提出的认知计算 (Cognitive Computing)，其目标是构建不需要显式编程的机器（计算机、软件、机器人、网站、移动应用、设备等）。

###机器学习定义二：上述定义很好，但可能有点太模糊。因此提出一个更精确的定义，**“正确提出的学习问题：如果计算机程序对于任务T的性能度量P通过经验E得到了提高，则认为此程序对经验E进行了学习。”**为了阐述清楚，我们举一个例子：在下棋程序中，经验E指的就是程序的上万次的自我联系的经验，任务T就是下棋，性能度量P指的就是在比赛过程中取胜的概率，有了性能指标后，我们就能告诉系统是否学习该经验。
**此处待插入图片**

###机器学习算法分类：上述定义为机器学习设定了清晰的目标，但是，它们没有告诉我们如何实现该目标，我们应该让定义更明确一些。这就需要**第二类定义**，这类定义描述了**机器学习算法**，以下是一些流行的定义。在每种情况下，都会为算法提供一组示例供其学习。

**- 监督式学习：**为算法提供训练数据，数据中包含每个示例的“正确答案”；例如，一个检测信用卡欺诈的监督学习算法接受一组记录的交易作为输入，对于每笔交易，训练数据都将包含一个表明它是否存在欺诈的标记。即用一部分已知分类、有标记的样本来训练机器后，让它用学到的特征，对还没有分类、无标记的样本进行分类、贴标签。多用于**分类**。

**- 无监督式学习：** 该算法在训练数据中寻找结构，比如寻找哪些示例彼此类似，并将它们分组到各个集群中。即所有的数据没有标记，类别未知，让它自己学习样本之间的相似性来进行分类。多用于**聚类**。

**- 半监督式学习：** 有两个样本集，一个有标记，一个没有标记。综合利用有类标的样本（ labeled sample）和没有类标的样本（ unlabeled sample），来生成合适的分类。

**有待继续解释”半监督式学习“**

###机器学习问题分类：我们希望在机器学习算法分类的基础上更具体一些，一种方法是通过分析机器学习任务能解决的问题类型，对任务进行细化：

**- 分类：**一种**监督学习**问题，其中要学习的答案是**有限多个可能值之一**；例如，在信用卡示例中，该算法必须学习如何在“欺诈”与“诚信”之间找到正确的答案，在仅有两个可能的值时，我们称之为二元分类问题；用于**实现分类的常用算法**包括：支持向量机 (SVM)、提升 (boosted) 决策树和袋装 (bagged) 决策树、k-最近邻、朴素贝叶斯 (Naïve Bayes)、判别分析、逻辑回归和神经网络。
 
 **-回归：**一种**监督学习**问题，其中要学习的答案是一个**连续值**。例如，可为算法提供一条房屋销售及其价格的记录，让它学习如何设定房屋价格；常用**回归算法**包括：线性模型、非线性模型、规则化、逐步回归、提升 (boosted) 和袋装 (bagged) 决策树、神经网络和自适应神经模糊学习。

**-细分（聚类）：**一种**无监督学习**问题，其中要学习的结构是一些类似示例的集群。一种**无监督学习**问题，其中要学习的结构是一些类似示例的集群。

**-网络分析：**一种**无监督学习**问题，其中要学习的结构是有关网络中的节点的重要性和作用的信息；例如，网页排名算法会分析网页及其超链接构成的网络，并寻找最重要的网页。谷歌等 Web 搜索引擎使用的就是这种算法，其他网络分析问题包括社交网络分析。

**此处待插入图片**

###机器学习工作流程及定义三：上述两个定义的问题在于，开发一个机器学习算法并不足以获得一个能学习的系统。诚然，机器学习算法与学习系统之间存在着差距。上述两个定义的问题在于，开发一个机器学习算法并不足以获得一个能学习的系统。诚然，机器学习算法与学习系统之间存在着差距。下面给出一个**机器学习工作流**，如下图所示；机器学习算法被用在工作流的“训练”步骤中，然后它的输出（一个经过训练的模型）被用在工作流的“预测”部分中。好的与差的机器算法之间的区别在于，我们在“预测”步骤中获得的预测质量。这就引出了机器学习的另一个定义：**“机器学习的目的是从训练数据中学习，以便对新的、未见过的数据做出尽可能好的预测”。**

###深度学习（Deep Learning,DL）

**深度学习是一种实现机器学习的技术。**到此，可能会有疑问？机器学习下的深度学习、监督学习、无监督学习以及半监督学习之间是什么关系呢？其实就是**分类方法不同而已**，他们之间可以**互相包含**。打个比方：一个人按性别可以分为男人和女人，而按年龄来分可以分为老人和小孩子。所以在深度学习中我们可以用到监督学习和非监督学习，而监督学习中可以用到很基础的不含神经元的算法（KNN算法），也可以用到添加了多层神经元的深度学习算法。

**有待插入深度学习、监督学习..图片表示**

**深度学习定义**深度学习是机器学习中一种基于对数据进行表征学习的算法。观测值（例如一幅图像）可以使用多种方式来表示，如每个像素强度值的向量，或者更抽象地表示一系列边、特定形状的区域等。而使用某些特定的表示方法更容易从实例中学习任务（例如人脸识别、面部表情识别）。**深度学习的好处是用非监督式或半监督式的特征学习和分层特征提取高效算法来替代手工获取特征。**

**深度神经网络**

**xxxx此处有待描述ANN、CNN、RNN的介绍**

###强化学习（Reinforcement Learning,RL）


###迁移学习（Transfer learning,TL）

**迁移学习**顾名思义就是把已学训练好的模型参数迁移到新的模型来帮助新模型训练。考虑到大部分数据或任务是存在相关性的，所以通过迁移学习我们可以将已经学到的模型参数（也可理解为模型学到的知识）通过某
种方式来分享给新模型从而加快并优化模型的学习效率不用像大多数网络那样从零学习 (Starting From Scratch)。

**迁移学习定义**迁移学习是机器学习技术的一种，其中在一个任务上训练的模型被重新利用在另一个相关的任务上。

**定义一：**迁移学习和领域自适应指的是将一个任务环境中学到的东西用来提升在另一个任务环境中模型的泛化能力。

**定义二：**迁移学习就是通过从已学习的相关任务中迁移其知识来对需要学习的新任务进行提高。

**迁移学习在深度学习中的应用**：迁移学习还与多任务学习和概念漂移等问题有关，它**并不完全是深度学习的一个研究领域**。尽管如此，由于训练深度学习模型需耗费巨大资源，包括大量的数据集，迁移学习便成了深度学习中一种很受欢迎的方法。但是，只有当从第一个任务中学到的模型特征是容易泛化的时候，迁移学习才能在深度学习中起到作用。“在迁移学习中，我们首先在基础数据集和任务上训练一个基础网络，然后将学习到的特征重新调整或者迁移到另一个目标网络上，用来训练目标任务的数据集。如果这些特征是容易泛化的，且同时适用于基本任务和目标任务，而不只是特定于基本任务，那迁移学习就能有效进行。”——深度神经网络中的特征如何迁移的？这种用于深度学习的迁移学习形式被称为**推导迁移** (Inductive Transfer)。就是通过使用合适但不完全相同的相关任务的模型，将模型的范围（模型偏差）以有利的方式缩小。

**此处有待插入图片**

**迁移学习使用方法**：们可以在自己的预测模型问题上使用迁移学习，通常有两种方法：**开发模型方法**和**预训练模型方法**。

对于**开发模型方法**，分为四步：
 
 **- 选择源任务：**必须选择一个与大量数据相关的预测模型问题，这个大量的数据需要与输入数据，输出数据和/或从输入到输出数据映射过程中学习的概念之间存在某种关系。

**- 开发源模型：**接下来，必须为这个第一项任务开发一个熟练的模型；该模型必须比原始模型更好，以确保一些特征学习已经发挥了其作用。

** - 重用模型：**然后可以将适合源任务的模型用作感兴趣的另一个任务模型的起点；这取决于所使用的建模技术，可能涉及到了全部或部分模型。

** - 调整模型：**可选项，对感兴趣任务的调整输入—输出配对数据或改进模型。

对于**预训练模型方法**，分为三步：

** - 选择源任务：**从可用的模型中选择预训练的源模型，许多研究机构会发布已经在大量的且具有挑战性的数据集上训练好的模型，在可用模型的模型池里面也能找到这些模型。

** - 重用模型：**然后可以将预训练的模型用作感兴趣的另一个任务模型的起点，这取决于所使用的建模技术，可能涉及使用全部或部分模型。

**-调整模型：**可选项，对感兴趣任务的调整输入—输出配对数据或改进模型。
 其中，第二类迁移学习方法在深度学习领域是很常见的。

#**Part Ⅱ**

接下来将介绍
 
 ** 机器学习 VS 深度学习 VS 强化学习 VS 迁移学习 VS 人工智能**
 




![输入图片描述](img-readme/QQ%E6%88%AA%E5%9B%BE20210315172022.png)


