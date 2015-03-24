HTTPie
===


Options
---

| Short   | Long           | Description          |
|:-------:|:---------------|----------------------|
| **-d**  | **--download** | Download mode        |
| **-v**  | **--verbose**  | Verbose mode         |
| **-f**  | **--form**     | Form data            |


HTTP Methods
---

### GET

`http -v GET [example.org]`

### GET with query strings

`http -v GET [example.org] fname==hello lname==world`

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