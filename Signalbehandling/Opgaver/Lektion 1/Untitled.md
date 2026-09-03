$$E = mc²$$



## Problem 3.27 — Digital Convolution

Given:

$$h(k) = \begin{cases} 2, & k = 0,1,2 \\ 1, & k = 3,4 \\ 0, & \text{elsewhere} \end{cases}$$

$$x(k) = \begin{cases} 2, & k = 0 \\ 1, & k = 1,2 \\ 0, & \text{elsewhere} \end{cases}$$

Evaluate:

$$y(n) = \sum_{k=-\infty}^{\infty} x(k)\,h(n-k)$$

### Solution

$$h = [2, 2, 2, 1, 1], \quad x = [2, 1, 1]$$

$$y(0) = 2\cdot2 = 4$$

$$y(1) = 2 + 4 = 6$$

$$y(2) = 2 + 2 + 4 = 8$$

$$y(3) = 0 + 2 + 2 + 2 = 6$$

$$y(4) = 2 + 1 + 2 = 5$$

$$y(5) = 1 + 1 = 2$$

$$y(6) = 1 = 1$$

$$\boxed{y = [4, 6, 8, 6, 5, 2, 1]}$$

**Check:** $(2+2+2+1+1)(2+1+1) = 8 \times 4 = 32 = 4+6+8+6+5+2+1$ ✓