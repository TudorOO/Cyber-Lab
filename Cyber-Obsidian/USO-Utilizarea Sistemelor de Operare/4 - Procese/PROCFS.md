Sistemul de fisiere virtual **procfs** contine informatii despre procese ce ruleaza in momentul acela. Acesta este in memorie, nu are suport pe disc. se regaseste in `/proc`

/proc este compus din fisiere cu nume obisnuit si directoare cu nume ce reprezinta PID-urile proceselor ce ruleaza curent. Fiecare director cu nume PID contine mai multe informatii despre proces, de exemplu:
- **exe** --> legatura simbolica catre executabilul aferent procesului.
- **fd** --> director cu tabela de descriptori de fisiere a procesului
- **status** --> informatii despre starea procesului
- **task** --> director cu threadurile procesului.

`/proc` contine si alte intrarii pentru investigarea sistemului, care sunt accesate de alte utilitare ce nu tin de procese.