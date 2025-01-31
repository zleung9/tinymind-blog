---
title: OpenAI-o1真的会思考吗
tags:
  - 人工智能
id: '1125'
categories:
  - - Article
date: 2024-09-15 22:41:01
---

_在OpenAI的眼中，实现通用人工智能大致要经历5个阶段：对话(conversation)，推理(reasoning)，代理(agent)，创新(innovation)，组织(organization)。OpenAI的o1模型已经达到了推理这一阶段，相信第三阶段也指日可待。在它到达第四阶段—创新—之前，个人认为还需要达到”直觉“这个阶段。_

OpenAI在上周推出了最新的模型o1-preview。名字的含义是Orion（猎户座）一代。有人说计数器重置为1，因此很可能不会有GPT-5，o1将开启一个全新的时代。  
很多人对o1模型能力进行了解读，也有大量的新奇的应用如雨后春笋一般涌现出来，总得来说o1是思维链(Chain of Thought, COT)的集大成者，它很可能推动LLM新一轮的范式改变：侧重点从训练到推理转移，然后以推理时间的增长来继续scaling law。但是它真的会“思考”吗？

# o1模型本质上就是把思维链内化

o1本质上就是把思维链（COT）内化。之前需要依赖人工写COT来指导LLM接近正确答案，现在OpenAI的把COT隐匿地训练到了o1的内部。就像AlphaGo下棋，形成了巨大的树形搜索空间，相当于一条条COT构成的空间，这里COT的具体步骤的组会空间是巨大的，人写的COT未必是最优的。问题越复杂，这个树的搜索空间就越大，搜索复杂度就越高，找到正确答案涉及到的COT步聚越多。  
这一突破意味着复杂的提示词工程(Prompt Engineering)可能会逐渐淡出舞台。未来,用户无需再构造繁琐的提示词,AI系统将能够自主生成最适合的思维过程,这无疑是向着更高度智能化迈进的一大步。

# **从训练到推理的转变**

简单的来说，OpenAI o1 系列模型，在复杂推理上的性能提升模式**与传统 LLM 预训练式的性能提升不同**，主要**通过强化学习的方式，让模型不断完善思考过程**，包括对不同策略进行尝试，认识到错误等。这个过程是推理阶段完成的  
因此，我们应该有两种方式来增加能力：在训练期间以及在推理期间。这实际上对Nvidia的竞争对手如Groq和SambaNova Systems来说是一个利好信号，因为他们有更多机会在推理计算方面竞争，而在训练计算方面几乎没有机会竞争。

# **o1会思考吗**

人类的物理数学大师一定程度上是不是因为他们计算能力强，解决具体问题的逻辑能力强，而是他们的强大的“直觉”。物理学中有很多奠基性的理论，都是物理学家先有了答案，然后再回头去证明和推理心中的那个答案。他们的答案是如何来的呢？这就是大师们的“直觉”。

> A mathematician is a person who can find analogies between theorems; a better mathematician is one who can see analogies between proofs and the best mathematician can notice analogies between theories. One can imagine that the ultimate mathematician is one who can see analogies between analogies.  
> \----- Stefan Banach

LLM的预训练所得的是对一种简单规则的“直觉”。以前我们通过大量的数据，让LLM抽象出了数据背后最一般的映射，也就是规则，比如语言里的语法，一些简单的数学规则（基于统计意义上的）。但是很多复杂问题是多个简单规则的嵌套，这时候LLM就力不从心了，因为它无法通过“死记硬背”的方法来学会这些规则组合。现在我们有o1模型，可以借助COT来解决这些问题。这时COT有点像人类的逻辑思考，或者Reasoning。近一步想，如果通过大量的COT作为数据，是不是可以训练出对复杂问题的“直觉”呢？这个时候的LLM是不是就更像一个科学家那样“思考了”？