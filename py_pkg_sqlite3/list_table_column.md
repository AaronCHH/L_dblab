# To list columns/fields in a sqlite table

```py
import sqlite3
connection = sqlite3.connect('~/foo.sqlite')
cursor = connection.execute('select * from bar')
cursor.description is description of columns

names = list(map(lambda x: x[0], cursor.description))
```

* Alternatively you could use a list comprehension:
```py
names = [description[0] for description in cursor.description]
```

* Reference
  * https://stackoverflow.com/questions/7831371/is-there-a-way-to-get-a-list-of-column-names-in-sqlite
  * https://stackoverflow.com/questions/11996394/is-there-a-way-to-get-a-schema-of-a-database-from-within-python