# Installation and configuration of postgresql

## Walkthrough 

```
zypper search-packages postgresql 
# also installs the client packages as dependencies 
zypper install -y postgresql14-server 
systemctl start postgresql

# empty
ls -la /var/lib/pgsql

systemctl start  postgresql
# Do not forget to enable it 
systemctl enable postgresql 

# now we have data files 
ls -la /var/lib/pgsql/data

```

## Filestructure 

 * https://www.postgresql.org/docs/current/storage-file-layout.html

## Administrationsuser konfigurieren 

```
sudo passwd postgres 
su - postgres
pgsql
# so kommen wir wieder raus 
\q

```

## Walkthrough Datenbank 

```
su - postgres 
createuser -P -d testu
createdb -O testu testdb
psql testdb
```

```
# in psql 
# Jetzt kann man eine Tabelle in der Datenbank anlegen:
```

```
CREATE TABLE books ( id int, name varchar(80), publisher varchar(80), date_published date );
```

```
# Die Liste der Relationen kann man sich anzeigen lassen:
testdb=# \dt
```

```
Liste der Relationen
 Schema | Name  |   Typ   | Eigentümer 
--------+-------+---------+------------
 public | books | Tabelle | postgres
```

```
Mit INSERT fügt man Daten in die Tabelle ein:
```

```
INSERT INTO books VALUES ('1', 'Reference openSUSE Leap 15.1', 'SUSE LLC', '2019-05-25');
```

```
Die Tabellenstruktur liest man mit:
```

```
\d books
```   
   
```   
Tabelle »public.books«
     Spalte     |          Typ          | Sortierfolge | NULL erlaubt? | Vorgabewert 
----------------+-----------------------+--------------+---------------+-------------
 id             | integer               |              |               | 
 name           | character varying(80) |              |               | 
 publisher      | character varying(80) |              |               | 
 date_published | date                  |              |               | 
``` 

```
# Ob der Eintrag der Daten in die Tabelle geklappt hat, zeigt das SELECT-Statement:
```

```
SELECT * FROM books;
```
 
``` 
 id |             name             | publisher | date_published 
----+------------------------------+-----------+----------------
  1 | Reference openSUSE Leap 15.1 | SUSE LLC  | 2019-05-25

```

```
# tabelle löschen 
drop table books;
\q
```

```
# in bash
dropdb testdb; 
```

## Ref:
  
  * https://de.opensuse.org/PostgreSQL
