
<h2><b>Comenzi uzuale</b></h2>

***cd*** --> Change directory
***pwd*** -->Print working directory
***ls {optiuni}*** --> List
	1. ***-l*** -> afiseaza detalii despre fiecare director/fisier(dimensiune, utilizator, grup, permisiuni, data modificare so tip de fisier(vezi [[Formatul fisierelor si tipuri de sisteme]]))
	2. ***-a*** -> afiseaza toate fisierele, inclusiv cele **ascunse**
	3. ***-h*** -> afiseaza dimensiunea fisierelor in K/M/Gbytes
***cat*** -> afisare continut fisier
***less*** -> afisare continut fisier, cu interfata similara cu vim
***touch*** -> creeaza fisier gol, updateaza data modificare
***ln*** -> creeaza legatura simbolica
***mkdir*** -> creeaza directory
***cp {sursa} {destinatie}*** -> copiaza un fisier 
***cmp*** -> compara doua fisiere, nu returneaza nimic daca sunt la fel
***diff {-r}*** -> compara doua foldere, recursiv
***mv*** -> muta un fisier sau un folder altundeva
***rm {optiuni}*** -> sterge un fisier sau folder
	1. ***-r*** -> sterge folder recursiv
	2. ***-f*** -> sterge fortat
***rmdir*** -> sterge folder si ce e in el
***locate*** -> cauta un fisier intr-o baza de date locala(*cautare indexata*)
***updatedb*** -> updateaza baza de date mentionata mai sus
***find {options}*** -> cauta exhaustiv in ierarhia fisierelor(*cautare exhaustiva*)
	1. ***-name*** -> cauta dupa nume
	2. ***-type*** -> cauta dupa tipul de fisier
	3. ***-size*** -> cauta dupa marimea fisierului
***whereis*** --> cauta locul corespunzator unei comenzi 
***which*** --> cauta calea catre executabilul unei comenzi 
***type*** --> returneaza modul de interpretare al comenzii(builtin, external, alias)


<h2><b>Arhivare/Dezarhivare</b></h2>
***zip*** --> arhivare + compresare
***tar*** --> arhivare
***gzip/bzip2*** --> compresare

***tar {optiuni}*** --> utilitara pentru arhivare, dezarhivare
	1. c -> creeaza arhiva
	2. x -> dezarhiveaza
	3. t -> listeaza continut
	4. v -> verbose
	5. f -> numele arhivei
	6. z -> compresare gzip
	7. j -> compresare bzip2
*Exemplu:* `tar czf 01-fs.tar.gz uso.git/labs/01-fs`

See also: [[Directoare linux]]
