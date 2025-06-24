<h3>1. Incheierea unui proces </h1>
	a. **-kill*** --> trimite un semnal ales procesului. 
	b. **-pkill*** --> trimite un semnal catre procese care au un anumit atribut(ex: apartin cuiva)
	c. **-killall / -skill*** --> la fel ca pkill, dar, mai limitat
	d. Pentru a trimite semnale catre un proces, putem folosi si combinatii de taste:
	
		
| Ctrl+c      | SIGINT      | Intrerupe executia programului curent                                        |
| ----------- | ----------- | ---------------------------------------------------------------------------- |
| **Ctrl+z**  | **SIGTSTP** | **Suspenda executia programului curend si-l trece in background**            |
| **Ctrl+\\** | **SIGQUIT** | **Intrerupe executia programului curent, mai puternic(nu poate fi ignorat)** |
<h3>2. Inlantuirea comenzilor </h3>

| Operator de inlantuire | Conditie pentru a rula a doua comanda   |
| ---------------------- | --------------------------------------- |
| ;                      | Nicio conditie                          |
| \|\|                   | Prima comanda s-a terminat cu insuccess |
| &&                     | Prima comanda s-a terminat cu success   |
<h3>Pipe-uri</h3>
Operatorul **|** transfera iesirea standard a unei comenzi catre iesirea standard a altei comenzi.
