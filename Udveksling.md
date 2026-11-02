## NUS Singapore

### Fag
Statestik
![[Pasted image 20260919230500.png|700]]



Hej Simon og Lukas

Tak for snakken i dag og for jeres input. I fik begge besvaret en del af mine spørgsmål.

Jeg er dog lidt usikker på, om jeg fik gjort min pointe helt klar, og hvad vi egentlig endte med at blive enige om.

Min påstand var, at en router (f.eks. ens hjemmerouter) som udgangspunkt får tildelt en offentlig, globalt unik IP-adresse fra internetudbyderen. Denne kan selvfølgelig være dynamisk og dermed ændre sig over tid.

Enhederne på hjemmenetværket får derimod tildelt lokale IP-adresser, typisk via DHCP, mens NAT sørger for at oversætte mellem de private og offentlige adresser. Hvis man eksempelvis ønsker at tilgå sin stationære computer via SSH fra et andet sted i verden, kan man konfigurere port forwarding på sin router, så indgående trafik på en bestemt port videresendes til den pågældende computer.

Det er dog ikke altid, at ens hjemmerouter har sin egen offentlige IP-adresse. Internetudbyderen kan nemlig benytte cgnat, hvilket betyder, at flere husstande og deres routere deler den samme offentlige IPv4-adresse.

I dette tilfælde vil ens hjemmerouter være placeret bag internetudbyderens NAT. Det betyder, at man normalt ikke kan oprette en SSH-forbindelse udefra ved blot at konfigurere port forwarding på sin egen router. CGNAT-enheden ved nemlig ikke, hvilken af de interne routere en ny indgående forbindelse skal videresendes til.

Her kan man muligvis benytte den løsning, du nævnte, Simon (RPS), eller lave en aftale med internetudbyderen om eksempelvis at få tildelt sin egen offentlige IP-adresse eller få konfigureret port forwarding. Men som udgangspunkt kan severen ikke ligge bag en NAT, uden aftaler med udbyder eller andre løsninger som tailscape. Så vil man ikke kunne komme i kontakt med severen ude fra.
[https://www.quora.com/Does-every-router-get-a-unique-public-IP-address](https://www.quora.com/Does-every-router-get-a-unique-public-IP-address)