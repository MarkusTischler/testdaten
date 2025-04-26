# Eine einfache Variante zur Erstellung von Testdaten
Warum und wieso gibt es auf meiner Webseite https://markus-tischler.com

### Die CSV mit 100.000.000 Einträgen zum Download:
Download:
https://downloads.karo-it.com/fiktive_personenliste_100000000.zip (5.8GB)

### Als Postgres pg_dump

Postgresql Version 15 wurde verwendet
```bash
pg_dump -d poc --format=directory --jobs=4 --file=/tmp/backup/poc
tar -czvf /tmp/backup/poc_backup.tar.gz poc
```
Download:
https://downloads.karo-it.com/poc_backup_postgresql.tgz (6.8GB)


### Als Oracle DataPump Export 19c
Details siehe Dump Logfile <br>
Download: 
https://downloads.karo-it.com/poc_backup_oracle.tgz (7.4GB)

### Inhalt der Dumps
```sql
TABLE_NAME                     SIZE_IN_MB
------------------------------ ----------
FIKTIVE_DATEN_ROWS_100000000        17060
FIKTIVE_DATEN_ROWS_10000000          1732
FIKTIVE_DATEN_ROWS_1000000            176
FIKTIVE_DATEN_ROWS_100000              18
FIKTIVE_DATEN_ROWS_10000                2
FIKTIVE_DATEN_ROWS_1000               ,25
```

### Aufbau der Tabellen
```
Name          Null? Typ          
------------- ----- ------------ 
ID                  NUMBER(19)   
GESCHLECHT          VARCHAR2(10) 
VORNAME             VARCHAR2(50) 
NACHNAME            VARCHAR2(50) 
EMAIL               VARCHAR2(50) 
PLZ                 VARCHAR2(10) 
ORT                 VARCHAR2(50) 
STRASSE             VARCHAR2(50) 
HAUSNUMMER          VARCHAR2(10) 
TELEFONNUMMER       VARCHAR2(50) 
GEBURTSDATUM        DATE         
IBAN                VARCHAR2(50) 
BANK_NAME           VARCHAR2(50)
```

