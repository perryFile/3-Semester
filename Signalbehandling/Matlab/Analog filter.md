
```matlab

y = lsim(H_s, x, t);

```


Eksempel:

```matlab

H_s = tf(bt,at)

omega = [500, 1200, 6000, 10000]
t = 0:0.0001:0.01;
for i = 1:length(omega)´
    figure;
    x = sin(t*omega(i));
    y = lsim(H_s, x, t);
    plot(t, x, 'b', t, y, 'r')
    xlabel('Time [s]');
    ylabel('Amplitude');
    title(['InputFilter analog (Blue) vs Output (Red) at \omega = ', num2str(omega(i)), ' rad/s']);
    legend('Input', 'Output');
end

```
