
![[Pasted image 20261006140807.png]]

MDR = MEM || Betyder at vi bruger en cycle på at læse data ind i MDR

|     | IADD1              | IADD2     | IADD3                                 |
| --- | ------------------ | --------- | ------------------------------------- |
| Cy  | **MAR=SP=SP-1;rd** | **H=TOS** | **MDR = TOS = MDR+H; wr; goto(MBR1)** |
| 1   | B = SP             |           |                                       |
| 2   | C = B-1            | A = TOS   |                                       |
| 3   | MAR = sp = C; rd   | C = A     |                                       |
| 4   | MDR = MEM          | H = C     |                                       |
| 5   |                    |           | A = H                                 |
| 6   |                    |           | B = MDR                               |
| 7   |                    |           | C = MDR+H                             |
| 8   |                    |           | MDR = TOS = C; wr                     |
| 9   |                    |           | goto(MBR1)                            |
