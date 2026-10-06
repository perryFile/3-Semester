![[Pasted image 20261006095145.png]]

Husk vi så efter kan bruge:
[b,a] = zp2tf(z,p,k)
til at få en transferfunktion. Vi får koefficenterne der skal stå i transferfunktionen
```matlab

[z,p,k] = buttap(4);
[num,denum] = zp2tf(z,p,k)

```
