![[Pasted image 20261006143045.png|513]]

## IADD
![[Pasted image 20261006140807.png]]

MDR = MEM || Betyder at vi bruger en cycle på at læse data ind i MDR

|     | IADD1              | IADD2     | IADD3                                 |
| --- | ------------------ | --------- | ------------------------------------- |
| Cy  | **MAR=SP=SP-1;rd** | **H=TOS** | **MDR = TOS = MDR+H; wr; goto(MBR1)** |
| 1   | B = SP             |           |                                       |
| 2   | C = B-1            | A = TOS   |                                       |
| 3   | MAR = sp = C; rd   | C = A     |                                       |
| 4   | MDR = MEM          | H = C     |                                       |
| 5   |                    |           | A = H; B = MDR                        |
| 6   |                    |           | C = A+B                               |
| 7   |                    |           | MDR = TOS = C; wr                     |
| 8   |                    |           | MEM = MDR; goto(MBR1)                 |

Vær opmærksom på at vi skal vente (I "IADD3") på at H er klar og derfor kan vi først starte i næste linje. I cycle 8 skal vi vente på at MEM = MDR, at vi skriver til memory.

Fordi vi har 3 latches vil vi kunne clocke 3 gange så hurtigt så vi vil kunne gøre det på 8 cyclus vs MIC2's 9 cyclus. Så MIC3 er hurtigere
## ISTORE
![[Pasted image 20261006143652.png]]


|     | istore1            | istore2           | istore3                 | istore4   | istore5                 |
| --- | ------------------ | ----------------- | ----------------------- | --------- | ----------------------- |
| Cy  | **MAR = LV+MBR1U** | **MDR = TOS; wr** | **MAR = SP = SP-1; rd** |           | **TOS=MDR; goto(MBR1)** |
| 1   | A = LV; B = MBR1U  |                   |                         |           |                         |
| 2   | C = A+B            | A = TOS           | B = SP;                 |           |                         |
| 3   | MAR = C            | C = A             | C = SP - 1              |           |                         |
| 4   |                    | MDR = C; wr       | MAR = SP = C; rd        |           |                         |
| 5   |                    |                   |                         | MDR = MEM |                         |
| 6   |                    |                   |                         |           | A = MDR                 |
| 7   |                    |                   |                         |           | C = MDR                 |
| 8   |                    |                   |                         |           | TOS = C; goto(MBR1)     |

MIC 2 = $5\cdot 3 = 15$ cycles 
vs 
MIC 3 = 8 cycles

## ILOAD
![[Pasted image 20261006145137.png]]


|     | iload1             | iload2            | iload3                     |
| --- | ------------------ | ----------------- | -------------------------- |
| cy  | MAR = LV+MBR1U; rd | MAR = SP = SP + 1 | TOS = MDR; wr; goto (MBR1) |
| 1   | A = LV; B = MBR1U  |                   |                            |
| 2   | C = A+B            | A = SP            |                            |
| 3   | MAR = C; rd        | C = A+1           |                            |
| 4   | MDR = MEM          | MAR = SP = C      |                            |
| 5   |                    |                   | A = MDR; wr                |
| 6   |                    |                   | C = A                      |
| 7   |                    |                   | TOS = C; goto(MBR1)        |

Her vil MIC 3 kunne gøre det på 7 cycles vs MIC 2 der vil bruge 9 cycles