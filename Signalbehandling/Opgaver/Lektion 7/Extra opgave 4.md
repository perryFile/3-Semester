
![[Pasted Image 20261022100615_296.png]]

Har tilføjet følgende kode siden opgave 3

```matlab

%% 
%Vi vil nu gerne sammenligne impuls response

n = 0:1000;
figure();
impulse(H_s,'r',H1_z,'b',H2_z,'g')
legend('Analog Butterworth', ...
       'Matched Z-transform', ...
       'Impulse Invariant');

```

![[Pasted image 20261022135154.png]]