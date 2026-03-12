# 🧬 基因组学中的机器学习魔法 (Machine Learning For Genomics)
### 🌟 序言 (Introduction)

现在的基因组数据正在像炸掉的实验室一样，呈指数级爆炸增长哦！💥 这种“数据超负荷”的情况，当然需要更厉害的魔法工具来捕捉数据里的细微灵光，这样我们才能做出超准的推理和决定呢！✨

虽然机器学习（ML）、深度学习（DL）还有 AI 酱都已经进化得非常成熟、完全可以胜任基因组学的解析任务了，但在很多地方（比如非洲），可爱的生信学子们由于缺乏实战机会，在这些黑科技上还存在一点点小小的“技能断层”呢。😢

所以呀，在这个小小的教程里，我们要一起学习机器学习的基础咒语，还要手把手教你如何把乱糟糟的基因数据转化成“魔法矩阵”进行建模！💪 虽然很多课程表里写了这些内容，但实际上大家都没怎么教，这样在向“数据科学”靠拢的生信浪潮里可是会吃亏的哦。

为了不让大家掉队（特别是顺手解决某人的困扰），本实验室助手决定帮大家一把，一起开启这段赛博生信之旅吧！✧(≖ ◡ ≖✿)

### 🛠️ 学习能力值 (Competencies)

在这个小小的课程里，我们打算给各位探员传授以下核心能力哦 (可以去看看 ISCB 官方能力指南 呢)：

1.知识与技能储备：带你深度解锁科学探索的全过程，看清生信在其中扮演的超级英雄角色！🧬

2.理解与应用大爆发：教你在分子生物学、基因组学、医学或群体遗传学研究的战场上，灵活运用统计学、机器学习和数据科学的各种“奇妙算法”！📊

3.实战与落地：手把手教你掌握最适合本专业的命令行操作和脚本编写技能，变身赛博生信高手！💻

4.知识与管理：学会如何优雅地管理海量数据，让数据们乖乖听话不乱跑！🗄️

### Learning Objectives
To attain the above competencies, the workshop participants should be able to:
1. Describe the application of machine learning in genomics
2. Explain the various machine learning principles and how they can be applied to genomics
3. Explain the research design approaches as applied to machine learning for genomics
4. Know the various open science tools (Jupyter Notebooks, Pandas, Conda)and how they support a reproducible bioinformatics research
5. Know the various machine learning frameworks in Python


### Learning Outcomes
From the above objectives, the workshop participant should acquire the following skills;
1. Be able to set up Jupyter and Conda environments for machine learning for a genomic project to ensure reproducibility
2. Be able to transform genomic data for machine learning modelling
3. Be able to perform exploratory analysis on genomic data, feature engineering, and parameter selection
4. Be able to develop and validate machine learning models using genomic data

### Instructors
1. Caleb Kibet
2. 

### Who should attend?

EANBiT Fellows

## Contents

This course is broken up into several notebooks (lectures).

