<h3>Informatii continue</h3>
1. ***top*** --> interfata interactiva de afisare periodica a info despre procesee
2. ***htop*** --> interfata interactiva de afisare periodica a info despre procesee
3. ***iotop*** --> interfata pentru investigarea folosirii discului
4. ***sysstat*** --> monitorizare continua a resurselor de sistem

<h3>Informatii de tip Snapshot:</h3>
1. ***ps*** --> afiseaza procesele din terminalul curent si atributele acestora([[Atributele unui proces]]), selectiv
2. ***pidof*** --> afiseaza PID-ul proceselor care au o anumita imagine de proces
3. ***pgrep*** --> afiseaza procesele care corespund unei anumite conditii(mai multe)
4. ***pstree*** --> afiseaza ierarhia de procese al sistemului
5. ***pmap*** --> afiseaza harta memoriei unui proces, adica zonele de memorie ocupate
6. ***lsof*** --> afiseaza fisierele deschide de un proces
7. ***uptime*** --> afiseaza incarcarea unui sistem(loadul) in 1 minut, 5 minute si 15 minute
8. ***jobs*** --> folosita pentru a afisa comenzi din shellul curent
9. ***lsof -p*** --> afiseaza tabela de descriptori de fisiere a unui proces
10. ***ltrace*** --> urmareste apelurile de biblioteca
11. ***strace*** --> urmareste apelurile de sistem

<h4>PS</h4>
	***Argumente***:
		1. **-e** --> toate procesele din sistem
		2. **-f** --> listare cu mai multe atribute
		3. **-u** --> listarea proceselor ce apartin utilizatorului []
		4. **-N** --> neaga comanda(-N -u -> nu apartine utilizatorului)
		5. **-C** --> listarea proceselor ce au ca imagine []
		6. **-o** --> numai atributele listate:
			- pid
			- cmd (comenzi pornire)
			- %cpu
			- rss (memorie utilizata)
			- state 
		7. **--no-header**
		8. **--sort** {attribute}
		9. **=** --> daca il pui dupa un atribut, nu mai arata headerul


<h2>Utilitare pentru interactiunea cu procesele<//h2>
1. ***nice -n*** --> modifici prioritatea(nice) unui proces la load
2. ***renice*** --> modifici prioritatea unui proces in timp de run-time
3. ***fg*** --> aduce un proces in foreground
4.  ***bg*** --> trece un proces din background in starea Running
5. ***kill*** [^1]--> trimite un semnal unui proces
6. ***pkill*** --> trimite un semnal la mai multe procese ce indeplinesc o conditie
7. ***killall*** --> trimite un semnal catre mai multe procese ce indeplinesc o conditie

[^1]: [[Operatii cu procese]]
