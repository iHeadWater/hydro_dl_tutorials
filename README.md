# **hydro-dl-basic**

# **人工智能（Artificial Intelligence, AI）理论基础学习**

## 人工智能的三大学派
**（1）符号主义学派：基于数理逻辑，认为人类思维的过程可以用符号操作来描述，在给定由公理和规则组成的集合后，所有智能行为都能归结为对特定命题的判定问题。**
  * 精确逻辑：采用数理逻辑方法，对于命题可以用精确的规则进行划分。
    * 典型应用：专家系统，专家系统分为两个子系统：
      * 知识库：存储结构化信息。
      * 推理引擎：自动推理系统，用于评估知识库的当前状态，并应用相关规则进行逻辑推理，然后将新结论添加到知识库中。
      * 缺点：
        * 需要人为定义和补充规则，决定了专家系统的智能水平不会高于人类，无法解决复杂问题；
        * 基于逻辑推理，无法解决非逻辑性问题。
  * 模糊逻辑：元素可以属于多个不同的集合，元素和不同集合的关联性强弱由隶属度决定。
    * 模糊控制系统：
      * 模糊化：利用隶属函数完成输入变量的模糊化，得到模糊变量。
      * 模糊推理：通过规则器对输入进行推理，得到模糊控制变量。
      * 逆模糊：利用隶属函数去模糊化处理为精确的控制变量。
    * 一些定义：
      * 隶属度：用于表示不确定性的强弱，在概率随机性基础上加入了信息的意义和定性，是一种比随机性更加深刻的不确定性质。如35岁的人属于年轻人和中年人集合的隶属度可能为0.6和0.4。<br />
       
**（2）联结主义学派：基于神经网络，认为人类大脑的思维体系具有复杂的秉性结构，从神经元开始，进而研究神经网络模型和脑模型。**
  * 感知器（出现于20世纪60至70年代）：解决线性分类问题。
    * M-P模型（阈值加权和模型）：
      * 一个神经元接受的信号可以是起刺激作用的，也可以是起抑制作用的，其累积效果决定该神经元的状态，同时神经元的突触信号的输出是“全或无”，即仅当神经元接受的信号强度超过某个阈值时，才会由突触进行信号输出。
    * 学习算法：感知器学习算法。
      * 原理：输入连接的所有输出信号值和存储在处理单元局部内存中的参数值相互作用后得到求和累计值，输出通过激活函数进行处理。
      * 学习过程：**调整其中存储的参数值的过程。**
      * 分类：
        * 无监督学习：学习过程中，数据中输入样本的信息，但不知道输入和输出之间的关系，感知器通过学习抽取输入样本的特征或同级规律。如Hebb算法（赫布）。
        * 监督学习：学习过程中，数据是成对出现的，与输入对应的输出是已知的。通过逐步将集中的样本输入到网络中，根据输出结果和理想输出之间的差别来调整和学习感知器中存储的参数，从而使感知器的输出逐渐接近理想输出。如Delta法则（德尔塔，梯度下降）
    * 计算平台：晶体管。
    * 应用：几乎没有，因为需要收集大量的专门知识并定义庞杂的推理方案，成本高。
* 人工神经网络（Artificial Neural Network，即ANN ）（出现于20世纪80-90年代）：对生物神经网络的模仿，无法解决抑或问题。
    * 结构：
      * 输入层：接受来自网络外部的信号输入。
      * 隐藏层：对输入信号进行变换和学习，是人工神经网络强大学习和表达能力的来源。
      * 输出层：输出网络的计算结构。
    * 特点：
      * 信息是分布式存储和表示的。每个人工神经元中保存的参数值称为神经网络的长时记忆。**人工神经网络的学习过程，就是调整每个人工神经元保存的参数值的过程。**
      * 全局并行+局部操作。每个神经元的输入-输出映射具有局部性，全局并行使得可以高速并行地处理大量数据。
    * 学习算法：反向传播算法
      * 反向传播算法两个过程（反复执行这两个过程，直到一定的迭代次数或者损失函数不再下降为止）：
        * 前向传播：
          * 从输入层经隐藏层逐层处理后，传至输出层。
          * 通常网络输出与理想输出存在误差，用损失函数L（O,L）来计算实际输出和理想输出之间的误差，**网络的训练目标是最小化损失函数。**
        * 反向传播：
          * 利用损失函数计算输出层和理想输出之间的误差，并利用此误差计算输出层的直接前导层的误差，在用输出层前导层误差估计更前一层的误差。如此重复获得所有其他各层的误差估计。
          * 通过最小化每层的误差（梯度下降法）来修改每层的参数值，从而达到学习的目的。
    * 计算平台：图形处理器。
    * 应用：语音识别、图像识别、自动驾驶等。
