
$$ \sum_{i} Input^{i} \cdot Weight ^{i} = 2 \cdot 4 - 3 \cdot 4 = -4 \rightarrow 0$$

$$
f(x) =
\begin{cases}
x, & \text{if } \sum wx + b \geq 0 \\
0, & \text{if } \sum wx + b < 0
\end{cases}
$$

## Softmax

![[Pasted image 20261113180631.png]]


$$s(x_{i}) = \frac{e^{x_{i}}}{\sum_{j=1}^{n}e^{x_{j}}}$$

## MSE loss

$$MSE = \frac{1}{n}\sum_{i=1}^{n}(y_{i}-\hat{y}_{i})²$$
$$LOSS = \frac{1}{2}(\hat{y}-y)²$$

$$LOSS = \frac{1}{2}(10-8)² = 2$$

## Chainrules

$$\frac{\partial L}{\partial w_{3}} = \frac{\partial L}{\partial \hat{y}} \cdot\frac{\partial \hat{y}}{\partial w_{3}} = \frac{1}{2}(10-8)^2 \cdot 5= 10$$
$$\frac{\partial L}{\partial w_{2}} = \frac{\partial L}{\partial \hat{y}}\cdot \frac{\partial \hat{y}}{\partial h}\cdot \frac{\partial h}{\partial w_{2}}=2\cdot 2 \cdot 3 = 12$$
$$\frac{\partial L}{\partial w_{1}} = \frac{\partial L}{\partial \hat{y}}\cdot \frac{\partial \hat{y}}{\partial h}\cdot \frac{\partial h}{\partial w_{1}} = 2\cdot 2 \cdot 2 =8$$

$$learningRate = \eta = 0.0125$$

$$w_{ny} = w_{gammel}-\eta \cdot \frac{\partial L}{\partial w}$$

$$w_{1} = 1-0.0125\cdot 8 = 0.9$$$$w_{2} = 1-0.0125\cdot 12 = 0.85$$$$w_{3} = 1-0.0125\cdot 10 = 1.875$$

$$45 \rightarrow [0.2, 0.4,0.6]$$
$$23 \rightarrow [0.9, 0.34,0.56]$$
$$67 \rightarrow [0.12, 0.24,0.43]$$
$$98 \rightarrow [0.11, 0.12,0.99]$$
$$\text{kost} = 899 = [0.2, 0.4, 0.5]$$
$$\text{kost}_{mad} = 899 = [0.22, 0.86, 0.2]$$
$$\text{kost}_{redskab} = 899 = [-0.32, 0.2, -0.9]$$

$$ \operatorname{Attention}(Q,K,V) = \operatorname{softmax}\left( \frac{QK^T}{\sqrt{d_k}} \right)V$$


**Query (Q):** Repræsenterer, hvilken information tokenet søger efter hos andre tokens.

**Key (K):** Bruges til at vurdere, hvor relevant et andet token er for den pågældende query.

**Value (V):** Indeholder den information, som bliver kombineret med information fra andre tokens.