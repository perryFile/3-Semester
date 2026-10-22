![[Pasted Image 20261022100615_296.png]]

3)
Se opgave 1 og 2 for $H_{1}(z)$  og $H_{2}(z)$ 

Følgende kode for opgave: 
```matlab
clear; clc; close all;

fa = 1000;
omega_a = 2*pi*fa;
fs = 8000;
T = 1/fs;

[b,a] = butter(3, omega_a, 's');
H_s = tf(b,a);

%% H1_z - Matched Z-transform

H11_z = tf(0.5441,[1,-0.4559],T,'Variable','z^-1');
H12_z = tf(0.406,[1,-1.05,0.4559],T,'Variable','z^-1');

H1_z = H11_z * H12_z;

% Normaliser DC-forstærkningen til 1
H1_z = H1_z / dcgain(H1_z);

%% H2_z - Impulse Invariant

H21_z = tf(0.7854,[1,-0.4559],T,'Variable','z^-1');

H22_z = tf(-0.3927-0.2267j, [1,-0.5250-0.4247j],T,'Variable','z^-1');

H23_z = tf(-0.3927+0.2267j,[1,-0.5250+0.4247j],T,'Variable','z^-1');

H2_z = H21_z + H22_z + H23_z;

% Fjern numeriske imaginære afrundingsfejl
[b2,a2] = tfdata(H2_z,'v');

b2 = real(b2);
a2 = real(a2);

H2_z = tf(b2,a2,T,'Variable','z^-1');

%% Bode-plot

figure();

bode(H_s,'r',H1_z,'b',H2_z,'g');

legend('Analog Butterworth', ...
       'Matched Z-transform', ...
       'Impulse Invariant');

grid on;
```

Giver følgende graf. Vi kan se at jo tættere vi kommer på cutoff desto dårligere bliver vores digitale filter.
![[Pasted image 20261022134354.png]]