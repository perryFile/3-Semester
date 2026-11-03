![[Pasted image 20261103135527.png]]

a) 
Der vil komme 6 unikke processer. 
- Først vil en parent forke ud og lave et child. Her er der 2 processer.
- Så vil denne child lave endnu en fork(inde i  If loopet), så nu har vi 3 processor, 2 child og en parent. 
- Så vil de alle sammen forke til sidst. Så nu har vi 6 processor.

b) 
Der vil komme 8 unikke tråde.
Husk hver process er også lig med en tråd. 
- Inde i if loopet har vi 2 child som vil lave en thread hver. Vi har i alt 6 processor så dermed 6 tråde, plus de 2 ekstra tråde der er blevet lavet, så 8 tråde i det hele.