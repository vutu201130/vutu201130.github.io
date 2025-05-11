## Bias-Variace Tradeoff
Trong lý thuyết về học máy, bias-variace tradeoff là một khái niệm quan trọng để hiểu về tính chất của model học được.
Trong bài toán học máy, dựa vào data thu thập được, mục tiêu là cố gắng đi tìm một ánh xạ \(f\), \(y=f(x)\) mô tả mối quan hệ giữa \(y\) và \(x\).

- Bias: độ lệch giữa mô hình học được và ground-truth. Mô hình học được kí hiệu là $\hat{f}$. Ground-truth cần đi xấp xỉ là $f$.
- Variance: mô tả sự toán loạn của mô hình học được. 

Lý tưởng nhất là train được ra mô hình low-bias và low-variabce.

Bias-variance decompisition

Settings:

Giả sử $y=f(x) + \epsilon$ với $\epsilon$ là một nhiễu có kỳ vọng $\mathbb{E}[\epsilon] = 0$ và phương sai $\mathbb{Var}[\epsilon] = \delta^2$

Với mỗi một tập training $D$ ta train được 1 hàm xấp xỉ $\hat{f}$ cho $f$. Trong setting này, $\hat(f)$ là biến ngẫu nhiên, còn $f$ là không phải ngẫu nhiên.

$\text{Error} = E[(y-\hat{f})^2]$ là trung bình lỗi của thuật toán (mô hình) trên tất cả các tập dataset. Tức là dùng nhiều tập data để tính nhiều $\hat{f}$ thì trung 
bình lỗi so với ground-truth là bao nhiêu.

Do $y=f(x) + \epsilon$ với $\epsilon$ nên

$$
\begin{aligned}
E[(y-\hat{f})^2] = E[(f(x) + \epsilon -\hat{f})^2] \\
                &= E[((f(x) -\hat{f}) + \epsilon)^2] 
\end{aligned}
$$



$E[(\hat{f}(x) - f(x))^2] = \text{Bias}^2 + \text{Variance} + \text{Noise}$
