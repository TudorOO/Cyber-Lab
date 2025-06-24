
<h5> Procesele pot fi impartite in 2 categorii, bazat pe Interactivitate</h5>
**Interactive** --> Preiau informatii de la utilizator(shell)
**Neinteractive/batch** --> Nu preiau informatii, ruleaza fara interventia userului(NTP)

<h3> 1.Terminale </h3>
Terminalul este un dispozitiv care intermediazza transmiterea intrarii si iesirii de la user la shell. El este asociat desriptorului de intrare standard al shellului.
![[Pasted image 20250624193257.png]]

Comanda **tty** indica terminalul curent pentru un shell. Fiecare terminal are o intrare in directorul `/dev`

Fiecare proces este asociat unui terminal cand este creat. De obicei, preiau standard out de la shell, iar standard in este citit exclusiv de procesul din foreground.
Procesele pot fi detasate de terminal, lucru ce nu poate fi reversat. In acest fel, stdin si stdout sunt schimbate pentru fisier in alti descriptori.

<h3> Procese daemon</h3>
Proces **daemon** = proces in background care are ca parinte procesul **init**. Se mai numesc si **servicii**(exemple: init, cron, servicii de retea, etc.)
Asadar, procesele daemon:
- Ruleaza in **background**
- Ofera un **serviciu** sistemului
- **Nu** au terminal asociat
- Au ca proces parinte **init**
- descriptorii lor standard refera la intrarea `/dev/null`

Pentru a vedea procesel daemon, folosim `ps -f -ppid 1`


<h3>Detasarea unui proces (Daemonizare)</h3>

Poate fi realizata in 2 moduri:

<h4>1. Daemonizare propriu-zisa(nohup/disown)</h4>
! Procesele **NU** devin daemoni propriu-zisi, caci nu au stdout catre `/dev/null` si nici nu au ca parinte init.

Cand inchidem un terminal(shell) trimitem un semnal `SIGHUP` catre procesele din background, care le inchide si pe acestea. Utilitarul **`nohup`** face ca un proces sa ignore acest semnal si astfel sa nu fie inchis odata cu inchiderea shellului. Comanda asta **prefixeaza** alta comanda.
Cand folosim `nohup` iesirea standard devine `nohup.out`, deci deseori trebuie sa redirectionam stdout catre /dev/null

Exemplu:
`nohup transmission-cli ubuntu-18.04.1-desktop-amd64.iso.torrent > /dev/null 2>&1 &`

Comanda **`disown`** face ca shell-ul sa nu trimita semnal `SIGHUP` la un proces deja creat.

<h4>2. Sesiune noua de terminal(Multiplexare)</h4>

`screen tmux bybou` sunt **multiplexoare de terminal**. Creeaza o sesiune de terminal de la care ne putem detasa si la care apoi ne putem reatasa.
Proces:
- Se porneste o sesiune de terminal folosind screen, tmux sau byobu.
- Se ruleaza comenzile in acel terminal.
- Se face detasarea de la terminal.
- Se poate, ulterior, realiza reconectarea la terminal.


| Functionalitate       | tmux                        | byobu                        | screen                  |
| --------------------- | --------------------------- | ---------------------------- | ----------------------- |
| creare fereastra noua | Ctrl+b c                    | F2                           | Ctrl+a c                |
| detasare              | Ctrl+b d                    | Shift+F6                     | Ctrl+b c                |
| listare sesiuni       | tmux list-sessions          | bybou list-sessions          | screen -ls              |
| reatasare sesiune     | tmux attach \[session-name] | bybou attach \[session-name] | screen -r \[session-id] |
| schimbare fereastra   | Ctrl+b \<window-id>         | F3,F4                        | Ctrl+a    \<window-id>  |
| inchidere sesiune     | Ctrl+b :kill-session        | Ctrl+a \                     | Ctrl+a \                |
Un alt utilitar, mai simplu, este `dtach`.