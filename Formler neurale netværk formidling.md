
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
