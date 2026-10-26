![[Pasted image 20261026105304.png]]

![[Pasted image 20261026105321.png]]

10.126.128.23 er min ip adresse
128.119.245.12 er modtagerens ip

![[Pasted image 20261026105424.png]]
![[Pasted image 20261026105449.png]]
Vi sender ud fra min port 52042 og sender til destination port 80, som er http port

![[Pasted image 20261026105546.png]]

Den har et sequence number på 0
![[Pasted image 20261026105735.png]]

At tcp pakken har en segment længde på 0 og sequence number på 0

![[Pasted image 20261026105836.png]]
![[Pasted image 20261026105955.png]]

Den sender en sequence number på 0 og en ack på 1

![[Pasted image 20261026110059.png]]
![[Pasted image 20261026110813.png]]
Vi har payload på 2476 bytes. Nej ikke alt dataen blev "fittet" i en segment. Vi sender flere pakker.

![[Pasted image 20261026111018.png]]

![[Pasted image 20261026112623.png]]
a.
Tiden er 5.2546...![[Pasted image 20261026111048.png]]

b. 
![[Pasted image 20261026111555.png]]
Den blev acket ved tiden 5.4268...

c. 
Den er 5.4268-5.2646 = 0.1622

d.
![[Pasted image 20261026111804.png]]
5.42684-5.2225=  0.20434

e.
![[Pasted image 20261026111933.png]]
Så estimatedRTT = (1-0.125)* 0.1622+0.125*0.20434 = **0.1674675**



![[Pasted image 20261026112712.png]]

![[Pasted image 20261026112835.png]]

De første 4 pakker sendt har en payload på 2476 bytes
![[Pasted image 20261026112957.png]]
Vi har så en header længde på 32 bytes. Så 
2476+8 = 2484