* 深度学习（21世纪初-至今）：复杂函数
  * 特点：
    * 相比于传统人工神经网络最大的特点是网络成熟更多，利用了卷积神经网络和循环神经网络等更为复杂的结构，参数量成倍增长，使模型的表示和学习能力进一步提升。 
  * 学习算法：预训练+微调
    * 通过一个“预训练”的过程对神经网络进行逐层学习，在通过反向传播算法对整个网络进行“微调”。
  * 计算平台：分布图形处理器平台。
  * 应用：如图像、语音、自然语言处理等几乎所有人工智能领域。<br />
 
 **(3)行为主义学派：基于进化论，认为必须赋予机器自主感知和行动的能力，将重点放在语言、行为等外部信号的建模上。**
 * 进化计算算法：模拟生物种群在进化过程中的自然选择和自然遗传机制。
   * 遗传算法：模拟生物在自然环境中遗传和进化而形成的一种自适应全局优化概率搜索算法，按照与个体适应度成正比的概率决定当前群体中每个个体遗传到下一群体中的机会。
     * 三种遗传算法：
       * 选择算子：根据各个个体的适应度，按照一定的概率规则，从当前群体中选择出一些优良的个体遗传到下一代群体中。
       * 交叉算子：将群体内的各个个体随机搭配成对，对每一个个体，根据交叉概率交换它们之间的部分染色体。
       * 变异算子：对群体中的各个个体，以变异概率改变染色体上的基因值为其他的等位基因。
     * 遗传算法对群体反复执行选择、交叉、变异步骤，直到搜索群体找到目标函数的最优值或者满足收敛条件。
     * 特点：
       * 自适应概率搜索技术，增加搜索过程的随机性和灵活性。
       * 解空间的多点搜索，可并行处理，提高性能。
       * 以目标函数值作为搜索信息，不需要目标函数的导数等其他信息。
     * 一些定义：
       * 适应度函数：对问题中每个个体都能进行度量的函数。
       * 染色体：遗传算法使用固定长度的二进制符号串来表示群体中的个体。
 * 群体智能算法：对生物群体在协作和交互过程中涌现出的复杂行为进行建模。
   * 定义：指一群功能简单、具有信息处理能力、自组织能力的个体通过通信、交互、协作等手段所涌现出简单个体所不具备的复杂问题求解能力。
   * 特征：
     * 个体同质，没有中心控制节点，适用于并行计算模型；
     * 种群具有可扩展性，种群内个体数目可变；
     * 种群内部具有协作性，个体之间存在相互协作机制；
     * 种群具有临近性，个体之间交互机制的作用范围有限；
     * 种群具有自适应性，能顾根据环境变化自动调整；
     * 种群具有稳定性，某些个体故障不会影响到系统的正常工作。
   * 常见算法：
     * 蚁群算法：基于蚁群觅食行为的建模。
       * 特点:
          * 种群多样性：以随机概率选择路径。
          * 信息素更新的正反馈机制：某条路径更短，则往返时间越短，路径上信息素被更新的频率更高，路径上的信息素浓度更高。
       * 应用场景：组合优化问题，如任务调度问题、图着色问题、旅行商问题。
     * 粒子群算法：基于鸟群觅食行为的建模。
       * 可行解（鸟类）朝全局最优解（食物）移动和收敛的过程。
       * 一些定义：
          * 个体学习能力：个体记忆自身历史信息的能力。
          * 社会认知能力：感知临近个体飞行状态的能力。
       * 应用场景：对连续空间的优化求解问题。
  ## 机器学习
 * 学习就是系统在不断重复的工作中对本身能力的增强或者改进，使得系统在下一次执行同样任务或类似任务时，会比现在做的更好或效率更高。<br />
 * 机器学习是近20多年兴起的一门**多领域交叉学科，涉及概率论、统计学、逼近论、凸分析、算法复杂度理论等**多门学科。机器学习理论主要是涉及和分析一些让计算机可以**自动“学习”**的算法。<br />
 * 机器学习算法是一类从数据中自动分析获得规律，并利用规律对未知数据进行预测的算法。<br />
  [机器学习工作流程]（https://github.com/wangmengyun1998/hydro-dl-basic/blob/main/img-readme/%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%B7%A5%E4%BD%9C%E6%B5%81%E7%A8%8B.jpg）<br />
  
 (1)机器学习的定义
  * 系统通过获取经验替身自身性能的过程。即系统自我改进过程。机器学习是人工智能的核心研究领域之一。
  * 机器学习研究的是如何使计算机能够模拟或实现人类的学习功能，从大量数据中发现规律、提取知识，并在实践中不断完善和增强自我。
  * 机器学习的过程就是一个对包含可能假设的空间进行搜索的过程，使得到的假设在满足先验知识和其他约束的前提下，与给定训练样本是最吻合的。
  * 机器学习就是一类能够让计算机从大量已知的以特征向量表示的训练样本中，学习到一个泛华能力强的分类器的方法。
     * 分类器好坏的衡量标准：损失函数
       * 分类问题中，损失函数定义为机器学习得到的分类器对样本的分类结果和样本真实类别的差异。
       * 回归问题中，损失函数定义为学习得到的分布与样本的真实分布之间的差别。
    * 目标：最小化损失函数。
      * 优化方法：
        * 启发式的方法：
          * 遗传算法
          * 粒子群算法
        * 基于梯度方向的算法：
          * 批量梯度下降法
          * 随机梯度下降法
          * 小批量梯度下降法
    * 一些定义：
      * 梯度：是一个向量（矢量），表示某一函数在该点处的方向导数沿着该方向取得最大值，即函数在该点处沿着该方向（此梯度的方向）变化最快，变化率最大（为该梯度的模）。
      * 过拟合问题：简单的最小化损失函数在训练样本上的值，容易造成分类器对没有见过的样本的分类正确率降低，即分类器的泛华能力不够。
      * 惩罚项：在损失函数里添加的一个衡量分类器复杂度的标准。
        * 惩罚项通常由分类器参数的各种形式表征，当分类器形式太复杂时，使得损失函数的值也会比较大。
        * 作用：使得降低分类器错误率的同时，也能将分类器的形式限制得比较简单，保证它的泛华能力。<br />
         
 （2）机器学习的基本术语
