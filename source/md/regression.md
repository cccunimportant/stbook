# 迴歸分析

假設：
* 自變數 X 不是一種隨機變數，而是一種數學變數。
* 依變數 Y 是一種條件隨機變數，記為 Y|x
* Y|x 的平均值 E(Y|x) 記為 [[ ![](../timg/41ee2e44b920.jpg) ]]
* [[ ![](../timg/41ee2e44b920.jpg) ]] 所形成的曲線稱為 Y 對 X 的迴歸曲線 (curve of regression of Y on X)。
    * X 用來幫助預測 Y|x 的行為，被稱為獨力變數 (independent variable)，預測變數 (predictor variable) 或迴歸變數 (regressor)。
    * Y 根據 X 值而改變，因此稱為依變數 (dependent variable) 或稱為反應變數 (response variable)。

## 簡單線性迴歸模型：(Simple Linear Regression Model)

* Y 對 X 的線性迴歸曲線：[[ ![](../timg/0e352b553f3e.jpg) ]]

* 模型：[[ ![](../timg/a3bf855c653c.jpg) ]] ; 其中的 [[ ![](../timg/9b283153b989.jpg) ]] 代表截距 ; [[ ![](../timg/c00e3fbf3236.jpg) ]] 代表斜率

* 樣本：[[ ![](../timg/9dae0cdc2d43.jpg) ]]  ; 其中的 [[ ![](../timg/a8a39608d0c5.jpg) ]] 稱為殘差誤差 (residual error)

* 點估計：我們可以用最小平方估計值 [[ ![](../timg/f269b9a89549.jpg) ]] 取代 [[ ![](../timg/1c721884a2f8.jpg) ]]

 ![](../timg/df2be0199711.jpg) 

 ![](../timg/ba79c9c8339d.jpg) 

## 最小平方估計式：

 ![](../timg/1ff2aabd3306.jpg) 

 ![](../timg/3fe59fb3dd9c.jpg) 

* 誤差平方和 (error sum of squares)：

 ![](../timg/feff338ee89f.jpg) 

* 區間估計：用來檢定迴歸線有多符合樣本數據 (迴歸顯著嗎？)
    * 斜率 [[ ![](../timg/64e034ad3ef3.jpg) ]] 的點估計、區間估計與檢定
    * 截距 [[ ![](../timg/ebe1f25883d6.jpg) ]] 的點估計、區間估計與檢定
    * 估計式 [[ ![](../timg/78ae5c00fe2b.jpg) ]] 的點估計、區間估計與檢定
    * 殘差分析：分析誤差的型態 (是否適合固定變異數，常態分布的條件等等)
    * 相關係數的點估計、區間估計與檢定

 ![](../timg/e07d8328e3ab.jpg) 

## 複線性迴歸模型：(Multiple Linear Regression Model)

複線性迴歸模型：[[ ![](../timg/f9ef7b6505fe.jpg) ]]

p 階多項式模型：[[ ![](../timg/b9a14980bce1.jpg) ]]

矩陣公式：[[ ![](../timg/0c05ddb64e50.jpg) ]] ; 其中的 E 為誤差部分，也就是殘差

矩陣法可以解複線性迴規，也可以解 p 階多項式，是一般通用的線性方程式解法。

最小平方估計式：[[ ![](../timg/91f2c01e749a.jpg) ]] ; 其中的 E 為誤差部分，也就是殘差。
* 變異數的算式： [[ ![](../timg/bd5c57b1aade.jpg) ]] 。
* 變異數的估計式： [[ ![](../timg/059986a06098.jpg) ]] 。
* 區間估計：平均的信賴區間，單一預測反應值的預測區間
* 檢定：單一預測變數的檢定，顯著回歸的檢定，預測變數子集合的檢定 (看是否能去掉一些變數仍然有足夠的預測能力)
* 變數：加入屬性變數 (分類變數)，考慮選擇變數的準則 (前進選擇法、後退消去法、逐步迴歸法、最大化 [[ ![](../timg/c5ac556dba22.jpg) ]] 法、[[ ![](../timg/9b6d4c27e0e0.jpg) ]] 統計量、PRESS 統計量)。
* 變形：模型轉換 (指數模型 [線性轉球狀]、乘冪模型、倒數模型)。

### 範例：眼睛疾病與年齡的關係 (Silvey [1970] 提供的假想小範例)

年齡 (Age)  20  35  45  55  70
----------- --- --- --- --- ---
測試樣本數  50  50  50  50  50
眼睛失明數  6   17  26  37  44

想要知道：

* 這組數據是否符合 Logistic 和 Probit 模型，並分別估計其 LD50 統計值。
* 在此 LD50 代表一個男性居民盲眼的機率為 50% 時的年齡。


R 程式範例：

```R
> weight = rnorm(100, 60, 10)
> height = rnorm(100, 170, 20)
> plot(weight, height)
> 
```

![](../img/weightHeightPlot.jpg)

```R
> lm(height~weight)

Call:
lm(formula = height ~ weight)

Coefficients:
(Intercept)       weight  
   166.8733       0.0531  

> summary(lm(height~weight))

Call:
lm(formula = height ~ weight)

Residuals:
    Min      1Q  Median      3Q     Max 
-47.165 -15.268   0.384  14.527  40.083 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 166.8733    13.4913  12.369   <2e-16 ***
weight        0.0531     0.2201   0.241     0.81    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 

Residual standard error: 18.4 on 98 degrees of freedom
Multiple R-squared: 0.0005939,  Adjusted R-squared: -0.009604 
F-statistic: 0.05823 on 1 and 98 DF,  p-value: 0.8098 
```

### 參考文獻
*《R导论》PDF 版本 — http://www.biosino.org/R/R-doc/files/R-intro_cn.pdf
    * Silvey [1970] 的範例的來源為：第 76 頁 (11.6 廣義線性模型)

