sqv
===

Run SQL on CSV or TSV text files from command line.
It based on [Alasql](github.com/agershun/alasql) project

```
    sqv 'select * from ? where a>10 and year<?' a.txt 2014
    sqv 'select * from ? left join ? using city WHERE clients.name like ? ' ../clients.txt ../counties.csv "A%"
```
