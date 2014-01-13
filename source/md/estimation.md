# 估計 -- 不偏估計式與信賴區間

## 不偏估計式

* 定義：(不偏估計式) 若 [[ ![](../timg/1350546872ea.jpg) ]] 則稱估計式 [[ ![](../timg/433acd3e109e.jpg) ]] 為 [[ ![](../timg/f6c1ecf1eac0.jpg) ]] 的不偏估計式。

## 信賴區間

估計式 [[ ![](../timg/f6c1ecf1eac0.jpg) ]] 的 [[ ![](../timg/1bd18bd3fcf1.jpg) ]]% 信賴區間是一個範圍，[[ ![](../timg/f6c1ecf1eac0.jpg) ]] 在這個範圍之間的機率是 [[ ![](../timg/1bd18bd3fcf1.jpg) ]]%

 ![](../timg/e7f87fca1ecf.jpg) 

假如 [[ ![](../timg/f6c1ecf1eac0.jpg) ]] 的分布符合某種分布 D，則代表我們想要找尋的算式如下：

 ![](../timg/7bd84223a2d1.jpg) 

在一般的情況下，我們通常將範圍外的機率 [[ ![](../timg/9845198045ec.jpg) ]] 平均分配在兩邊，因此上式相當於找尋

 ![](../timg/8563f4c3f635.jpg) 
 ![](../timg/3736b94a69a2.jpg) 
 ![](../timg/2062d53a96f7.jpg) 

### 習題

習題 1 : 

> 累積分布表查詢 (信賴區間)
> 
> 1. 請從標準常態分布表中查出 [[ ![](../timg/20d8d7e657d0.jpg) ]] 的 L1 値。
> 
> 2. 請從標準常態分布表中查出 [[ ![](../timg/2d9ae630c9ff.jpg) ]] 的 L2 値。
> 
> 3. 請從卡方分布表中查出自由度 24 的分布中符合 [[ ![](../timg/cf7a2c225722.jpg) ]] 的 L1 値。
> 
> 4. 請從卡方分布表中查出自由度 24 的分布中符合 [[ ![](../timg/8737fd8107e9.jpg) ]] 的 L2 値。
> 
> 5. 請從 T 分布表中查出自由度 10 的分布中符合 [[ ![](../timg/58e1d20c9030.jpg) ]] 的 L1 値。
> 
> 6. 請從 T 分布表中查出自由度 10 的分布中符合 [[ ![](../timg/2b42e617cc02.jpg) ]] 的 L2 値。

習題 2：同習題 1，但改用 R 函數計算累積分布 (信賴區間)

```R
> qnorm(0.025)
[1] -1.959964
> qnorm(0.975)
[1] 1.959964
> qchisq(0.025, 24)
[1] 12.40115
> qchisq(0.975, 24)
[1] 39.36408
> qt(0.025, 10)
[1] -2.228139
> qt(0.975, 10)
[1] 2.228139
> qt(0.025, 24)
[1] -2.063899
> qt(0.975, 24)
[1] 2.063899
> 
```

## 常態分布的信賴區間

標準常態分布通常寫為 Z，其信賴區間可以寫成如下算式，然後用累積常態分布表查出信賴區間。

 ![](../timg/07b188ead6b7.jpg) 

但是由於常態分布的兩邊對稱，因此平均分配之後就是找出 [[ ![](../timg/1f93a9ae3038.jpg) ]] 與 [[ ![](../timg/7f60eaeb58f2.jpg) ]] 的値，此時可以利用累積常態分布表進行查詢，找出 L1 與 L2 的範圍。

舉例而言，假如我們要找的是 95% 的信賴區間，那麼就可以從標準常態分布表中找到 [[ ![](../timg/da2f514d0ac2.jpg) ]], 且 [[ ![](../timg/8c8b7b93e198.jpg) ]]，於是我們知道 95% 信賴區間為

 ![](../timg/ae745f1d51ca.jpg) 

範例：

