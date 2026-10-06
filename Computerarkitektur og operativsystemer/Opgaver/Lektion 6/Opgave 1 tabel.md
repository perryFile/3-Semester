
![[Pasted image 20261006140807.png]]

MDR = MEM || Betyder at vi bruger en cycle på at læse data ind i MDR

|     |                |         |                                   |
| --- | -------------- | ------- | --------------------------------- |
| Cy  | MAR=SP=SP-1;rd | H=TOS   | MDR = TOS = MDR+H; wr; goto(MBR1) |
| 1   | B = SP         |         |                                   |
| 2   | C = B-1        | A = TOS |                                   |
| 3   | MAR = C; rd    | C = A   |                                   |
| 4   | MDR = MEM      | H = C   |                                   |
|     |                |         | A = H                             |
|     |                |         | B = MDR                           |
|     |                |         |                                   |
