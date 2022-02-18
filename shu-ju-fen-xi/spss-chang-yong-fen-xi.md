# SPSS常用分析

### 描述性分析

**频数分析**

频数分析是对一组数据的不同数值的频数，或者数据落入指定区域内的频数进行统计，了解其数据分布状况的方式。通过频数分析，能在一定程度上反映出样本是否具有总体代表性，抽样是否存在系统偏差，并以此证明以后相关问题分析的代表性和可信性。

**描述性统计**

描述性统计分析是对调查总体所有变量的有关数据进行统计性描述，包括数据的集中趋势与离散趋势

**分类汇总**

根据定类变量分类进行汇总（按照某一标准进行分类，然后在分完类的基础上对各类别相关数据分别进行求和、求平均数、求个数、求最大值、求最小值等方法的汇总。又名列联表分析）

**正态性分析**

正态性检验用于检验数据是否满足正态分布，一些算法需要数据满足正态分布（如单样本 t 检验，独立样本 t 检验等）

**相关性分析**

相关分析是对变量两两之间的相关程度进行分析。相关分析的计算方式有三种，分别是 Pearson 相关系数（适用于定量数据，且数据满足正态分布）、Spearman 相关系数（数据不满足正态分布时使用）。Kendall's tau -b 相关系数（有序定类变量）

### 差异性分析

#### 参数检验

**方差分析**

方差分析（单因素方差分析或 F 检验）用于定类字段（X）与 1 个或 1 个以上的定量字段（Y）之间的差异性研究。需要注意的是，一个定类字段称为单因素方差分析，两个定类字段及以上称为多因素方差分析，与独立样本 T 检验不同的是，方差分析可用于多分类定类字段数据的差异性分析，T 检验只能作用于二分类定类变量

**独立样本t检验**

独立样本 t 检验用于分析一个定类变量与一个或者多个定量变量之间有无明显差异，需要特别注意的是，该定类变量为二分类变量（三分类及以上使用方差分析），各分类频数可以不相等

#### 非参数检验

**卡方检验**

卡方检验（Pearson 卡方检验）主要是比较定类变量与定类变量之间的差异性分析。通过统计样本的实际观测值与理论推断值之间的偏离程度，实际观测值与理论推断值之间的偏离程度就决定卡方值的大小，如果卡方值越大，二者偏差程度越大；反之，二者偏差越小；若两个值完全相等时，卡方值就为 0，表明理论值完全符合

### 统计建模&#x20;

**线性回归（最小二乘法）**

线性回归是利用数理统计中回归分析，来确定两种或两种以上变量间相互依赖的定量关系的一种统计分析方法，在线性回归分析中，只包括一个自变量和一个因变量，且二者的关系可用一条直线近似表示，这种回归分析称为一元线性回归分析。如果回归分析中包括两个或两个以上的自变量，且因变量和自变量之间是线性关系，则称为多元线性回归分析。

**主成分分析（PCA）**

主成分分析将多个有一定相关性的指标进行线性组合，以最少的维度解释原数据中尽可能多的信息为目标进行降维，降维后的各变量间彼此线性无关，最终确定的新变量是原始变量的线性组合，且越往后主成分在方差中的比重也小，综合原信息的能力越弱，与因子分析不同的是，因子分析是利用少数几个公共因子去解释较多个要观测变量中存在的关系，它不是对原始变量的重新组合。

**因子分析（探索性）**

因子分析是基于降维的思想，在尽可能不损失或者少损失原始数据信息的情况下，将错综复杂的众多变量聚合成少数几个独立的公共因子，这几个公共因子可以反映原来众多变量的主要信息，在减少变量个数的同时，又反映了变量之间的内在联系。通常因子分析有三种作用：一是用于因子降维，二是计算因子权重，三是计算加权计算因子汇总综合得分

**岭回归**

岭回归是一种专用于共线性数据分析的有偏估计回归方法，实质上是一种改良的最小二乘估计法，通过放弃最小二乘法的无偏性，以损失部分信息、降低精度为代价获得回归系数更为符合实际、更可靠的回归方法，对病态数据的拟合要强于最小二乘法。

**单位根检验（ADF）**

在使用很多时间序列模型的时候，如 ARMA、ARIMA，都会要求时间序列是平稳的，所以一般在研究一段时间序列的时候，第一步都需要进行平稳性检验，除了用肉眼检测的方法，另外比较常用的严格的统计检验方法就是 ADF 检验，也叫做单位根检验。单位根检验是指检验序列中是否存在单位根，因为存在单位根就是非平稳时间序列了。

**差分分析**

差分，本质上就是下一个数值减去上一个数值，主要是消除一些波动使数据趋于平稳，非平稳序列可通过差分变换转化为平稳序列

**（偏）自相关分析（acf/pacf）**

自相关（ACF）是指序列与其自身经过某些阶数滞后形成的序列之间存在某种程度的相关性，而偏自相关函数（PACF）是在其他序列给定情况下的两序列条件相关性的度量函数。一般来说（偏）自相关用于时间序列分析 AR、MA 的 p、q 进行定阶

**时间序列模型(ARIMA)**

ARIMA 模型的全称叫做自回归移动平均模型，是统计模型中最常见的一种用来进行时间序列预测的模型

### 问卷分析

**信度分析**

