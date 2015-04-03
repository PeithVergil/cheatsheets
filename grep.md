Grep
======


#### Options
*   **-c, --count**
*   **-i, --ignore-case**
*   **-n, --line-number**
*   **-r, --recursive**
*   **-v, --invert-match**
*   **-E, --extended-regexp**

#### Search _file_ for _keyword_
`grep keyword file`

#### Case insensitive searching
`grep -i keyword file`

#### Search recursively
`grep -r keyword folder`

#### Match whole word
`grep -w keyword file`

#### List just the filenames
`grep -l keyword *.txt`

#### List just the filenames
`grep -l keyword *.txt`

#### Match words that starts with ...
`grep "^keyword" /path/to/file`

#### Match words that ends with ...
`grep "keyword$" /path/to/file`

#### Match whole word with regex
`grep "^keyword$" /path/to/file`

Match one string or the other:

```bash
grep -E "Keyword|keyword" /path/to/file
```