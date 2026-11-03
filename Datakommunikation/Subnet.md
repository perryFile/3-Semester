

Subnet kan dele ip adressen om i områder. Det kan være smart hvis man gerne vil give forskellige regler til nogle typer af clienter men ikke andre. Feks lærer og elever. I eksemplet under vil de første 24 bits læst fra venstre mod højre, være ip adressen, hvor så de sidste 8 bit, altså 256 forskellige tal kan være de forskellige brugere på subnettet. Så vi har under 3 forskellige subnets.
![[Pasted image 20261102215747.png|431]]
Hvis man feks har ip adressen som subnet 223.1.3.0/24 vil 223.1.3 være subnettet og antal af forskellige bruger vil nu være 223.1.3.0 - 223.1.3.256 
Der vil altså ikke være andre steder i verden(hvis vi ser bort fra NAT opdeling) hvor disse ip adresser vil være eksisterende.

## Videre forklaring
En internetudbyder i danmark kan feks have subnettet 223.1.0.0/16 her vil 223.1.0.0 - 223.1.256.256 give dem 65.536 forskellige ip adresser som de feks kan tildele routere til hustande. Der vil ikke være andre steder hvor disse ip adresser mellem 223.1.0.0 - 223.1.256.256 vil eksisterer. 

$$65.536\cdot 65.536 = 4.294.967.296$$

Der vil stadig være over 4 milliarder forskellige ip adresser. 

Hvis en udbyder har fået: 
1.0.0.0/8 så råder de over 16.777.216 adresser, men derfor kan en anden udbyder godt få
2.0.0.0/24 altså 256 adresser, disse vil stadig være tilgængelige. 

## Hvor?
Der kan være subnets overalt. På din router, ved internetudbyder, på internettet osv. 