> 假如 [[ ![](../timg/f6c1ecf1eac0.jpg) ]] 的分布符合常態分布，則代表我們要尋找的算式如下。
> 
>  ![](../timg/07b188ead6b7.jpg) 
> 

但是由於常態分布的兩邊對稱，因此平均分配之後就是找出 [[ ![](../timg/1f93a9ae3038.jpg) ]] 與 [[ ![](../timg/7f60eaeb58f2.jpg) ]] 的値，此時可以利用標準常態分布表進行查詢，找出 L1 與 L2 的範圍。

舉例而言，假如我們要找的是 95% 的信賴區間，那麼就可以從標準常態分布表中找到 [[ ![](../timg/da2f514d0ac2.jpg) ]], 且 [[ ![](../timg/8c8b7b93e198.jpg) ]]，於是我們知道 95% 信賴區間為

 ![](../timg/ae745f1d51ca.jpg) 

## 參考文獻
* [常態分佈. (2011, October 24). Retrieved from 維基百科, 自由的百科全書](http://zh.wikipedia.org/w/index.php?title=%E6%AD%A3%E6%80%81%E5%88%86%E5%B8%83&oldid=18137847)
* http://en.wikipedia.org/wiki/Normal_distribution


+ 估計的參數種類

根據單一母體所抽出的樣本，推論統計可以猜測母體中隨機變數 X 的下列特性：

# 可能屬於哪一類型的分布？ (distribution, 二項、布瓦松、均等、常態、指數、卡方....)
# 其平均值的可能點預估？ ([[ ![](../timg/c9faf6ead2cd.jpg) ]]:mean 的點估計)
# 其變異數的可能點預估？ ([[ ![](../timg/77a3b715842b.jpg) ]]:variance 的點估計)
# 機率 p 的可能點預估？ (p 的點估計)
# 各種分布參數的可能點預估？ (parameters, [[ ![](../timg/25bc87099312.jpg) ]])
# 平均數的可能範圍？ ([[ ![](../timg/c9faf6ead2cd.jpg) ]]:mean 的區間估計)
# 變異數的可能範圍？ ([[ ![](../timg/77a3b715842b.jpg) ]]:variance 的區間估計)
# 機率 p 的可能範圍？ (p 的區間估計)
# 各種分布參數的可能範圍預估？ (parameters, [[ ![](../timg/25bc87099312.jpg) ]] 的區間估計)

+ 平均值的估計

* 定理：[[ ![](../timg/a1c233438b21.jpg) ]] 為 [[ ![](../timg/e6e3b9a5862e.jpg) ]] 的不偏估計式。

* 定理：[[ ![](../timg/0cbcfdb432aa.jpg) ]] 服從標準常態分布。(條件是樣本數夠多，根據中央極限定理)

++ 平均值的信賴區間

+++ 第一種情況：在變異數 [[ ![](../timg/15c541d17491.jpg) ]] 已知的情況之下，應該用常態分配估計 [[ ![](../timg/b5e8c0f01bda.jpg) ]] 的信賴區間。

[[math]]
P[L1 \le Z \le L2] = 1-\alpha
[[/math]]

通常我們將區間的兩邊取平均，得到 [[ ![](../timg/9845198045ec.jpg) ]] 的値

[[math type="eqnarray"]]
&& P[L1 \le Z \le L2] &=& 1-\alpha && ; 常態分布的信賴區間 \\
&& P[L1 \le \frac{\bar{X}-\mu}{\sigma/\sqrt{n}} \le L2] &=& 1-\alpha &&  ; 因為  \frac{\bar{X}-\mu}{\sigma/\sqrt{n}} 服從常態分布 \\
&& P[L1 \frac{\sigma}{\sqrt{n}} \le \bar{X}-\mu \le L2 \frac{\sigma}{\sqrt{n}}] &=& 1-\alpha && ; 乘以 \frac{\sigma}{\sqrt{n}} \\
&& P[-\bar{X}+L1 \frac{\sigma}{\sqrt{n}} \le -\mu \le -\bar{X} + L2 \frac{\sigma}{\sqrt{n}}] &=& 1-\alpha && ; 減去 \bar{X} \\
&& P[\bar{X}-L1 \frac{\sigma}{\sqrt{n}} \ge \mu \ge \bar{X} - L2 \frac{\sigma}{\sqrt{n}}] &=& 1-\alpha && ; 乘以 -1 並改 \le 為 \ge \\
&& P[\bar{X}-L2 \frac{\sigma}{\sqrt{n}} \le \mu \le \bar{X} - L1 \frac{\sigma}{\sqrt{n}}] &=& 1-\alpha && ; 將整個算式反向寫出
[[/math]]

結論：在變異數 [[ ![](../timg/15c541d17491.jpg) ]] 已知的情況之下，[[ ![](../timg/b5e8c0f01bda.jpg) ]] 的信賴區間公式如下。
[[math]]
P[\bar{X}-Z_{1-\alpha/2} \frac{\sigma}{\sqrt{n}} \le \mu \le \bar{X} - Z_{\alpha/2} \frac{\sigma}{\sqrt{n}}] = 1-\alpha
[[/math]]


* 用法：L  是滿足 [[ ![](../timg/59e6e043be3d.jpg) ]] 情況的 L 値，我們可以利用「累加常態分布表」查詢出 [[ ![](../timg/237608d504f3.jpg) ]] 的 z 値，該値即為滿足 [[ ![](../timg/59e6e043be3d.jpg) ]] 的 L 値。然後將此 L 値代入上列最後一個算式，即可得到 [[ ![](../timg/b5e8c0f01bda.jpg) ]] 值的信賴區間。

+++ 第二種情況：在變異數 [[ ![](../timg/15c541d17491.jpg) ]] 未知的情況之下，應該用 T 分配估計 [[ ![](../timg/b5e8c0f01bda.jpg) ]] 的信賴區間。

說明：因為變異數 [[ ![](../timg/15c541d17491.jpg) ]] 未知，此時必須改用樣本變異數 [[ ![](../timg/b18dd9969fdd.jpg) ]] 對變異數進行估計，因此引入了另一層的誤差，這是為何改用 T 分布的原因。

[[math]]
T = \frac{Z}{\sqrt{\chi_{\gamma}^2/{\gamma}}}
[[/math]]

結論：在變異數 [[ ![](../timg/15c541d17491.jpg) ]] 未知的情況之下，[[ ![](../timg/b5e8c0f01bda.jpg) ]] 的信賴區間公式如下。
[[math]]
P[\bar{X} - T_{1-\alpha/2} \frac{S}{\sqrt{n}} \le \mu \le \bar{X} - T_{\alpha/2} \frac{S}{\sqrt{n}}] = 1-\alpha
[[/math]]

+ 比例的估計

問題：假設 X 為某種 {0,1} 隨機變數，其中 [[ ![](../timg/f411300d6788.jpg) ]]，那麼我們如何根據樣本推估出 p 値呢？

[[math]]
\hat{p} = \frac{X}{n} = \frac{具有某特性的樣本數量}{所有樣本數量}
[[/math]]

說明：比例 [[ ![](../timg/dc64b1f498fa.jpg) ]] 是一種 {0,1} 的特殊隨機變數之平均，因此根據中央極限定理 [[ ![](../timg/aabce87e755b.jpg) ]] 趨近於常態分配。

期望値：[[ ![](../timg/0f4fe9688e8f.jpg) ]]

二級動差：[[ ![](../timg/a91a57d31793.jpg) ]]

變異數：[[ ![](../timg/8638a7348d5b.jpg) ]]

+ 比例的信賴區間

根據平均值的估計法，[[ ![](../timg/0cbcfdb432aa.jpg) ]] 會趨近於標準常態分布 Z，套用到比例上後：[[ ![](../timg/1961d81f042e.jpg) ]], [[ ![](../timg/624c465959d7.jpg) ]]，因此下列算式會趨近於 Z。

[[math]]
\frac{\hat{p}-p}{\sqrt{p(1-p)/n}}
[[/math]]

+ 變異數的估計

* 定理：[[ ![](../timg/6bb703bf05da.jpg) ]]

* 定義：[[ ![](../timg/a1c233438b21.jpg) ]] 的標準差為 [[ ![](../timg/46abe04be0e5.jpg) ]]，稱為平均標準誤。

* 定義：(樣本變異數) [[ ![](../timg/b18dd9969fdd.jpg) ]]

[[math]]
S^2 = \sum_{i=1}^n \frac{(X_i - \bar{X})^2}{n-1} = \frac{n \sum_{i=1}^n X_i^2 - (\sum_{i=1}^n Xi)^2}{n (n-1)}
[[/math]]

* 定理：[[ ![](../timg/b18dd9969fdd.jpg) ]] 是 [[ ![](../timg/15c541d17491.jpg) ]] 的不偏估計式。

* 定理：以下算式服從自由度 n-1 的卡方分配。

[[math]]
\frac{(n-1) S^2}{\sigma^2} = \frac{\sum_{i=1}^n (X_i-\bar{X})^2 }{\sigma^2}
[[/math]]

++ 變異數的信賴區間

[[ ![](../timg/15c541d17491.jpg) ]] 的信賴區間為：

[[math type="eqnarray"]]
&& P[\chi_{\alpha/2}^2 \le \frac{(n-1) S^2}{\sigma^2} \le \chi_{1-\alpha/2}^2] &=& 1-\alpha \\
[[/math]]

也就是：

[[math type="eqnarray"]]
&& P[\frac{(n-1) S^2}{\chi_{1-\alpha/2}^2} \le \sigma^2 \le \frac{(n-1) S^2}{\chi_{\alpha/2}^2}] &=& 1-\alpha \\
[[/math]]

請注意：累積卡方分布通常有分為「右尾累積」與「左尾累積」，本公式中的 [[ ![](../timg/40c510378c57.jpg) ]] 是根據「左尾累積」表所設計的。

如果按右尾累積表則公式應該改為：[[ ![](../timg/f83f54718a44.jpg) ]]

+ R 程式範例

++ 平均值的區間估計

範例一：母體的變異數已知的情況

[[code]]
mean.range = function(x, alpha=0.05, sigma) {
    n = length(x) # n = 樣本數
    mx = mean(x) # mx 即為平均值 mu 的點估計
    r1 = qnorm(alpha/2) # 信賴區間，下半截掉 alpha/2
    r2 = qnorm(1-alpha/2) # 信賴區間，上半截掉 alpha/2
    L1 = mx-r2*sigma/sqrt(n) # 信賴區間下限
    L2 = mx-r1*sigma/sqrt(n) # 信賴區間上限
    range = c(L1, mx, L2) # 信賴區間
}
[[/code]]

以下的母體的標準差為 [[ ![](../timg/c71de12f0938.jpg) ]]，也就是變異數 [[ ![](../timg/ea362775ea10.jpg) ]]

[[code]]
# 常態分布 (標準差為 2, 變異數為 4)
> R = mean.range(rnorm(20, mean=3, sd=2), sigma=2)
> R
[1] 1.728047 2.604570 3.481093
> R = mean.range(rnorm(20, mean=3, sd=2), sigma=2)
> R
[1] 2.795340 3.671863 4.548385
> R = mean.range(rnorm(20, mean=3, sd=2), sigma=2)
> R
[1] 1.720384 2.596906 3.473429
> R = mean.range(rnorm(20, mean=3, sd=2), sigma=2)
> R
[1] 2.580179 3.456702 4.333224
> R = mean.range(rnorm(20, mean=3, sd=2), sigma=2)
> R
[1] 2.332650 3.209172 4.085695
> 
[[/code]]

範例二：母體的變異數未知的情況。

[[code]]
mean.range2 = function(x, alpha=0.05) {
    n = length(x) # n = 樣本數
    mx = mean(x) # mx 即為平均值 mu 的點估計
    S = sqrt(var(x)) # S 即為標準差的點估計
    r1 = qt(alpha/2, df=n-1) # 信賴區間，下半截掉 alpha/2
    r2 = qt(1-alpha/2, df=n-1) # 信賴區間，上半截掉 alpha/2
    L1 = mx-r2*S/sqrt(n) # 信賴區間下限
    L2 = mx-r1*S/sqrt(n) # 信賴區間上限
    range = c(L1, mx, L2)
}
[[/code]]

[[code]]
> # 常態分布 (標準差為 2, 變異數為 4)
> R = mean.range2(rnorm(20, mean=3, sd=2))
> R
[1] 2.303155 3.239184 4.175213
> R = mean.range2(rnorm(20, mean=3, sd=2))
> R
[1] 2.210444 3.146473 4.082502
> R = mean.range2(rnorm(20, mean=3, sd=2))
> R
[1] 1.745906 2.681934 3.617963
> R = mean.range2(rnorm(20, mean=3, sd=2))
> R
[1] 1.950239 2.886268 3.822296
> R = mean.range2(rnorm(20, mean=3, sd=2))
> R
[1] 2.049205 2.985234 3.921263
> R = mean.range2(rnorm(20, mean=3, sd=2))
> R
[1] 2.313619 3.249648 4.185677
> 
> # 擲骰子
> R = mean.range2(sample(1:6, 10, replace=T))
> R
[1] 1.469286 2.900000 4.330714
> R = mean.range2(sample(1:6, 10, replace=T))
> R
[1] 1.569286 3.000000 4.430714
> R = mean.range2(sample(1:6, 10, replace=T))
> R
[1] 1.969286 3.400000 4.830714
> R = mean.range2(sample(1:6, 10, replace=T))
> R
[1] 2.269286 3.700000 5.130714
> R = mean.range2(sample(1:6, 10, replace=T))
> R
[1] 2.269286 3.700000 5.130714
> 
> # 丟銅板 10 次
> R = mean.range2(sample(0:1, 10, replace=T))
> R
[1] -0.9307138  0.5000000  1.9307138
> R = mean.range2(sample(0:1, 10, replace=T))
> R
[1] -0.8307138  0.6000000  2.0307138
> R = mean.range2(sample(0:1, 10, replace=T))
> R
[1] -0.9307138  0.5000000  1.9307138
> R = mean.range2(sample(0:1, 10, replace=T))
> R
[1] -1.030714  0.400000  1.830714
> R = mean.range2(sample(0:1, 10, replace=T))
> R
[1] -0.8307138  0.6000000  2.0307138
> 
> # 丟銅板 100 次
> R = mean.range2(sample(0:1, 100, replace=T))
> R
[1] 0.1131566 0.5100000 0.9068434
> R = mean.range2(sample(0:1, 100, replace=T))
> R
[1] 0.03315661 0.43000000 0.82684339
> R = mean.range2(sample(0:1, 100, replace=T))
> R
[1] 0.1631566 0.5600000 0.9568434
> R = mean.range2(sample(0:1, 100, replace=T))
> R
[1] 0.1231566 0.5200000 0.9168434
> R = mean.range2(sample(0:1, 100, replace=T))
> R
[1] 0.1631566 0.5600000 0.9568434
> R = mean.range2(sample(0:1, 100, replace=T))
> R
[1] -0.01684339  0.38000000  0.77684339
> 
[[/code]]

++ 變異數的區間估計

[[code]]
var.range = function(x, alpha=0.05) {
    n  = length(x) # n = 樣本數
    r1 = qchisq(alpha/2, df=n-1) # 信賴區間，下半截掉 alpha/2
    r2 = qchisq(1-alpha/2, df=n-1) # 信賴區間，上半截掉 alpha/2
    S2  = var(x) # 樣本變異數
    L1 = (n-1)*S2/r2 # 信賴區間下限
    L2 = (n-1)*S2/r1 # 信賴區間上限
    range = c(L1, S2, L2) # 信賴區間
}
[[/code]]

[[code]]
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  7.182354 12.418792 26.492630
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  3.783027  6.541118 13.953967
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  4.686703  8.103637 17.287242
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  3.758948  6.499484 13.865151
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  6.451399 11.154920 23.796450
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  5.710536  9.873916 21.063724
> R=var.range(rnorm(20, mean=5, sd=3))
> R
[1]  7.84639 13.56696 28.94197
# 擲骰子
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 1.607192 2.778947 5.928244
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 1.940502 3.355263 7.157681
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 2.319470 4.010526 8.555533
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 1.246487 2.155263 4.597757
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 1.637631 2.831579 6.040521
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 2.502106 4.326316 9.229198
> R = var.range(sample(1:6, 20, replace=T))
> R
[1] 1.059286 1.831579 3.907252
> # 丟銅板
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1524232 0.2500000 0.4838261
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1381971 0.2266667 0.4386690
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1564879 0.2566667 0.4967281
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1524232 0.2500000 0.4838261
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1463263 0.2400000 0.4644730
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1524232 0.2500000 0.4838261
> R = var.range(sample(0:1, 25, replace=T))
> R
[1] 0.1524232 0.2500000 0.4838261

[[/code]]

+ 估計的參數種類

根據兩個母體所抽出的樣本，推論統計可以猜測兩個母體中隨機變數 X, Y 的下列特性：

# 比較兩機率 p1, p2 的差值 p1-p2 的檢定
# 比較兩平均數 [[ ![](../timg/8618b5799807.jpg) ]] 的差值 [[ ![](../timg/51e8457caef0.jpg) ]] 的檢定
# 比較兩變異數 [[ ![](../timg/1fa6c2dd4645.jpg) ]] 的差值 [[ ![](../timg/53cd6965dd28.jpg) ]] 的檢定
# 比較兩組中位數 M 的差值 [[ ![](../timg/80a0162bebf3.jpg) ]] 的檢定 (無母數方法)

+ 估計

||~ 被估計參數 ||~ 推論分布公式 ||~ 相關分配 ||~ 上下界限 ||
|| [[ ![](../timg/b5e8c0f01bda.jpg) ]] ([[ ![](../timg/d254f875e24c.jpg) ]] 已知) || [[ ![](../timg/ea433199f5e8.jpg) ]] || Z:標準常態 || [[ ![](../timg/f5af91b7a37b.jpg) ]] ||
|| [[ ![](../timg/b5e8c0f01bda.jpg) ]] ([[ ![](../timg/d254f875e24c.jpg) ]] 未知) || [[ ![](../timg/ca44e4bb91aa.jpg) ]] || [[ ![](../timg/1b0c47140d51.jpg) ]] || [[ ![](../timg/fec15f20ca19.jpg) ]] ||
|| [[ ![](../timg/15c541d17491.jpg) ]] || [[ ![](../timg/1c19b37aefcc.jpg) ]] || [[ ![](../timg/9783a8cfac29.jpg) ]]:卡方分布 || [[ ![](../timg/de5eb700c4ea.jpg) ]] _[[ ![](../timg/a0902c2e49e9.jpg) ]] ||
|| [[ ![](../timg/74d37d601e20.jpg) ]] || [[ ![](../timg/50a45dd584ef.jpg) ]] || Z:標準常態 || [[ ![](../timg/dfd3c39f7876.jpg) ]] ||

說明：[[ ![](../timg/aabce87e755b.jpg) ]] 其實是一種 0-1 情況的平均值。

+ 檢定

||~ 被檢定參數 ||~ 推論分布公式 ||~ 相關分配 ||~ 上下界限 ||
|| [[ ![](../timg/151c49425133.jpg) ]] ([[ ![](../timg/d254f875e24c.jpg) ]] 已知) || [[ ![](../timg/ea433199f5e8.jpg) ]] || Z:標準常態  || [[ ![](../timg/ea433231f0c5.jpg) ]] ||
|| [[ ![](../timg/151c49425133.jpg) ]] ([[ ![](../timg/d254f875e24c.jpg) ]] 未知) || [[ ![](../timg/ca44e4bb91aa.jpg) ]] || [[ ![](../timg/1b0c47140d51.jpg) ]] || [[ ![](../timg/fec15f20ca19.jpg) ]] ||
|| [[ ![](../timg/4604c9306a55.jpg) ]] || [[ ![](../timg/4603b0802bd1.jpg) ]] _
[[ ![](../timg/43e1ce1311c9.jpg) ]] || [[ ![](../timg/9783a8cfac29.jpg) ]]:卡方分布 || [[ ![](../timg/de5eb700c4ea.jpg) ]] _
[[ ![](../timg/a0902c2e49e9.jpg) ]] ||
|| [[ ![](../timg/832a1d7d795e.jpg) ]] || [[ ![](../timg/d0a761a1873a.jpg) ]] _
[[ ![](../timg/669f4dd9517e.jpg) ]] || Wilcoxon Sign Rank || [[ ![](../timg/1a9ba12b0718.jpg) ]] _
[[ ![](../timg/641467a9039d.jpg) ]] ||
|| [[ ![](../timg/9688550c301c.jpg) ]] || [[ ![](../timg/50a45dd584ef.jpg) ]] || Z:標準常態 || [[ ![](../timg/19d86511dd34.jpg) ]] ||
|| [[ ![](../timg/abed9fbeb6ea.jpg) ]] || [[ ![](../timg/57a2c0d502f8.jpg) ]] || Z:標準常態 || [[ ![](../timg/c039dc4be3a0.jpg) ]] ||
|| [[ ![](../timg/2b63f47a718f.jpg) ]] ||  ||  ||  |||| [[ ![](../timg/7831b353909a.jpg) ]] ||  ||  ||  ||
|| [[ ![](../timg/887992cb368f.jpg) ]] ||  ||  ||  ||


練習題3：[[[st:meanIntervalEstEx | 平均值的信賴區間估計 (母體變異數已知)]]]
 * 練習題4：[[[st:varIntervalEstEx | 變異數的信賴區間估計]]] (常態母體 => 服從自由度為 n-1 的卡方分配)
 * 練習題5：[[[st:tTestEx | 平均值的信賴區間估計 (母體變異數未知)]]] (用 S 取代 [[ ![](../timg/464a9b06c5de.jpg) ]] => 學生 t 分配)
# 2011.12.7 (檢定)
 * 練習題1：[[[st:meanTestEx | 分配平均的假設檢定]]] ([[ ![](../timg/a52710eca4dc.jpg) ]] )
 * 練習題2：[[[st:varTestEx | 變異數假設檢定]]] ([[ ![](../timg/c3b824c4909e.jpg) ]] )
 * 練習題3：[[[st:medianTestEx | 中位數的假設檢定]]] ([[ ![](../timg/0faaf0ac2c42.jpg) ]] ) (無母數方法, Wilcoxon Sign-Rank 檢定)
# 2011.12.14 (比例的推論)
 * 練習題1：[[[st:proportionEstEx | 比例的推論]]] ([[ ![](../timg/a59d6d3f4e35.jpg) ]] , 有事前估計與沒有事前估計的推論所需樣本數不同)
 * 練習題2：[[[st:proportionTestEx | 比例的檢定]]] ([[ ![](../timg/5635c2493cce.jpg) ]] )
 * 練習題3：[[[st:medianTestEx | 比較兩比例：估計+檢定]]] ([[ ![](../timg/550787fd9cdc.jpg) ]] )
# 2011.12.21 (比較兩平均與變異數)
 * 練習題1：[[[st:proportionEstEx | 比較兩平均]]] ([[ ![](../timg/becaeb19d078.jpg) ]])
 * 練習題2：[[[st:proportionTestEx | 比較兩變異數]]] ([[ ![](../timg/63bfd5bfee76.jpg) ]] , F 分配)
 * 練習題3：[[[st:proportionTestEx | 比較兩平均 (變異數相等)]]]