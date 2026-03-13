# 🧬 基因组学中的机器学习魔法 (Machine Learning For Genomics)
### 🌟 序言 (Introduction)

现在的基因组数据正在像炸掉的实验室一样，呈指数级爆炸增长哦！💥 这种“数据超负荷”的情况，当然需要更厉害的魔法工具来捕捉数据里的细微灵光，这样我们才能做出超准的推理和决定呢！✨

虽然机器学习（ML）、深度学习（DL）还有 AI 酱都已经进化得非常成熟、完全可以胜任基因组学的解析任务了，但在很多地方（比如非洲），可爱的生信学子们由于缺乏实战机会，在这些黑科技上还存在一点点小小的“技能断层”呢。😢

所以呀，在这个小小的教程里，我们要一起学习机器学习的基础咒语，还要手把手教你如何把乱糟糟的基因数据转化成“魔法矩阵”进行建模！💪 虽然很多课程表里写了这些内容，但实际上大家都没怎么教，这样在向“数据科学”靠拢的生信浪潮里可是会吃亏的哦。

举个小小且真实的例子。在单细胞测序（scRNA-seq）这个神奇的微观世界里，我们不仅是在跟细胞打交道，更是在跟高维数据的“幻觉”捉迷藏。我们经常会遇到“三人三样”的困境。面对同一份数据，三位研究者分别得到了 10、12、17 个聚类结果。这种不一致性，往往就是算法对噪声分布产生的过度拟合（Over-fitting）。

1. 现象分析：为什么会多出 7 个“幽灵群”？
从模式识别的角度看，聚类算法（如 Leiden/Louvain）本质上是在图中寻找局部最优的模块化得分（Modularity Score）。

- 低分辨率（Resolution = 0.5）： 算法识别出 10 个主导分布，它们代表了能量最低、最稳定的细胞大类。

= 高分辨率（Resolution = 1.2）： 算法的“视力”变得过于尖锐。它不再关注数据的泛化能力（Generalization），而是开始“背诵”噪声。它将原本属于同一个高维流形（Manifold）的连续分布，强行切割成了 17 个碎片。

2. 警惕“小提琴图”的甜蜜陷阱
很多魔法学徒看到多出来的群，第一反应就是画个小提琴图（Violin Plot）。如果看到某个 Marker 基因在两个群之间有那么一点点高度差异，就兴奋地觉得发现了“新亚群”。

但是！大魔法师要注意了：单看小提琴图是会“被骗”的哦！(＞x＜)

- 分布的假象： 小提琴图只展示了边际分布。在统计学上，两个高度重叠的分布，由于抽样误差（Sampling Noise），在小提琴图上可能看起来像是有不同的“腰身”。

- 缺乏空间上下文： 小提琴图把细胞从它们原本的“流形家园”里拎了出来。即便两个簇在小提琴图上表达量有异，但如果在高维空间中它们是完全连通的（即没有明显的密度断层），那么这种差异可能只是细胞转录状态的连续波动，而不是真正的生物学分类差异。

3. 系统化分析：用机器学习思维“破幻”
要识别出哪些是“过拟合”产生的碎片，我们需要动用更高级的魔法：

- 流形连通性分析（PAGA）： 利用图论的方法，检查这些簇之间的连通强度。如果两个簇之间的边（Edges）非常密集，说明它们在流形上是连续的，强行拆分它们就是“过拟合”。

- 重采样验证（Bootstrapping）： 对数据进行多次随机抽样。如果那多出来的 7 个群在每次抽样中都“忽隐忽现”，那它们就是算法捕捉到的噪声，而非真实的信号。

- 轮廓系数（Silhouette Score）评估： 计算细胞与其所属簇的相似度 vs 与最近邻簇的相似度。如果大量细胞的 $s(i)$ 接近 0，说明界限极其模糊，聚类过头啦！

为了不让大家掉队（特别是顺手解决某人的困扰），本魔女决定帮大家一把，一起开启这段赛博生信之旅吧！✧(≖ ◡ ≖✿)

