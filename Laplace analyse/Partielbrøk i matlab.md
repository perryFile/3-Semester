
Følgende scripts finder C konstanterne i partielbrøk opsplitning samt polerne.
[1 2/10 1/10] og [1 0 25] er konstanterne i følgende overførselsligning: 

 ![InkDrawing](<Laplace analyse/Bilag/Ink/Drawing/2026.9.13 - 14.55pm.svg>) [Edit Drawing](https://youtu.be/2arL1jh8ihA?type=inkDrawing&width=500&aspectRatio=1.778&viewBoxX=0&viewBoxY=0&viewBoxW=2000&viewBoxH=1125)


```matlab

num = 10;

den1 = [1 2/10 1/10];
den2 = [1 0 25];

den = conv(den1, den2);

[r,p,k] = residue(num, den)

```
