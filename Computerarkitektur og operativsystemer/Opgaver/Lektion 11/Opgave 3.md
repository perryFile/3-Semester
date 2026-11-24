![[Pasted image 20261124144215.png]]

![[Pasted image 20261124144659.png|547]]

a)
32 bit logical address har $2^{32}= 4294967296 \text{bytes}$ hvor vi bruger 8KB = 8192 bytes
så $\frac{4294967296}{8192} = 524288$ entries

524288 frames i den fysiske hukommelse.

Vi kan også gøre det på følgende måde: 
![[Pasted image 20261124151035.png]]

8KB = $8\cdot 2^{10} = 2^{3+10} =2^{13}$
Vores page n er derfor 13
Vores m beregnes sådan
32 bit logic er $2^{32}$ så m = 32
så page number er m-n = 32-13 = 19 
Vi kan teste.
$2^{19} = 524288$

b) 
Ved vores inverterede page, kan vi gøre det samme.
Vores m er nu 30 da vores fysiske hukommelse er 1GB er $1 \text{GB} =2^{30}$ 
Så 30-13 = 17
$2^{17} = 131072$
Vi spare derfor lidt entries ved at bruge inverteret, men det er stadig mange bytes der skal bruges på pages som giver meget overhead feks page tabel der skal ligge i vores hukommelse og fylder.