### Session 1
* [Notebook_01](Notebooks/01_Basic_Concepts.ipynb) Machine learning Concepts 
    * [Module_01_Slides](https://docs.google.com/presentation/d/1PhknhMdooQT860csFINj3IgxDDnkF-C3WKSI79CXdv4/edit?usp=sharing) Introduction to machine learning
    * [Module_02_Slides](https://docs.google.com/presentation/d/130bKZj6bScQ9NGykzbUsjjoYbYsmJFAWnYRGzbf-S4U/edit?usp=sharing) Machine Leaning Deep Dive

* [Notebook_02](Notebooks/02_Linear_Regression.ipynb) Linear regression
    * [Module 03_Slides](https://docs.google.com/presentation/d/16VhmU8YMTqHkUYXwOVapR88wFLRIIoHwqLQ6QhcD7LU/edit?usp=sharing) Introduction to Linear Regression


### Session 2
* [Notebook_03](Notebooks/03_RandomForest_DecisionTree.ipynb) Random Forest and Decision Trees
* [Notebook_04](Intro-to-Python/04_Feature_Engineering_genomics.ipynb) Feature Engineering in Genomics
    * [Module_04_Slides](https://docs.google.com/presentation/d/1bZmmy2JcAWZf6RuwUZVccKSHvUSqL1SgdZ5RAO_vK7g/edit?usp=sharing) Decision Trees


### Session 3
* [Notebook_05](Notebooks/05_Feature_Engineering_NLP.ipynb) Feature Engineering Example using NLP


### Session 4
* [Notebook_06](Intro-to-Python/06_MachineLeaning_VCF.ipynb) Machine Learning Using VCF output: Dimensionality Reduction

# Quick Introduction to Jupyter Notebooks

Throughout this course, we will be using Jupyter Notebooks. 

## Introduction
The Jupyter Notebook is an interactive computing environment that enables users to author notebooks, which contain a complete and self-contained record of a computation. These notebooks can be shared more efficiently. The notebooks may contain:
* Live code
* Interactive widgets
* Plots
* Narrative text
* Equations
* Images
* Video

It is good to note that "Jupyter" is a loose acronym meaning Julia, Python, and R; the primary languages supported by Jupyter. 

The notebook can allow a computational researcher to create reproducible documentation of their research. As Bioinformatics is datacentric, the use of Jupyter Notebooks increases research transparency, hence promoting open science. 

## Pre-requisites
Machine learning for genomics assumes familiarity with Python and Pandas. Please have a look at the [Python4Bioinformatics](https://github.com/kipkurui/Python4Bioinformatics) training materials for a refresher. 

## First Steps

### Installation

1. [Download Miniconda](https://www.anaconda.com/download/) for your specific OS to your home directory
    - Linux: `wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh`
    - Mac: `curl https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh`
2. Run:
    - `bash Miniconda3-latest-Linux-x86_64.sh`
    - `bash Miniconda3-latest-MacOSX-x86_64.sh`
3. Follow all the prompts: if unsure, accept defaults
4. Close and re-open your terminal
5. If the installation is successful, you should see a list of installed packages with
    - `conda list`

If the command cannot be found, you can add the Anaconda bin to the path using:
    `export PATH=~/miniconda3/bin:$PATH`

For reproducible analysis, you can [create a conda environment](https://conda.io/docs/user-guide/tasks/manage-environments.html) with all the Python packages you used.

    `conda create --name ml_genomics python jupyter`
    
To activate the conda environment:

    `source activate ml_genomics`

Having set-up conda environment, you can install `jupyter lab` using pip. 

`conda install -c conda-forge jupyterlab`

or by using pip

`pip3 install jupyter`

## How to learn from this resource?

Download all the notebooks from [MachineLearning4Genomics](https://github.com/mbbu/MachineLearning4Genomics). The easiest way to do that is to clone the GitHub repository to your working directory using any of the following commands:

    git clone https://github.com/mbbu/MachineLearning4Genomics.git

or

    wget https://github.com/mbbu/MachineLearning4Genomics/archive/master.zip
    
    unzip master.zip
    
    rm master.zip
    
    cd MachineLearning4Genomics-master
    
Then you can quickly launch jupyter lab using:

`jupyter lab`

NB: We will use a jupyter lab for training. 
A Jupyter notebook is made up of many cells. Each cell can contain Python code. You can execute a cell by clicking on it and pressing `Shift-Enter` or `Ctrl-Enter` (run without moving to the next line). 


### Resources to use:

1. [Encoding DNA ](https://medium.com/mlearning-ai/apply-machine-learning-algorithms-for-genomics-data-classification-132972933723)
2. [Machine Learning in Bioinformatics: Genome Geography:](https://towardsdatascience.com/machine-learning-in-bioinformatics-genome-geography-d1b1dbbfb4c2)From raw sequencing reads to a machine learning model, which infers an individual's geographical origin based on their genomic variation.
3. [Deep Learning for Genomics](https://colab.research.google.com/github/TankMermaid/1000-genomes-genetic-maps/blob/master/A_Primer_on_Deep_Learning_in_Genomics_Public.ipynb#scrollTo=bzsbNHqWiFek)
4. [Machine Learning for Genomics](https://towardsdatascience.com/machine-learning-for-genomics-c02270a51795). How to transform your genomics data to fit into machine learning models. 
5. [Machine Learning For Good](https://github.com/DeltaAnalytics/machine_learning_for_good)

6. [Machine Leaning in Bioinformatics](https://www.theaidream.com/post/explore-the-world-of-bioinformatics-with-machine-learning)

7. [Feature Engineering in Genomics - Variant calling](https://towardsdatascience.com/machine-learning-in-bioinformatics-genome-geography-d1b1dbbfb4c2)

8. [Machine leaning for genomic classification](https://medium.com/mlearning-ai/apply-machine-learning-algorithms-for-genomics-data-classification-132972933723)

9. [Support Vector Machines](https://towardsdatascience.com/https-medium-com-pupalerushikesh-svm-f4b42800e989)

10. [Mathematics For Machine Learning](https://mml-book.github.io/book/mml-book.pdf)
11. [Deep Learning Book - Machine Learning Chapter](https://www.deeplearningbook.org/contents/ml.html)

- https://github.com/nageshsinghc4/DNA-Sequence-Machine-learning

To Find datasets and get learning even further, [use Kaggle](https://www.kaggle.com/nageshsingh/classification-of-cancer)


## How to Contribute

To contribute, fork the repository, make some updates and send me a pull request. 

Alternatively, you can open an issue. 

## License
This work is licensed under the Creative Commons Attribution 4.0 Unported License. To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/
