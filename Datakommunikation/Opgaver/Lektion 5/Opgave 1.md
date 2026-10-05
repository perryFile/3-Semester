
![[Pasted image 20261005110346.png]]


Det er en DNS som bliver sendt som payload.
![[Pasted image 20261005111549.png|700]]

![[Pasted image 20261005111535.png|437]]

I vores header har vi:
Source port
Dest port
Length
Checksum
![[Pasted image 20261005111904.png]]




![[Pasted image 20261005112002.png]]

![[Pasted image 20261005112128.png]]

Vi har 4 gange 2 bytes. Så 8 bytes, 64 bits hvilket giver god mening da vi headeren har 2x32bit


![[Pasted image 20261005112251.png]]

Værdien af "Lenght" er hele UDP pakkens længde. Her er værdien 50 bytes, hvilket passer med en header på 8 bytes og 42 bytes payload:
![[Pasted image 20261005112417.png|530]]

![[Pasted image 20261005112436.png]]

Vi kan max sende en hel UDP pakke med 65353 bytes. Så payload er 65535-8 = 65527. Vi trækker altså de 8 bytes fra headeren fra
![[Pasted image 20261005112549.png|374]]

![[Pasted image 20261005112724.png]]

Det største tal vi kan lave med 2 bytes er 16² = 