信度分析主要用来考察问卷中量表所测结果的稳定性以及一致性，即用于检验问卷中量表样本是否可靠可信。量表题型就是问题的选项，是分陈述等级进行设置的。比如我们对手机的喜爱从非常喜欢到不喜欢这个程度的变化。在量表里面最出名的就是李克特 5 级量表，在这种量表的选项里面主要是分为'非常同意'、'同意'、'不一定'、'不同意'、'非常不同意'五种回答，分别记为 5、4、3、2、1

**效度分析**

效度分析通常是指问卷量表的有效性和正确性，即分析问卷题目的设计是否合理。问卷的效度分析是基于主成分因子分析实现的，通过比较题项的因子载荷系数是否在同一主成分表现最优而实现。

**多选分析**

多选题分析是针对问卷调研设计的一种分析多选题的比例情况和普及情况的模型。多选题一般一个选项是单独的一个标题，比如5个选项就有5个标题，多选题分析就是用于分析调研用户对多选题各个题项的选择比例。

**权重分析(熵权法)**

权重分析是通过熵权法对问卷调查的指标的重要性进行权重输出，根据信息熵的定义，对于某项指标，可以用熵值来判断某个指标的离散程度，其信息熵值越小，指标的离散程度越大， 该指标对综合评价的影响（即权重）就越大，如果某项指标的值全部相等，则该指标在综合评价中不起作用。因此，可利用信息熵这个工具，计算出各个指标的权重，为多指标综合评价提供依据。

**验证性因子分析**

验证性因子分析（confirmatory factor analysis, CFA）是用于测试一个因子与相对应的测度项之间的关系是否符合研究者所设计的理论关系的一种研究方法,可用于调查问卷的量表分析。

**组内相关系数**

组内相关系数(ICC)是衡量和评价观察者间信度和复测信度的信度系数指标。通常可以用于问卷调查中评价一个对象对多个样本在一段时间的重测信度，或者判断一批对象对多个样本的一致性检验。

**对应分析**

对应分析，又称为R-Q型因子分析，适用于有多个类别的分类变量，可以揭示同一个变量各个类别之间的差异，以及不同变量各个类别之间的对应关系，与卡方检验不同的是，对应分析不单单展示了不同分组的差异性，也能通过2维、3维的方式展示其在空间的关系。

**区分度分析**

区分度分析是利用独立样本T检验对问卷数据收集时是否存在差异性进而研究区分度的一种方法。其原理为，对分析项求和【如品牌的潮流度打分，价格打分，舒适度打分】，然后将平均数据分成三部分按37分或者其他比例分别分为低分组，中分组和高分组，然后使用独立样本t 检验去对比各分组之间是否有着明显的差异，如果具有明显的差异，则说明具有良好的区分性。

### 量化分析&#x20;

**秩和比综合评价法(RSR)**

秩和比（RSR）指将效益型指标从小到大排序进行排名、成本型指标从大到小排序进行排名，再计算秩和比，最后统计回归、分档排序。通过秩转换，获得无量纲统计量 RSR，以 RSR 值对评价对象的优劣直接排序或分档排序，从而对评价对象做出综合评价。

**优劣解距离法（TOPSIS)**

TOPSIS 法是一种常用的组内综合评价方法，能充分利用原始数据的信息，其结果能精确地反映各评价方案之间的差距。基本过程为基于归一化后的原始数据矩阵，采用余弦法找出有限方案中的最优方案和最劣方案，然后分别计算各评价对象与最优方案和最劣方案间的距离，获得各评价对象与最优方案的相对接近程度，以此作为评价优劣的依据。该方法对数据分布及样本含量没有严格限制，数据计算简单易行。

**模糊综合评价**

模糊综合评价借助模糊数学的一些概念，对实际的综合评价问题提供评价，即模糊综合评价以模糊数学为基础，应用模糊关系合成原理，将一些边界不清、不易定量的因素定量化，进而进行综合性评价的一种方法。

**灰色关联分析**

对于两个系统之间的因素，其随时间或不同对象而变化的关联性大小的量度，称为关联度。在系统发展过程中，若两个因素变化的趋势具有一致性，即同步变化程度较高，即可谓二者关联程度较高；反之，则较低。因此，灰色关联分析是指对一个系统发展变化态势的定量描述和比较的方法，其基本思想是通过确定参考数据列和若干个比较数据列的几何形状相似程度来判断其联系是否紧密，它反映了曲线间的关联程度。

**耦合协调度**

耦合协调度模型用于分析事物的协调发展水平。耦合度指两个或两个以上系统之间的相互作用影响，实现协调发展的动态关联关系，可以反映系统之间的相互依赖相互制约程度。协调度指耦合相互作用关系中良性耦合程度的大小，它可体现出协调状况的好坏。

**层次分析法（简化版）**

层次分析法是一种解决多目标的复杂问题的定性与定量相结合的决策分析方法。该方法将定量分析与定性分析结合起来，用决策者的经验判断各衡量目标之间能否实现的标准之间的相对重要程度，例如通过构建评价指标（景色、费用，居住，饮食、旅途）对候选旅游地（桂林、黄山，北戴河）量化评价，进行选择。简化版里面，SPSSPRO舍弃了对方案层的层次总排序，如需层次总排序，敬请期待SPSSPRO-层次分析法（专业版）