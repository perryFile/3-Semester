
![[Pasted image 20261020140308.png]]

![[Pasted image 20261020140436.png]]
A: child: pid = 0 
B: child: pid1 = 2603
C: parent: pid = 2603
D: parent: pid = 2600

Husk 
```cpp
pid = fork()
```

Det giver pid for childen. Derudover er 

```cpp
pid1 = getpid()
```
giver ens egen pid. 
