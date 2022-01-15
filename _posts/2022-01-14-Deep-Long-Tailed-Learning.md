---
title: Deep Long-Tailed Learning A Survey
date: 2022-01-15 8:12:00 +0800
categories: [Paper]
tags: [Review, Long-tailed Learning, Deep Learning, Imbalanced Learning, Re-sampling]
seo:
  date_modified: 2022-01-15 17:06:47 +0800

---

***link***: https://arxiv.org/pdf/2110.04596.pdf



> ABSTRACT

​		Long-tailed class imbalance, a common problem in practical visual recognition tasks, often limits the practicality of deep network based recognition models in real-world applications, since they can be <mark>easily biased towards dominant classes and perform poorly on tail classes</mark>. To address this problem, a large number of studies have been conducted in recent years, making promising progress in the field of deep long-tailed learning. Considering the rapid evolution of this field, this paper aims to provide a comprehensive survey on recent advances in deep long-tailed learning. To be specific, we group existing deep long-tailed learning studies into three main categories (<mark>i.e., class re-balancing, information augmentation and module improvement</mark>)



> 1. INTRODUCTION

​		In real-world applications, training samples typically exhibit a long-tailed class distribution, where a small portion of classes have massive sample points but the others are associated with only a few samples. (as shown in **Fig. 1**)

<img src="/home/whyk/snap/typora/46/.config/Typora/typora-user-images/image-20220115150132185.png" alt="image-20220115150132185" style="zoom:67%;" />

​		To address long-tailed class imbalance, massive deep long-tailed learning studies have been conducted in recent years, , we aim to provide a comprehensive survey for recent long-tailed learning studies conducted before mid-2021. As shown in **Fig. 2**, we group existing methods into three main categories based on their main technical contributions.



> 2. PROBLEM DEFINITION AND BASIC CONCEPTS

##### 2.1 Problem Definition

$$
\begin{align}
&\textrm{Long-tailed training set:}
\quad
\begin{Bmatrix}
x_{i}, y_{i}
\end{Bmatrix}^{n}_{i=1}
\qquad
\textrm{(where each sample}
\;x_{i}\;
\textrm{has a corresponding class label }
\;y_{i}
)
\\
&\textrm{Total number of training
set over K classes:}
\quad
n = \sum_{k=1}^n n_k
\qquad
\textrm{(where}
\;n_{k}\;
\textrm{denotes the data
number of class  }
\;k,\; )

\\
&n_{k}/n
\textrm{ indicates the label frequency of class k.}
\\
\\
&\textrm{classes are sorted by cardinality in
decreasing order ,
and then the imbalance ratio is defined as\;}
n1/nK.
\end{align}
$$

​		This task is challenging due to two difficulties:

- <mark>imbalanced data numbers across classes make deep models biased to head classes and performs poorly on tail classes.</mark>
- <mark>Lack of tail-class samples makes it further challenging to train models for tail-class classification. </mark>

##### 2.2 Datasets

<img src="/home/whyk/snap/typora/46/.config/Typora/typora-user-images/image-20220115161911543.png" alt="image-20220115161911543"  />

##### <del>2.3 Evaluation Metrics </del>

##### <del>2.4 Mainstream Network Backbones</del>

##### <del>2.5 Long-tailed Learning Challenges</del>

##### 2.6 Relationships with Other Tasks     

| Other Tasks                  | Relationships with Long-tailed learning                      |
| ---------------------------- | ------------------------------------------------------------ |
| Class-imbalanced learning    | class-imbalanced learning, the number of classes can be very small and <mark>the number of minority data is not necessarily small</mark>; while in long-tailed learning, there are a large number of classes and the tail-class samples are often very scarce. |
| Few-shot learning            | Few-shot train models from a <mark>limited number of labeled samples</mark>, while e tail classes generally have a very small number of samples |
| Out-of-domain Generalization | a class of tasks, in which the <mark>training distribution is inconsistent with the unknown test distribution.</mark> Such inconsistency includes inconsistent data marginal distributions, domain generalization, inconsistent class distributions . long-tailed is a part of inconsistent class distributions problem. |

> 3. CLASSIC METHODS

![image-20220115150414900](/home/whyk/snap/typora/46/.config/Typora/typora-user-images/image-20220115150414900.png)

##### 3.1 Class Re-balancing

3.1.1 Re-sampling

​		Re-sampling is one of the most widely-used methods to resolve class imbalance in the last few decades. The common practices of re-sampling are random over-sampling (ROS) and random under-sampling (RUS). 

| random over-sampling(ROS)                                    | random under-sampling(RUS)                    |
| ------------------------------------------------------------ | --------------------------------------------- |
| repeats the samples from tail classes                        | discards the samples from head classes        |
| overfit to tail classes when the classes are extremely skewed | degrade the model performance on head classes |

Instead of using random re-sampling, recent long-tailed learning studies develop various kinds of sampling methods, including <mark>class-balanced re-sampling</mark> and <mark>scheme-oriented sampling</mark>.

- Class-balanced re-sampling

  



























