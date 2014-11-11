textsql
===

Run SQL on CSV or TSV text files from command line.
It based on [Alasql](github.com/agershun/alasql) database engine

## Regular queries

```
    textsql 'select * from csv(a.txt) where a>10 and year<?' 2014
    textsql 'select * from ? left join ? using city WHERE clients.name like ?' clients.txt counties.csv "A%"
    textsql 'SELECT * FROM tab(clients.txt) WHERE a>20 and year<?' 2013
    textsql 'SELECT lastname+' '+firstname FROM csv(http://acme.com/clients.txt, (firstname, lastname))'     
```

## Macros
You can define a macro:

```
    textsql -n countlines 'SELECT MID(line, 0,1) AS firstletter, COUNT(*) FROM txt(?) GROUP BY firstletter'
    textsql countlines myfile.txt 
```
To delete macro:

```
    textsql -n countlines
```


## Queries in files
Run queries from files with parameters:

```
    textsql -f myquery.txt 2014

    //  FILE myquery.txt
    SELECT lastname+' '+firstname FROM csv(http://acme.com/clients.txt, (firstname, lastname, year)) WHERE year = ?

```


