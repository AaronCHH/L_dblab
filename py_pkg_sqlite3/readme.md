# Usage of sqlite3

<!-- TOC -->

- [Usage of sqlite3](#usage-of-sqlite3)
  - [Import](#import)
  - [Create and link to a database file](#create-and-link-to-a-database-file)
    - [Type1: use con](#type1--use-con)
    - [Type2: use cur](#type2--use-cur)
    - [Type3: use with statement (no need for con.commit() and con.close())](#type3--use-with-statement-no-need-for-concommit-and-conclose)

<!-- /TOC -->
## Import

```py
import sqlite3
```  

## Create and link to a database file
### Type1: use con
```py
import sqlite3
con = sqlite3.connect('foo.db')
con.execute('lorem')
con.commit()
con.close()
```

### Type2: use cur
```py
import sqlite3
con = sqlite3.connect('foo.db')
cur = con.cursor()
cur.execute('lorem')
con.commit()
con.close()
```

### Type3: use with statement (no need for con.commit() and con.close())
```py
import sqlite3
with sqlite3.connect(dbFile) as con:
  cur = con.cursor()
  cur.execute('lorem')
``` 