* 我们看到一些关于橘子和橙子的数据集合，这些记录的集合称为**数据集**。<br />
* 每条记录是关于一个橘子或橙子的描述称为**示例或样本**。<br />
* 记录中的形状、剥皮、味道称为**属性或特性**。<br />
* 圆形、难、甜为各自属性或特征的**属性值**。<br />
* 如果把形状、味道、剥皮设为三个坐标轴，那么它们长成一个描述橘子或橙子的**属性空间或样本空间**，每个橘子或橙子都可以在属性空间中找到自己的坐标位置，我们把每个示例也称为**特征向量**。<br />
* D{x1,x2,...xm}是m个示例的数据集，xi={xi1,xi2,...xid}是d维样本空间X的一个特征向量，d为样本空间的维数。<br />
* 从数据中学得模型的数据称为**学习或训练**；这个过程通过某个学习算法来实现，训练过程中使用的数据称为**训练数据**，其中每个样本称为一个**训练样本**。训练样本组成的集合称为**训练集**。例如，橘子或橙子称为标记，拥有了标记的信息的实例称为**样例**。<br />
* 机器学习的任务一般有以下几类：
  * 当预测或输出的是**离散值**，此类学习任务称为**分类问题**。比如人脸识别、动作识别都是此类任务。
  * 当预测或输出的是**连续值**，此类学习任务称为**回归问题**。比如房价预测、股票价格预测等。
  * 对只涉及两个类别的分类问题称为**二分类任务**，常见于是否问题。比如划分是否为动物，肿瘤为良性或恶性，股票是涨还是跌等，我们经常说的正例、负例也是针对二分类问题。
  * 设计多个分类为**多分类任务**，二分类和多分类都是属于分类问题，由于二分类问题清醒简单而又广泛，所以单独列出为一类问题。
  * **聚类任务**是将相似的事物归类为一组，例如对文本数据集自动进行分组。
  * **多标签标注问题**是对一个变量序列的输入，获得一个变量序列的输出。多标签问题可以看做是分类任务的一种扩展，例如图像识别，在分类任务上会给出单个标签，如猫、狗、天空、森林等。而**多标签**是给一张图像多个类别，比如实际图像可能既有天空、大海、又有行人、房屋等。分类问题一般用于内容单一的图像，多标签则用于处理复杂场景的图像，也可用于图像检索的任务。<br />
  
 （3）监督学习
 * 监督学习的目的是学习一个由模型输入到模型输出的映射，学习的结果成为**模型**，模型集合就是假设空间。<br />
 * 模型分为概率模型，就是学习条件概率，X条件下Y的的概率和非概率模型，就是决策函数Y等于F（X）联合概率分布。<br />
 * 假设输入与输出的随机变量X和Y遵循联合概率分布p（x,y），这为分布函数或分布密度函数，对于学习系统来说，联合概率分布是未知的，训练数据和测试数据被看做是以联合概率分布p（x,y）独立同分布产生的，监督学习的问题形式化输入的是**训练数据**，也就是**样例**，每个样例包含数据x和对应的标签Y，通过学习系统的学习得到模型，该模型可以是概率模型也可以是非概率模型，模型得到后可以对xn+1的测试数据进行分类测试，推测出xn+1的标签yn+1。<br />
   [监督学习]（插入图片）<br />
   
 
 （4）训练误差和测试误差
 （5）过拟合与模型选择
 （6）泛华能力
 （7）编码器和解码器
  (8)生成模型和判别模型
 （9）模型性能评估
   
 （10）机器学习的分类
 * 按照训练样本的具体情况分类
   * 监督学习：用来训练分类器的训练样本由样本的特征向量和类别标号构成。
     * 常见监督学习算法：
       * 回归分析和统计分类
         * 线性回归
         * 决策树
         * 神经网络
   * 无监督学习：训练样本只有特征向量，而不包括每个向量对应的类别。
    * 常见的无监督学习算法：
      * 聚类分析
        * k-均值聚类
        * 模糊k-均值聚类
   * 半监督学习：介于监督学习和无监督学习之间，指在大量无类别标签的样本的帮助下，训练少量已有类别标签的样本，获得比仅仅利用这些很少的标注样本训练得到的分类器的分类能力更强的分类器，以弥补有类别标签的样本不足的缺点。<br />
   * 强化学习：在某个环境中，存在各种不同的状态，机器可以采取几种不同的动作使得自己在几种不同状态之间以一定的概率切换，不同的状态对应不同的结果，这个结果用汇报来衡量，通过强化学习找到策略，使得机器在面对不同的状态时采取合适的动作，使得获得的汇报最大。
