+ 機率公理三元體

第一要素為樣本空間 S，是樣本點 s 的全體，根據問題需要事先取定；

第二要素為事件場, 是 S 中某些滿足下列條件的子集的全體所組成的集類:

[[math type="eqnarray"]]
(1)  & & S \in F； \\
(2)  & & 若 A \in F, 則 \bar{A} \in F;\\
(3)  & & 若 A \in F, B \in F 則 A \cup B \in F;\\
[[/math]]

第三要素為機率公理

[[math type="eqnarray"]]
(1)  & & P(S) = 1 \\
(2)  & & P(A) \ge 0 \\
(3)  & & P(A1 \cup A2) = P(A1) + P(A2) \; ; \; if \; A1 \cap A2 = \emptyset \\
[[/math]]

三元體 (S, F, P) 就構成一個概率空間 (probability space)。

+ 概率測度的連續性.

單調遞增極限事件：

> 在概率空間（S, F , P）中，假如有一單調遞增的事件序列 [[ ![](../timg/bd0a6ce42df6.jpg) ]]，則我們可以定義 [[ ![](../timg/8aab4b987dcb.jpg) ]] ，根據「機率公理三元體」的公理體系，A 仍然是一個事件。

單調遞減極限事件：

> 在概率空間（S, F , P）中，假如有一單調遞減的事件序列 [[ ![](../timg/c42e968135ec.jpg) ]]，則我們可以定義 [[ ![](../timg/8aab4b987dcb.jpg) ]] ，根據「機率公理三元體」的公理體系，A 仍然是一個事件。

連續性定理：
[[math]]
P(A) = \lim_{n \to \infty} P(A_n)
[[/math]]

由於連續性定理，我們可以將高等微積分的那些概念引入到機率理論體系中。

+ 參考文獻
# 波雷爾集 (borel set) -- http://en.wikipedia.org/wiki/Borel_set
# [http://zh.wikipedia.org/wiki/Sigma_%E4%BB%A3%E6%95%B0 維基百科：σ代數]
# [http://zh.wikipedia.org/wiki/%E6%B5%8B%E5%BA%A6%E8%AE%BA 測度論]
# http://en.wikipedia.org/wiki/Measure_(mathematics)
# §3  概率的公理化定义 -- http://www.math.zju.edu.cn/Probability/course/chapter1-3.htm
> 重點摘要：概率论起源于古代赌博游戏. 但概率的数学模型的提出普遍归功于法国数学家巴斯卡（Pascal， 1623-1662）和费马（Fermat， 1601-1655）.他们通过书信讨论有关掷骰子游戏的数学问题，利用排列组合方法精确计算出某些问题的概率，同时创立了关于排列、组合、二项系数等理论. 此后，由于贝努里（Bernoulli， 1654-1705）、德莫佛（De Moivre 1667-1754）、 贝叶斯(Bayes)、薄丰(Buffon)、勒让德(Legendre)，拉格朗日（Lagrange）等人的工作，概率论的内容逐渐丰富，到拉普拉斯（Laplace 1749-1827）时所谓古典概率论的结构已基本完成， 《分析概率论》(1812)是其集大成之作. 有关概率的统计或经验的观点主要是由费歇尔(Fisher)、冯-迈思(Von-Mises)发展起来的. 冯-迈思的样本空间概念最终使得人们可以基于测度观点来发展概率数学理论. 现代概率论的公理化体系于20世纪30年代由苏联数学家柯尔莫格洛夫(Kolmogorov,1903-1987)所创立. 这不仅对论述无限随机试验序列或一般的随机过程给出了足够的逻辑基础，而且也极大地促进了数理统计理论的发展.