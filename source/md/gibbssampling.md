+ 簡介

Gibbs 取樣程序的使用時機是在聯合分布 [[ ![](../timg/d3626f51831d.jpg) ]] 未知，但是單一變數的條件機率 [[ ![](../timg/b30a63ccb3eb.jpg) ]] 已知的情況。在此種情況下，我們可以利用亂數產生的樣本，統計聯合機率分布。

該程序首先取得一個樣本 y0 作為初始值，然後利用蒙地卡羅法透過 (X, y0) 產生新樣本 x1，接著再利用 (x1, Y)  產生 y1。於是我們得到下列這個疊代程序 

Algorithm GibbsSampling(X, Y)
　[[ ![](../timg/cb0051ee3fea.jpg) ]] = generate sample from P(Y)
　for i = 1 to N
　　[[ ![](../timg/98113093da15.jpg) ]] = generate sample from [[ ![](../timg/f68c409ed1f7.jpg) ]]
　　[[ ![](../timg/72185419194d.jpg) ]] = generate sample from [[ ![](../timg/c857a0ca1b68.jpg) ]]
　calculate P(X,Y)
End Algorithm

以上疊代程序是針對兩個隨機變數的情況，假如我們希望延伸到 k 個隨機變數的情況，可以修改演算法如下。

Algorithm GibbsSampling([[ ![](../timg/eb5f88344981.jpg) ]])
　[[ ![](../timg/cb0051ee3fea.jpg) ]] = generate sample from P(Y)
　for i = 1 to N
　　j = random(1..k)
　　[[ ![](../timg/60826c1e50a0.jpg) ]] = generate sample from [[ ![](../timg/9b2859733b37.jpg) ]]
　calculate [[ ![](../timg/44b25243a938.jpg) ]]
End Algorithm


Gibbs 取樣程序是『蒙地卡羅馬可夫算法』(MCMC) 的一個案例，也是 Metropolis-Hasting 取樣程序的一個特例，我們可以利用Metropolis-Hasting 取樣程序計算貝氏網路的聯合機率分布。

+ 參考文獻
# 3.4 The Gibbs Sampling Algorithm, http://fedc.wiwi.hu-berlin.de/xplore/ebooks/html/csa/node28.html
# Handbook of Computational Statistics , http://fedc.wiwi.hu-berlin.de/xplore/ebooks/html/