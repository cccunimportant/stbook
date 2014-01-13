定義：隨機變數 X 的密度函數為 f(x)，其特徵函數為：

[[math]]
\phi_X(t) = E[e^{itX}] = \int_{-\infty}^{\infty} f(x) e^{i t x} dx
[[/math]]

特徵函數事實上就是 f(x) 的傅立葉轉換，傅立葉轉換對任何連續可微函數都一定存在，對離散情況也可有離散傅立葉轉換。

範例：常態分布的特徵函數

[[math type="eqnarray"]]
\phi_X(t) 
& = & \int_{-\infty}^{\infty} (\frac{1}{\sqrt{2\pi} \sigma} e^{- \frac{1}{2} [(x-\mu)/\sigma]^2} ) e^{i t x} dx \\
& = & e^{i t x - t^2 \sigma^2/2}
[[/math]]




+ 參考文獻
# [http://www.csie.nuk.edu.tw/~tkyin/2008Fall/PrincipleCommunication2008Fall/cp/Comm_Chapter5.ppt 通訊原理第五章 機率、隨機訊號與雜訊 (ppt)]

+ 柴比雪夫不等式

[[math type="eqnarray"]]
P[ | X - \mu | < k \delta] \ge 1-\frac{1}{k^2}
[[/math]]