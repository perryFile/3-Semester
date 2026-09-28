![[Pasted image 20260928100941.png]]

5.
![[Pasted image 20260928102318.png]]
Vi kan se at vi sender DNS med UDP. DNS er altid UDP. Det står explicit som User Datagram Protocol.


6.
![[Pasted image 20260928102449.png]]

![[Pasted image 20260928102611.png]]

Vi modtager igen med UDP. Packet number er 101


7.
![[Pasted image 20260928102803.png]]
![[Pasted image 20260928102930.png]]
![[Pasted image 20260928103004.png]]
Det er matchene destination port som source port. Det er port 53, som er standart for DNS

8.
![[Pasted image 20260928103033.png]]
![[Pasted image 20260928103100.png]]
Til ip: 10.220.2.24

9.
![[Pasted image 20260928103134.png]]

![[Pasted image 20260928103205.png]]

Den har 1 spørgsmål og 0 svar.

10.
![[Pasted image 20260928103243.png]]
![[Pasted image 20260928103316.png]]

Den har et spørgsmål og et svar.

11.
![[Pasted image 20260928103534.png]]
![[Pasted image 20260928103515.png]]

![[Pasted image 20260928103622.png]]
Destination: 10.220.2.24
Source: 10.220.2.24


12.
![[Pasted image 20260928103700.png]]
	![[Pasted image 20260928104033.png]]

Linux maskinen gør at det ligner vi  Faktisk Da det er en non authoritative, må det være vores lokale DNS server.

13.
![[Pasted image 20260928104200.png]]

