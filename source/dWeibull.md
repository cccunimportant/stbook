## 威布爾分布 (Weibull Distribution)

 ![](../timg/11bd5a871bf1.jpg) 

* 用途：(可靠度工程) f(x) 失敗時間, R(t) 可靠度, [[ ![](../timg/9f69619b8dc9.jpg) ]] 失敗率

* Ｒ函數：weibull(a:shape, b:scale)
 * 公式：f(x) = 1 / (π s (1 + ((x-l)/s)^2))
 * 說明：location=l , scale=s 
 * 網址：<http://stat.ethz.ch/R-manual/R-patched/library/stats/html/Weibull.html>

### 特性

* 期望值： ![](../timg/7cc953363931.jpg) 

* 變異數： ![](../timg/0be88ecd1cbf.jpg) 

* 動差生成函數：  ![](../timg/87471c62f700.jpg) 

### R 程式範例一

```R
op=par(mfrow=c(2,2))
curve(dweibull(x, 1, 1), 0, 10)
curve(dweibull(x, 1, 5), 0, 10)
curve(dweibull(x, 5, 1), 0, 10)
curve(dweibull(x, 5, 5), 0, 10)

```

![](../img/dweibullCurve4.jpg)


