
![[Pasted image 20261103140323.png]]
![[Pasted image 20261103140358.png|492]]

Void ```*runner(void *param)``` vil lave en funktion som vil sætte en global variabel til at være 5. 

Vi starter med at forke, nu har vi to processer. Vores child vil gå ind i det første if loop.
Her vil vi initialiserer en ny thread ```pthread_attr_init(&attr)```og derefter laver vi en ny thread med create ```pthread_create(&tid, &attr, runner, NULL)``` Her siger vi threaden skal køre funktionen runner. Derefter skal ```pthread_join(tid, NULL)``` joine vores thread tilbage med vores child og printer værdien af value.

Hvis det er ikke er en child process skal den vente på child process er færdig og så printe vores værdi. 

a) 
Ud fra overstående vil både LINE C printe værdien 5 da det er en global variabel som vi ændre og derfor overlever at vi har lavet en thread og joiner igen. Vores LINE P printe værdien 0 da når vi forke vi vil lave en kopi af hele vores kode og dermed også den globale variabel. 