![[Pasted image 20260921103442.png]]
Vi anvender HTTP 1.1:
![[Pasted image 20260921103504.png]]

![[Pasted image 20260921103518.png]]
Vi accepterer engelsk GB(britisk engelsk) version og en normal engelsk, men som accepteres mindre.
![[Pasted image 20260921103750.png]]

![[Pasted image 20260921103958.png]]

Min IP adresse er:  10.126.128.215
Destination er : 128.119.245.12
![[Pasted image 20260921104221.png]]

![[Pasted image 20260921104255.png]]
Status code er OK: **200**
![[Pasted image 20260921104327.png]]

![[Pasted image 20260921104355.png]]
Last modified: 28 oktober 2025 05:59:01 GMT

![[Pasted image 20260921105017.png]]

![[Pasted image 20260921105102.png]]

128 bytes bliver returnered 
![[Pasted image 20260921105132.png]]



![[Pasted image 20260921105555.png]]

![[Pasted image 20260921105606.png]]
No we do not!
![[Pasted image 20260921105831.png]]


![[Pasted image 20260921105851.png]]

Yes!
![[Pasted image 20260921110035.png]]

![[Pasted image 20260921110104.png]]
Den indeholder "IF-MODIFIED-SINCE". Hvis den er blevet modificeret siden, vil den lave en fuld request igen.
![[Pasted image 20260921110214.png]]
![[Pasted image 20260921110526.png]]
Nej der bliver ikke sendt en explicit return af filens indhold. Det ligger i cachen og bliver hentet derfra. Browseren bruger en kopi som ligger i dens cache. Respons phrase er "not modified"
![[Pasted image 20260921110540.png]]

![[Pasted image 20260921110751.png]]
![[Pasted image 20260921110809.png]]

Vi sender kun en GET request: 

![[Pasted image 20260921112741.png]]


![[Pasted image 20260921112803.png]]
43 i mit tilfælde: 
![[Pasted image 20260921112741.png]]

![[Pasted image 20260921113011.png|409]]
**200** og "OK"
![[Pasted image 20260921112948.png]]


![[Pasted image 20260921113059.png]]
Jeg får to TCP pakker. Den sidste HTTP pakke er egentlig en TCP pakke som wireshark lægger sammen og kalder HTPP.
![[Pasted image 20260921113713.png|700]]