注：本项目参考/汉化自开源项目 [Machine Learning for Genomics](https://github.com/mbbu/MachineLearning4Genomics)，感谢原作者 Mbbu 的无私分享！🪄✨

### 🛠️ 学习能力值 (Competencies)

在这个小小的课程里，我们打算给各位探员传授以下核心能力哦 (可以去看看 ISCB 官方能力指南 呢)：

1.知识与技能储备：带你深度解锁科学探索的全过程，看清生信在其中扮演的超级英雄角色！🧬
2.理解与应用大爆发：教你在分子生物学、基因组学、医学或群体遗传学研究的战场上，灵活运用统计学、机器学习和数据科学的各种“奇妙算法”！📊
3.实战与落地：手把手教你掌握最适合本专业的命令行操作和脚本编写技能，变身赛博生信高手！💻
4.知识与管理：学会如何优雅地管理海量数据，让数据们乖乖听话不乱跑！🗄️

### 🎯 学习目标 (Learning Objectives)

为了达成上述这些超厉害的能力，各位探员在工作坊结束时应该能够：

1. **描述**机器学习在基因组学中的各种奇妙应用 🧬
2. **解释**各种机器学习原理，以及它们是如何变身为基因组学的强大助手的 🤖
3. **解释**应用于基因组机器学习的研究设计方法（也就是规划你的“魔法路径”啦！）📐
4. **熟练掌握**各种开源科学工具（比如 Jupyter Notebooks, Pandas, Conda），并了解它们如何支持生信研究的“时空复原术”（可重复性研究）！🧪
5. **认识** Python 中各种超好用的机器学习框架（也就是你的赛博魔法阵法包哦！）🐍


### 🎓 学习成果 (Learning Outcomes)

通过上述目标的修炼，各位探员将掌握以下核心技能：

1. **环境构筑术**：能够为基因组项目搭建 Jupyter 和 Conda 的机器学习环境，确保你的研究拥有像“时间回溯”一样的完美复现能力！🧪
2. **数据大变身**：能够将原始的基因组数据进行华丽转化，变成适合机器学习建模的“能量矩阵”！⚡
3. **精准定位**：能够对基因组数据进行探索性分析、特征工程和参数选择（就像在数据迷雾中精准定位目标的探员一样呢！）。🔍
4. **模型进化**：能够利用基因组数据开发并验证机器学习模型，成为真正掌控生命编码的建模高手！🤖

## 📜 课程目录 (Contents)

本课程被划分为若干个交互式魔法笔记（也就是讲座啦！）。

### 🧊 第一阶段：基础构建 (Session 1)

* [魔法笔记 01](https://www.google.com/search?q=Notebooks/01_Basic_Concepts.ipynb) 机器学习核心概念
* [模块 01 幻灯片](https://docs.google.com/presentation/d/1PhknhMdooQT860csFINj3IgxDDnkF-C3WKSI79CXdv4/edit?usp=sharing) 机器学习入门：初识魔法
* [模块 02 幻灯片](https://docs.google.com/presentation/d/130bKZj6bScQ9NGykzbUsjjoYbYsmJFAWnYRGzbf-S4U/edit?usp=sharing) 机器学习深潜：探寻更深层的咒语


* [魔法笔记 02](https://www.google.com/search?q=Notebooks/02_Linear_Regression.ipynb) 线性回归：预测未来的直线
* [模块 03 幻灯片](https://docs.google.com/presentation/d/16VhmU8YMTqHkUYXwOVapR88wFLRIIoHwqLQ6QhcD7LU/edit?usp=sharing) 线性回归入门：画出命运的曲线



### 🌳 第二阶段：森林与基因 (Session 2)

* [魔法笔记 03](https://www.google.com/search?q=Notebooks/03_RandomForest_DecisionTree.ipynb) 随机森林与决策树：在迷宫中寻找答案
* [魔法笔记 04](https://www.google.com/search?q=Intro-to-Python/04_Feature_Engineering_genomics.ipynb) 基因组学中的特征工程：提取生命的信号
* [模块 04 幻灯片](https://docs.google.com/presentation/d/1bZmmy2JcAWZf6RuwUZVccKSHvUSqL1SgdZ5RAO_vK7g/edit?usp=sharing) 决策树深意：逻辑的分叉口



### 💬 第三阶段：语言的秘密 (Session 3)

* [魔法笔记 05](https://www.google.com/search?q=Notebooks/05_Feature_Engineering_NLP.ipynb) 自然语言处理 (NLP) 特征工程实例：让机器听懂悄悄话

### 🔬 第四阶段：高维解构 (Session 4)

* [魔法笔记 06](https://www.google.com/search?q=Intro-to-Python/06_MachineLeaning_VCF.ipynb) 利用 VCF 输出进行机器学习：降维分析的艺术

顺手解决某人的困扰（实验室助手再次上线！）：

# 📓 Jupyter Notebooks 快速入门 (Quick Introduction)

在整个课程中，我们都会用到超级好用的 **Jupyter Notebooks** 哦！

## 🌟 简介 (Introduction)

Jupyter Notebook 是一个超棒的交互式计算环境，它能让研究员们编写出包含完整计算记录的“魔法笔记本”。这些笔记分享起来非常方便，里面可以装载各种宝贝：

* 实时运行的代码 🐍
* 交互式小部件
* 各种酷炫的图表 📊
* 叙述性文本（就是你现在看到的这种）
* 数学公式
* 图片、视频，应有尽有！🎬

悄悄告诉你，“Jupyter”其实是一个缩写，代表了它支持的三大主要魔法语言：**Ju**lia、**Py**thon 和 **R**。

对于赛博研究员来说，这种笔记本可以创建出“可重复”的研究文档。既然生信（Bioinformatics）是以数据为中心的，使用 Jupyter Notebook 就能大大增加研究的透明度，一起推动开放科学的发展吧！✨

## 🛠️ 前置准备 (Pre-requisites)

学习基因组学中的机器学习，需要探员你已经熟悉了 Python 和 Pandas 咒语。如果你觉得有点生疏，可以去看看 [Python4Bioinformatics](https://github.com/kipkurui/Python4Bioinformatics) 训练材料复习一下哟！

## 🚀 第一步 (First Steps)

### 安装 (Installation)

1. **下载 Miniconda**：根据你的操作系统，把这个小巧的工具下载到你的家目录：
* [下载地址](https://www.anaconda.com/download/)
* Linux 探员：`wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh`
* Mac 探员：`curl https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh`


2. **运行安装脚本**：
* Linux: `bash Miniconda3-latest-Linux-x86_64.sh`
* Mac: `bash Miniconda3-latest-MacOSX-x86_64.sh`


3. **跟随提示操作**：如果不确定的话，一路按回车接受默认设置（Defaults）就好啦！
4. **重启终端**：关掉窗口再重新打开。
5. **验证成功**：输入 `conda list`，如果你看到一长串安装包列表，那就说明魔法阵布置成功了！

如果系统提示找不到命令，你可以手动把路径添加进去：
`export PATH=~/miniconda3/bin:$PATH`

为了让你的实验可以完美复现，建议为你使用的包[创建一个 Conda 环境](https://conda.io/docs/user-guide/tasks/manage-environments.html)：
`conda create --name ml_genomics python jupyter`

**激活环境**：
`source activate ml_genomics`

环境准备好后，你可以安装更高级的 `jupyter lab`：
`conda install -c conda-forge jupyterlab` 或者用 `pip3 install jupyter`。

## 📖 如何利用本资源学习？ (How to learn)

先把 [MachineLearning4Genomics](https://github.com/mbbu/MachineLearning4Genomics) 仓库里的笔记本全部搬回家！最简单的办法就是在你的工作目录里运行：

```bash
git clone https://github.com/mbbu/MachineLearning4Genomics.git

```

或者使用下载大法：

```bash
wget https://github.com/mbbu/MachineLearning4Genomics/archive/master.zip
unzip master.zip
rm master.zip
cd MachineLearning4Genomics-master

```

最后，输入咒语启动实验室界面：
`jupyter lab`

---

*注：Jupyter Notebook 由许多“单元格（Cell）”组成。点击单元格并按下 `Shift + Enter`，就能执行里面的 Python 代码啦！快去试试吧！(๑•̀ㅂ•́)و✧*

### 📚 进阶宝库 (Resources to use)

想要让你的魔法等级再提升一个档次？这些珍贵的卷轴（资源）一定能帮到你哦：

1. [DNA 编码入门](https://medium.com/mlearning-ai/apply-machine-learning-algorithms-for-genomics-data-classification-132972933723)
2. [生信中的机器学习：基因组地理学](https://towardsdatascience.com/machine-learning-in-bioinformatics-genome-geography-d1b1dbbfb4c2)：从原始测序读段到机器学习模型，教你如何根据基因变异来推断一个人的地理起源在哪里哦！🌍
3. [基因组学深度学习实战 (Colab)](https://colab.research.google.com/github/TankMermaid/1000-genomes-genetic-maps/blob/master/A_Primer_on_Deep_Learning_in_Genomics_Public.ipynb#scrollTo=bzsbNHqWiFek)
4. [基因组学机器学习指南](https://towardsdatascience.com/machine-learning-for-genomics-c02270a51795)：手把手教你如何对基因组数据进行“大变身”，让它们完美适配各种机器学习模型！✨
5. [向善的机器学习开源项目](https://github.com/DeltaAnalytics/machine_learning_for_good)
6. [探索生信与机器学习的奇妙世界](https://www.theaidream.com/post/explore-the-world-of-bioinformatics-with-machine-learning)
7. [基因组学特征工程 - 变异检测篇](https://towardsdatascience.com/machine-learning-in-bioinformatics-genome-geography-d1b1dbbfb4c2)
8. [用于基因组分类的机器学习咒语](https://medium.com/mlearning-ai/apply-machine-learning-algorithms-for-genomics-data-classification-132972933723)
9. [支持向量机 (SVM) 的奥秘](https://towardsdatascience.com/https-medium-com-pupalerushikesh-svm-f4b42800e989)
10. [机器学习背后的数学魔法书 (PDF)](https://mml-book.github.io/book/mml-book.pdf)
11. [深度学习圣经 - 机器学习基础章](https://www.deeplearningbook.org/contents/ml.html)

* [DNA 序列机器学习 GitHub 仓库](https://github.com/nageshsinghc4/DNA-Sequence-Machine-learning)

如果你想寻找更多实验素材（数据集）或者在修炼之路上走得更远，快来 [使用 Kaggle](https://www.kaggle.com/nageshsingh/classification-of-cancer) 开启新大陆吧！🏆

## 📜 许可证 (License)

本作品采用 [知识共享署名 4.0 国际许可协议 (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/) 进行许可。

只要你记得标注原作者的劳动成果，就可以自由地分享和魔改这些内容啦！希望你在赛博生信的世界里玩得开心！(๑•̀ㅂ•́)و✧
