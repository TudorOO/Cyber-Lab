
<h2><b>Formatul fisierelor</b></h2>
*Doua* mari categorii:
	1) ***Fisierele de tip text***
	2) ***Fisierele binare***
<h3>Tipul fisierului(ls)</h3>
***-*** = regular file
***b*** = block special file
***c*** = character special file
***d*** = directory
***l*** = symbolic link
***n*** = network file
***p*** = FIFO
***s*** = socket

******

<h2><b>Tipuri de sisteme de fisiere</b></h2>

| SO<br>Sistem fisiere | Windows            | Linux        | Mac OS       |
| -------------------- | ------------------ | ------------ | ------------ |
| FAT32                | Nativ              | Nativ        | Nativ        |
| NTFS                 | Nativ(dupa WinNT)  | prin ntfs-3g | prin ntfs-3g |
| Ext2/3/4             | Driver third-party | Nativ        | -            |
| HFS+                 | -                  | Nativ        | Nativ        |
| APFS                 | -                  | -            | Nativ        |
| ISO9660              | Nativ              | Nativ        | Nativ        |
| UDF                  | Nativ              | Nativ        | Nativ        |
*Nativ insemana ca suportul este oferit de driverele ce insotesc sistemul de operare*


Sistemele de fisiere pot fi clasificate si dupa locul in care datele sunt stocate:

| Tip                                | Exemplu                 | Descriere                                           |
| ---------------------------------- | ----------------------- | --------------------------------------------------- |
| Sisteme cu fisiere cu suport fizic | FAT32, NTFS, Ext4, APFS | Pe un mediu de stocare                              |
| Sisteme de fisiere virtuale        | procfs, devfs, SSHFS    | Generate de SO sau alt software                     |
| Sisteme de fisiere pentru retea    | NFS, SMB                | Utilizate pentru accesul la fisiere aflate in retea |



