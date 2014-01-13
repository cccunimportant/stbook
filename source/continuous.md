# 機率分布 (連續型)

## 簡介

| 連續機率模型 | 密度函數 | R 函數 | 說明 |
|--------------|----------|--------|------|
| 常態分布(Normal) |  ![](../timg/b0aca724e39e.jpg)  | norm(mean, sd) | 中央極限定理：x1+x2+...+xk; 當 k 越大就越接近常態分布 | 
| 伽瑪分布 (Gamma) |  ![](../timg/7a2f5a287065.jpg)  | gamma(shape, rate = 1, scale = 1/rate) |   ![](../timg/c63269e21148.jpg)  <br/>  指數分布與卡方分布都是 Gamma 分布的特例 |
| 指數分布	(Exponential)|  ![](../timg/71075ebb0855.jpg)  | exp(rate) | 伽瑪分布( ![](../timg/ad965fa877cb.jpg) ) <br/> 布瓦松過程中，第一次事件出現的時間 W |
| 卡方分布 (Chi-Square) |   ![](../timg/1c1902be8fc6.jpg)  | chisq(df, ncp) | 伽瑪分布(  ![](../timg/10fe70a365dc.jpg)  ) <br/> 利用樣本推斷母體變異數 | 
| 均勻分布 (Uniform) |  ![](../timg/d199631f1413.jpg)  | unif(a:min, b:max) | a:範圍下限, b: 上限 <br/> 出現機會均等 |
| 柯西分布 (Cauchy) |  ![](../timg/868c8083bf08.jpg)  | cauchy(b:location, a:scale)  | |
| 威布爾分布 (Weibull)|  ![](../timg/d1d29714916b.jpg)  | weibull(a:shape, b:scale) |  ![](../timg/787bf9141c33.jpg)  <br/> 可靠度工程：f(x) 失敗時間, R(t) 可靠度, ![](../timg/5cba230c35b4.jpg)  失敗率 |
| T 分布 (T)	|  ![](../timg/47685e30d909.jpg)  | t(df, ncp) | 估計變異數時使用的分布 | 
| F 分布 (F)	|  ![](../timg/984c910d56d9.jpg)  |  f(df1, df2, ncp) | 等變異數 F 檢定時使用 | 
| 貝塔分布 (Beta) |  ![](../timg/6e86d1feb294.jpg)   | beta(a:shape1, b:shape2, ncp) |  | 
| 對數常態分布	 (Log Normal) | |  lnorm(meanlog, sdlog) | | 
| 邏輯分布	| | logis(location, scale)	| |
| Signrank	| | signrank(n)	| |
| 威爾斯	| | wilcox(m, n) | a,b 為兩組樣本 | 

## T 分布