* 按照算法的功能分类
  * 回归算法（预测连续目标变量）：通过最小化预测值与真实值之间差距，而拟合出输入特征之间的最佳组合的一类算法（用一条线来拟合一些离散的点）
    * 线性回归：利用最小二乘法建模因变量和一个或多个解释变量（或称为独立变量）之间对应关系的一种回归分析。
        * 学习方法：最小化基于预测值与真实值的均方误差所构成的损失函数
        * 最小二乘法（又称最小平方法）：是一种数学优化技术。它通过最小化误差的平方和寻找数据的最佳函数匹配。利用最小二乘法可以简便地求得未知的数据，并使得这些求得的数据与实际数据之间误差的平方和为最小。最小二乘法还可用于曲线拟合。其他一些优化问题也可通过最小化能量或最大化熵用最小二乘法来表达。
        * 应用场景：
           * 通过拟合函数根据自变量预测出一个因变量值
           * 用来量化因变量与自变量之间相关性的强弱，评估出某些与自变量不相关的因变量
    * 非线性回归：
       * 学习方法：最小化基于预测值与真实值的均方误差所构成的损失函数
       * 非线性的，模型可以是如对数、指数、高次方程等等
 * 分类算法（预测离散目标变量）：通过训练样本学习到每个类别的样本特征，利用这些特征构建分类线或分类面，将各种不同的样本分隔开，并且最小化错分样本数量的一类算法。
   * 贝叶斯分类算法(监督)：基于贝叶斯公式，逆概问题
      * 利用现有信息，计算出某些相关事件的先验概率，然后利用贝叶斯公式根据已知的经验计算得到需要的后验概率。
   * 决策树算法（监督）：某项活动开展与否，去决定于一系列前提条件，并且我们已经有了在这些条件下活动是否进行的训练数据，我们可以根据这些数据，按照是否满足某个特定的条件，逐步缩小活动是否开展所要考虑的条件范围，最终给出是否开展活动的确定性答案。
      * 决策树是一个预测模型，代表的是对象属性和对象值之间的一种映射关系
      * 每个结点表示某个对象，每个分叉路径代表某个可能的属性值，每个叶节点对应从根节点到该叶节点所经历的路径所表示的对象的值
      * 决策树构建过程是一个自顶向下的贪心递归过程
      * 缺陷：
        * 容易陷入过拟合，解决方法：预剪枝以及剪掉树中那些样本数非常少的结点，去除特例样本带来的冗余信息
    * 支持向量机（SVM,Support Vector Machine）（监督）：不仅考虑将训练样本正确区分开，而且考虑分类线（面）的位置，使得它能够将各类样本尽可能分隔得足够远
         * 可以解决线性不可分隔，通过核函数映射，使得在低维空间表示不可分的样本，通过投影到更高维的空间就可以变成线性可分的了。
         * 一些定义：
           * 核函数：核函数就是低维空间中的内积的某个函数，通过核函数可以计算出高维空间中两个数据点之间的距离和角度
    * 近邻算法（监督）：
       * K-近邻算法：基于实例的学习算法
          * 算法在对未知样本进行分类时，需要先计算它与所有一致类别标签的样本的欧式距离，然后找出与它距离最近的k个样本，这k个样本中哪个类别样本数最多，就将这个未知的样本分类为对应的类别
          * k通常取不能被类别整除的值
   * 聚类算法（无监督）：基于距离的聚类算法（迭代求解）
      * 预将数据分为k组，则随机选取K个对象作为初始的类别中心，然后计算每个对象与类别中心之间的距离，把每个对象分配给距离它最近的类别中心。类别中心以及分配给它们的对象就代表一个聚类。每分配一个样本，聚类的类别中心点会根据聚类中现有的对象被重新计算。这个过程将不断重读直到满足某个终止条件。终止条件可以是没有（或最小数目）对象被重新分配给不同的聚类，没有（或最小数目）聚类中心在发生变化，误差平方和局部最小。
   * 深度学习算法（深度神经网络）：相比于人工神经网络，其拓扑结构上节点层数比较多。
     * 定义：
       * 一种多层描述的表示学习，通过组合简单、非线性模块来实现，每个模块都会将最简单的描述（从原始输入开始）转变为较高层、较为抽象的描述。
       * 深度学习善于在高纬度的数据中摸索出错综复杂的结构。
     * 举例子：图像识别：
       * 第一特征层：机器学到的特征主要是图像中特定方位、位置边缘的信息
       * 第二特征层：机器通过发现特定边缘的组合来检测图案，此时机器并不考虑边缘位置的微小变化
       * 第三特征层：机器将局部图像与物体相应部位匹配
       * 后续层级：将局部组合起来从而识别出整个物体
       * 局部轮廓边缘组合形成基本图案，基本图案形成物体的局部，局部物体再组成物体。
     * 常用网络结构：
       * 卷积神经网络（Convolutional Neural Networks，CNN）(监督)：
      [插入CNN图片]  
         * 一些定义：
             * 离线的卷积计算：由一个特征图执行的过滤操作
             * 通道：一个通道是对某个特征的检测，通道中某一处数值的强弱就是对当前特征强弱的反应
         * 卷积层：通道与通道之间进行交互，探测前一层中特征之间的局部连接，之后再下一层生成新的通道
             * 一个卷积层单元通过一组滤波器权值连接到前一层的特征图的局部数据块；接下来，得到的局部加权和会传递至一个非线性函数进行变换计算激励值
         * 池化层：对语义相似的特征进行合并
             * 一个池化层单元通常会计算一个或几个特征图中一个局部块的最大值，相邻的池化单元则会移动一列或一行从小块读取输入
         * 常见应用
             * 人脸识别
             * 语音识别
             * 文本识别
             * 生物信息分割
      * 循环神经网络（Recurrent Neural Network,RNN,也称递归神经网络)：通常用于需要序列连续输入的任务，如语音和语言
        * 循环神经网络一次处理一个输入序列元素，同时维护的隐藏层单元中隐含着该序列过去所有元素的历史信息。
             * 编码器：一种在最后隐藏层将像素转换为活动向量的深度卷积网络
             * 解码器：一种类似机器翻译和神经网络语言模型的循环神经网络
        * 特殊隐藏层单元的长短期记忆网络：能够长期保存输入的信息
        * 一些定义：
             * 隐藏层：把输入数据的特征，抽象到另一个维度空间，来展现其更抽象化的特征，这些特征能更好的进行线性划分。
      * 对抗神经网络（Generative Adersarial Networks,GAN）:由判别模型和生成模型组成，可以利用对抗过程估计生成模型。 
        * 一个网络生成模拟数据，另一个网络判断生成的数据是真实的还是模拟的。生成模拟数据的网络要不断优化自己让判别的网络判断不出来，判别的网络也要不断优化自己让判断更加精确。两者的关系形成对抗，因此叫对抗神经网络。
      * 自编码机（Auto Encoder）(无监督）：基于多层神经元，主要用于数据的降维或者特征的抽取。
      * 玻尔兹曼机：受统计力学启发的多层学习机，它是一类典型的随机神经网络，属于反馈神经网络。
        * 离散Hopfield神经网络+模拟退火+隐单元=Boltzman机
    * 强化学习（Reinforcement Learning,RL，深度增强学习）：一种试错的学习方式，解决决策制定问题，学会根据自身所处环境自动做出相应决策
      * 定义：一个序列决策制定问题，它需要连续选择一些动作，从而使得机器在执行这些动作之后获得最大的收益、最好的结果。
      * 四个主要元素：
        * 环境状态集合S
        * 动作结合A
        * 状态之间的转换规则P
        * 特定动作导致的状态转移之后带来的回报R
      * 学习过程：
        * 探索：放弃一些已知的回报信息，而去尝试一些新的选择。
        * 利用：根据已知的信息使回报最大化，充分利用现有的对于环境的认识。
     * 演化学习：一个受益于自然演化的大型启发式随机优化算法
       * 演化算法在模拟自然演化的过程中主要考虑了两个关键因素：
         * 变分再生产：从当前的解集中通过某种方法产生新的解集。
         * 优选：不断的通过优胜劣汰的策略去剔除当前表现不达标的解集。
       * 常见演化算法：
         * 遗传算法（GA）
         * 遗传规划（GP）
         * 演化策略（ES）  
 （11）假设空间
 
 （12）学习方法三要素
 （13）奥卡姆剃刀定理
 （14）没有免费的午餐定理
 

  
  ## 机器学习与人工智能的区别
  ## 机器学习和数据挖掘的关系
  ## 机器学习和统计学习的关系
  机器学习是统计学习减去模型和假设的检验。<br />
  统计学和机器学习也有各自更关心的领域，统计学关注自身，例如生存分析、空间分析等，而机器学习关注在线学习、流行学习和主动学习等。
  ## 大数据机器学习的特点
  ## 机器学习和深度学习的区别
  ## 深度学习方法和其它人工智能方法的共性和差异
  **人工智能可以大致分为3种学习方法：**
  * 一种是**基于规则**的系统，另一种是**经典的机器学习方法或系统，**还有一种是**表示学习方法或系统**。
  * 基于规则的系统
     * 它没有可学习的模块，输入的数据通过手工设计的程序，直接获取特征然后输出。
  * 经典的机器学习方法或系统
     * 数据输入后通过手工设计获得特征，然后经过特征映射获得输出。
  * 表示学习方法或系统
     * 分为两类：**一类是非深度学习方法，一类是深度学习方法**。基于非深度学习方法是通过特征获得的，然后通过特征映射输出；而基于深度学习方法，首先学习得到简单的特征，然后通过附加的层去学习得到更多抽象的特征，最后通过特征映射输出结果。
  ## 深层学习和浅层学习的区别
  ## 强化学习和监督学习的区别
  ## 强化学习和深度学习的区别
  
  
  
  
  
  
  
  
  
  
  
  
  
  
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


