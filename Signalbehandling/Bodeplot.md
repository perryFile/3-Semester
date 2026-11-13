
Husk at vi har en logaritmisk skala på frekvensen

Det betyder at afstanden mellem $10¹$ til $10²$ og $10²$ til $10³$ er den samme. Så 
![[Pasted image 20261113171457.png]]
![[Pasted image 20261113171510.png|700]]

Vi kan altså tælle x aksens markeringer som 1 markering 2 markering osv. Så 2 markering ved $10³$ er 2000 rad/s. Bodeplottet over er sat til Hz så her er den 2000 Hz.

Det gøre på følgende måde: 
```matlab
h = bodeplot(Hz);
h.FrequencyUnit = 'Hz';
```

![[Pasted image 20261113171633.png|396]]