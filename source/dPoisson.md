## 布瓦松分布 (Poisson distribution)

意義：在單位時間內，事件出現平均 λ 次的機率分布。

公式： ![](../timg/0c930d2788b1.jpg) 

R 的公式：  ![](../timg/ca43e8b89676.jpg) 

R 函數：[pois(λ:事件平均出現次數)](http://stat.ethz.ch/R-manual/R-patched/library/stats/html/Poisson.html)

變數意義： ![](../timg/c049e3fdcead.jpg)  


![圖、布瓦松分布<BR/>來源：<http://en.wikipedia.org/wiki/Poisson_distribution>](../img/PoissonCurve.jpg)


特性：

布瓦松分布可以與泰勒展開式中的 Maclaurin 級數對映起來，所謂的 Maclaurin 級數就是泰勒展開式在 0 點的展開式。

> If the Taylor series is centered at zero, then that series is also called a Maclaurin series, named after the Scottish mathematician Colin Maclaurin, who made extensive use of this special case of Taylor series in the 18th century.

 ![](../timg/1ac4c638a017.jpg) 

![圖、布瓦松分布是二項分布 n 趨近無限大的極限情況<BR/>來源：<http://en.wikipedia.org/wiki/File:Binomial_versus_poisson.svg>](../img/PoissonVsBinomial.jpg)



### 布瓦松分配的公式來源

布瓦松分配可視為二項分配的極限形式，當 binom(n, p) 當中 n 趨近於無限大，而 p 非常小的時候，就會趨近布瓦松分配。

關鍵公式： ![](../timg/f5c44c7b2ec9.jpg) 


證明過程：

 ![](../timg/c1453b053b73.jpg)  .

 ![](../timg/6b58c105e8c3.jpg)  .

 ![](../timg/848edbaea265.jpg)  .

其中的 An 趨近於 1 ，證明如下：

 ![](../timg/08ef57551c17.jpg)  .

期望值與變異數

1.  ![](../timg/a7ee5299c8dd.jpg) 
2.  ![](../timg/f6b3e210bca6.jpg) 

動差生成函數： ![](../timg/96fa85ea62fa.jpg) 


### 習題：

習題：抽血時白血球數量的問題

> 問題： 假如現在從你身上抽一滴血，請回答下列兩個問題。
> 
> 1. 請定義一個隨機變數 X 代表那滴血中的白血球數量。
> 
> 提示： 樣本空間 S = 此時此刻你身上的所有白血球 = {w1,w2,......,wn}
> 
> 2. 請算出一滴血液中有三顆白血球的機率，假設該滴血液占你總血量的 1/1000。

解答 1：

>  X(A) = |A|
> 
> 說明： 
> 
> A 是一個事件，也就是白血球的樣本空間 S 的子集合，例如： A = {w1, w5, w9}
> 
> |A| 代表 A 集合的大小，也就是元素個數，舉例而言：
> 
>   如果 A = {w1, w5, w9} ，那麼 |A| = 3
> 
>   如果 B = {w2, w8}，那麼 |B| = 2
> 
>   如果 C = {}，那麼 |C| = 0
> 
>   如果 D = S，那麼 |D| = n
  
解答 2：

> P(X=3) = P({A | X(A) = 3}) = P({{w1, w2, w3}) + P({w1, w2, w4}) + ......
> 
> 假如任一顆白血球被抽到的機率等於該滴血液佔全身血液的比率，由於該滴血液佔總血量的 1/1000，所以給顆白血球被抽到的機率為 1/1000。
> 
> 而且假設這些白血球沒有智慧，也不會聚合在一起，因此相互之間獨立，那麼由於每顆白血球被抽到的機率為 1/1000，因此 P(w1) = P(w2) = .... P(wn) = 1/1000。
> 
> 那麼初步想法是 P(w1w3) = P(w1) * P(w3) = 1/1000 * 1/1000 。
> 
> 但是上述的想法有個小問題，那就是該情況代表其它白血球都沒被抽到，因此所謂的 P(w1w3) 真正的意思應該是
> 
>  ![](../timg/29e439b8a536.jpg) 
> 
> 所以 P(X=3) 應該算法如下：
> 
>  ![](../timg/960d1fb7e15e.jpg) 
> 
> 推而廣之，P(X=k) 的機率之算法如下：
> 
>  ![](../timg/c103f4ae13f5.jpg) 
> 
> 事實上，這個題目的機率分布就是下一章的二項分布，如下所示：
>
>  ![](../timg/c9c2c2819c48.jpg) 
> 
> 而且、當 n 趨近於無限大時，這個分布將會趨近於布瓦松分布，如下所示：
> 
>  ![](../timg/9fde5316116c.jpg) 
> 
> 其中的 λ 之意義為，在單位時間 (或單位面積、體積) 內，事件的出現次數平均為 λ 次。

習題：假設每 1CC 的血所含的白血球平均為 10 顆，那麼請問你抽 1CC 的血時，抽到 8 顆白血球的機率是多少。

解答：

> λ = 10，因此布瓦松分布為  ![](../timg/ce3620ab8f85.jpg)  ，將 x=8 代入，得到  ![](../timg/bce69f5aeddf.jpg)  

其數值可以用 R 軟體計算，如下所示：

```R
> ?dpois
> dpois(8, 10)
[1] 0.112599
> 10^8*exp(-10)/prod(1:8)
[1] 0.112599
```

### R 程式範例：曲線圖

```R
lambda=5.0; k=seq(0,20); 
plot(k, dpois(k, lambda), type='h', main='dpois(lambda=4.0)', xlab='k')
```
 
![](../img/dpoisPlot.jpg)

### R 程式範例：

```R
require(graphics)

-log(dpois(0:7, lambda=1) * gamma(1+ 0:7)) # == 1
Ni <- rpois(50, lambda = 4); table(factor(Ni, 0:max(Ni)))

1 - ppois(10*(15:25), lambda=100)  # becomes 0 (cancellation)
    ppois(10*(15:25), lambda=100, lower.tail=FALSE)  # no cancellation

par(mfrow = c(2, 1))
x <- seq(-0.01, 5, 0.01)
plot(x, ppois(x, 1), type="s", ylab="F(x)", main="Poisson(1) CDF")
plot(x, pbinom(x, 100, 0.01),type="s", ylab="F(x)",
     main="Binomial(100, 0.01) CDF")
```

執行結果：

```R
> require(graphics)
> 
> -log(dpois(0:7, lambda=1) * gamma(1+ 0:7)) # == 1
[1] 1 1 1 1 1 1 1 1
> Ni <- rpois(50, lambda = 4); table(factor(Ni, 0:max(Ni)))

 0  1  2  3  4  5  6  7  8 
 1  3  6  8 11 11  4  3  3 
> 
> 1 - ppois(10*(15:25), lambda=100)  # becomes 0 (cancellation)
 [1] 1.233094e-06 1.261664e-08 7.085799e-11 2.252643e-13 4.440892e-16
 [6] 0.000000e+00 0.000000e+00 0.000000e+00 0.000000e+00 0.000000e+00
[11] 0.000000e+00
>     ppois(10*(15:25), lambda=100, lower.tail=FALSE)  # no cancellation
 [1] 1.233094e-06 1.261664e-08 7.085800e-11 2.253110e-13 4.174239e-16
 [6] 4.626179e-19 3.142097e-22 1.337219e-25 3.639328e-29 6.453883e-33
[11] 7.587807e-37
> 
> par(mfrow = c(2, 1))
> x <- seq(-0.01, 5, 0.01)
> plot(x, ppois(x, 1), type="s", ylab="F(x)", main="Poisson(1) CDF")
> plot(x, pbinom(x, 100, 0.01),type="s", ylab="F(x)",
+      main="Binomial(100, 0.01) CDF")
> 
```

![](../img/poisson.jpg)

### 參考文獻
* [Wikipedia:卜瓦松分佈](http://zh.wikipedia.org/wiki/%E5%8D%9C%E7%93%A6%E6%9D%BE%E5%88%86%E4%BD%88)
* [Wikipedia:Poisson_distribution](http://en.wikipedia.org/wiki/Poisson_distribution)
