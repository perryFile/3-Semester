![[Pasted image 20260922104823.png]]

1. 
Hvis vi kigger på hvad den højste frekvens er, så kan vi se det er 30Hz som kommer fra 
sin(2$\pi$ * 30 * t). Vi ved man skal sample med $f_{s}$ ≥ 2*$f_{max}$ for at undgå aliasing. Så den mindste sampling frekvens er 60 Hz 
2.  
![[Pasted image 20260922112359.png]]

3. 

```matlab
Opgave 3

  

Jeg skal anvende FFT på både det continuous og diskrete signal

  

Fs_diskret = 60; %Sampling frekvens ved diskret. Skal være 2*f_max.

Ts_diskret = 1/Fs_diskret;

T_diskret = 0:Ts_diskret:0.2;

N_diskret = length(T_diskret); %Antal samples diskret'

  

Fs_cont = 1000; %Continuous sampling frekvens skal sættes højt.

Ts_cont = 1/Fs_cont;

T_cont = 0:Ts_cont:0.2;

N_cont = length(T_cont);

  

X_diskret = sin(2*pi*30*T_diskret)+cos(2*pi*20*T_diskret)+sin(2*pi*10*T_diskret)+2;

X_cont = sin(2*pi*30*T_cont)+cos(2*pi*20*T_cont)+sin(2*pi*10*T_cont)+2;

  

  

y_diskret = fft(X_diskret);

y_cont = fft(X_cont);

  

f_diskret = Fs_diskret/N_diskret*(0:N_diskret-1);

f_cont = Fs_cont/N_cont*(0:N_cont-1);

  

Laver FFT shift

  

YY_diskret = fftshift(y_diskret);

YY_cont = fftshift(y_cont);

ff_diskret = Fs_diskret/N_diskret*(-N_diskret/2:N_diskret/2-1);

ff_cont = Fs_cont/N_cont*(-N_cont/2:N_cont/2-1);

  

amplitude_diskret = abs(YY_diskret);

amplitude_continuous = abs(YY_cont);

  

figure();

subplot(2,1,1)

stem(ff_diskret,amplitude_diskret/N_diskret)

subplot(2,1,2)

stem(ff_cont,amplitude_continuous/N_cont)

xlim([-35 35])

```
![[Pasted image 20260922200725.png]]