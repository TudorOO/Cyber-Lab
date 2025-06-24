Un proces este creat de un executabil. Un proces este un program aflat in executie, iar programul este imaginea procesului. 

Crearea unui proces dintr-un executabil = **loading**
Momentul in care are loc loadingul = **load time**

**Loaderul**:
- interpreteaza programul executabil
- aloca memoria aferenta pentru proces
- copiaza din programul executabil datele si instructiunile in memorie
- face legatura cu biblioteci dinamice si le incarca in memorie
- plaseaza pe stiva procesului(accesibil functiei main) argumentele programului si variabilele de mediu, care devin argumentele functiei main()

![[Pasted image 20250624213752.png]]

