Cause server to make an additional or edited HTTP request to a resource

When a user can input the url that a server accesses(`website.thm/item/2?server={api server}`) an attacker can change the server to one of thier choice or change the item requested on the original server.
If the server variable has something appended at the end of it, make that text a variable using `&x=` 
Example: `https://website.thm/item/2?server=server.website..thm/flag?id=0&x=` results in `https://server.website.thm/flag?id=9&x=.website.thm/api/item?id=2`

To execute you can also change inspect fields like image values, basically any link in the source code can lead to a ssrf

<h2>Spotting</h2>
1. If a full URL is used in a parameter in the address bar
2. A hidden field in a form (`value="http://server.website..."`)
3. A partial URL in the address bar (hostname or path)