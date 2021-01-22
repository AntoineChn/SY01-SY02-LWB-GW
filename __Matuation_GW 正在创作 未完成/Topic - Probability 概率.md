<!-- ------------ General Header Template 0.3.6 ------------ -->
- Metadata :
	- 🆔 Zettelkasten_ID : 20210120224533
	- 🗺 Index : [[Wikiversity 🎓  - 🎲 Probability thoery 概率论 (占坑)]]

Created : [[2021-01-20 Wednesday]]

***************************************************************

# Topic - Probability 概率

## Summary - 概述

概率论 是  研究 不确定事件的 一套数学理论. 
概率 从数学上, 是一个 满足一些 特殊条件 (这些 条件 被称为 概率公理 ) 的 映射

- **从直觉上**, 如果我们有一个 结果带有随机性的 实验,  众多结果中 "某一结果的概率" 可以被看做 是 长期重复 这个实验 这个结果 出现的频率
	- 然而, 这种对于"概率" 基于"频率"的 认知, 可能会造成 一些 困扰. 比如, 对于 无法重复的 带有随机性的试验, 例如, 明天的天气 则 没有办法 解释
- **从数学上**, 概率 是 [[Sample space 样本空间|样本空间 (sample space)]] 的 满足一些 条件的 映射.

## Context - 预备知识

这个主题 需要的预备知识 有

- [[Topic - Set 集合]]
	- [[Power set 幂集]]
	- [[Binary relation#Binary relation 二元关系|Binary relation 二元关系]], 集合的 包含关系,  
	- [[Mathematical structure 数学结构|数学结构 (Mathematical structure)]]
- [[Topic - Map 映射]]
- [[Topic - Measure theory 测度论 (仅讨论部分知识点)]]
	- [[σ-algebra σ-代数|σ-代数 (σ-algebra)]]

```mermaid
flowchart TB
	s[集合];
	ss([子集]);
	es([空集]);
	sOfSs([子集系])
	ps([幂集]);
	br([二元关系])
	is_ss([包含关系])
	is_disjoint([互斥关系])
	por([偏序关系]);
	ma[映射];
	cs([可数集]);
	compl_s([补集运算])
	union_s([并集运算])
	inter_s([交集运算])
	bo([二元运算]);
	tribu([σ-代数]);
	g_tribu([张成 σ-代数]);	
	
	s --> ss
	s-->es
    ss --> sOfSs
	is_ss --> sOfSs
	
	subgraph 特殊的 集合
		ss & es 
		sOfSs & ps
	end
	
	s --> is_ss 
	ma-->br
	
	br-->por
	por  --> is_ss 
	br --> is_disjoint	
	subgraph 集合的二元关系
		is_ss
		is_disjoint
	end
	
	sOfSs-->ps
	ma-->bo
	inter_s & es --> is_disjoint
	
	s-->ma-->cs
	bo --> union_s & inter_s & compl_s
	subgraph 集合的二元运算
		union_s & inter_s & compl_s
	end
	
	is_disjoint & sOfSs & union_s & cs -->  tribu
	is_ss --> g_tribu	

	subgraph 测度论
		tribu --> g_tribu
	end
```

## Goals - 学习目标

```mermaid
flowchart TB
	s[集合];
	re([随机试验]);
	ef([基础事件])
	sample_space([样本空间]);
	tribu([σ-代数]);
	pm[概率测度];
	pOfEvent([随机事件的 概率分布]);
	Equiprobabilit([等概率模型 - 古典概型])
	cond([条件概率])
	indep([独立事件])
	total_forumla([全概率公式])
	chain([复合概率公式 - 链式法则])
	bayes([贝叶斯公式])
	rva[随机变量];
	ma[映射];
	drv([随机变量的 概率分布]);
	etc([etc. 见 topic - 随机变量])
		 
	s --> tribu
	s --> sample_space
	tribu --> pm --> drv
	sample_space  --> rva
	
	subgraph Topic - Probability
		re --> ef
		ef  --> sample_space
		pm --> pOfEvent 
		sample_space --> pOfEvent 
		pOfEvent --> cond & indep
		pOfEvent --> Equiprobabilit
	
		subgraph 条件概率 与 独立事件
			 cond & indep
			 cond --> total_forumla --> bayes
			 cond --> chain
		 end
		 
	 end

	ma  --> rva
	subgraph Topic - 随机变量
		rva --> drv --> etc
	end

```

-   了解 样本空间 (sample space) and 随机事件 (events)
-   了解 概率公理 (axioms of probability)
-   有限概率空间 (finite probability spaces)
-   了解 概率 在生产生活中的 两种 直观解读 :
	-   某一个 可重复发生的 随机事件 某结果发生的 (客观的) **频率** (objective frequency)
	-   某一个 可重复发生的 (或 不可重复发生的) 随机事件 某一结果 出现与否的 (主观的) 信任程度 (subjective belief)

## Core notes - 核心笔记

- [[Probability measure 概率测度#Probability 概率|Probability measure 概率测度]]
- [[Experiment (Probability theory) 随机试验#Experiment 随机试验|Experiment (Probability theory) 随机试验]]
	- [[Event (Probability theory) 概率事件#Event Probability theory 概率事件|Event (Probability theory) 随机事件]]
	- [[Sample space 样本空间#Sample space 样本空间|Sample space 样本空间]]
- [[Conditional probability 条件概率 (占坑)#Conditional probability 条件概率|Conditional probability 条件概率]]
	- [[Formule des probabilités totales 全概率公式 (占坑)]]
	- [[Formule de Bayes 贝叶斯公式 (占坑)]]
	- [[Independence (Probability thoery) 独立性 (占坑)]]

## Supplemental notes - 补充笔记

- [[试验 Vs 实验]]: 随机试验 是什么 ?
- [[什么是直觉|直觉 (intuition)]]
	- [[违反直觉的 概率问题]]
- [[Paradoxe de Bertrand]]: Bertrand 悖论, 概率是主观的 还是客观的 ?

***************************************************************
***************************************************************
<!-- Placeholder for pandoc Exportation with BibTeX -->

## References 📚
