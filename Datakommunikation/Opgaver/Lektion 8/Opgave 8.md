
Husk når vi bruger traceroute prøver at vi at komme hen til vores end point som vi specificere. Hver gang tilføjer vi en til time to live. Vi sender ICMP pakker som vil lave en ping request og vil modtage med ICMP en echo ping recieve.

På linux kan vi køre: sudo traceroute -I www.ust.hk 
-I betyder at vi vil sende ICMP pakker ellers vil linux sende UDP pakker. Når vi modtager ICMP vil den pakke vores request ind i en ICMP payload. Så altå både vores IP protocol og vores UDP pakke pakket ind i endnu en ICMP pakke som ligger i en IP protocol.


![[Pasted image 20261109104342.png]]

Fordi den ikke skal op igennem transport laget, men holdes på netværks laget.

![[Pasted image 20261109110107.png]]

![[Pasted image 20261109105915.png]]

Type 8 som betyder echo ping request

![[Pasted image 20261109105934.png]]
![[Pasted image 20261109105225.png|374]]
![[Pasted image 20261109105340.png]]

Type er 0 som er en echo ping. Code er også 0. 
Vi har 2 hex numre af 2 så det er 32 bits som er 4 bytes


![[Pasted image 20261109110518.png]]

Så vil nummeret være 17 som er en UDP pakke.





