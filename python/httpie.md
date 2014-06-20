HTTPie
===


Flags
---

* **-d, --download** Download mode
* **-f, --form** Form data
* **-v, --verbose** Verbose mode


HTTP Methods
---

### GET

`http -v [example.org]`

### PUT

`http -v PUT [example.org] [hello=world]`

### POST

`http -v -f POST [example.org] [hello=world]`

### DELETE

`http -v DELETE [example.org/posts/7]`


HTTP Headers
---

`http -v [example.org] User-Agent:Mozilla/5.0 [X-Custom-Header1:Hello] [X-Custom-Header2:World]`


Download
---

`http -d https://github.com/jakubroztocil/httpie/tarball/master`