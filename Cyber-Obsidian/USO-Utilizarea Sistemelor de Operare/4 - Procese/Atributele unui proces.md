
| Atribut                    | Rol                                                | Momentul atribuirii | Modificabil? |
| -------------------------- | -------------------------------------------------- | ------------------- | ------------ |
| PID                        | Identificare Proces                                | load                | nu           |
| PPID                       | Identificare parinte proces                        | load                | da           |
| Program Executabil         | Imaginea procesului <br>(cod si date, [[Pachete]]) | load                | nu           |
| UID/GID                    | Permisiuni proces                                  | load                | nu*          |
| Prioritate statica(nice)   | Importanta in accesul resurselor                   | load                | da           |
| terminal                   | Interfata de comunicare cu utilizatorul            | load                | da           |
| stare                      | Accesul curent la procesor                         | run                 | da           |
| timp de rulare pe procesor | Contabilizare consum procesor                      | run                 | da           |
| memorie consumata          | Contabilizare consum memorie                       | run                 | da           |
| spatiu virtual de addrese  | Harta memoriei unui proces                         | load                | da           |
| fisiere deschise           | Lucrul cu fisiere([[Directoare linux]])            | run                 | da           |

<h2>Starea unui proces</h2>
![[Pasted image 20250526214352.png]]

Valoarea loadului unui sistem = numarul de procese in stare ready

<h3>Prioritatea unui proces (Nice)</h3>
Prioritatea unui proces este determinata de valoarea nice: cu cat aceasta este mai mare, cu atat procesul lasa mai multe procese sa intre in fata lui la procesor, astfel scazand efectiv prioritatea.
