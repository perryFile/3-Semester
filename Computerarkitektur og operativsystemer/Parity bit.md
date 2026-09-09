Vi kan bruge parity bits til at korigere for errors i vores læsning af hukommelse. 
Hvis vi feks har en 16 bit data vi vil sende, kan vi tilføje 5 parity bits  til vores 16 bit, som giver 21 bits.

![[Pasted image 20260909121705.png]]

Vores bits er tilføjet så summen af 1 taller i følgende kombination er lige:

![[Pasted image 20260909121731.png|510]]

Hvis en af vores bits er flipped, vil man kunne identifisere fejlen på følgende måde:
![[Pasted image 20260909121813.png]]

Så ved vi at det er bit 5 som er blevet flippet. Da 1+4 = 5

