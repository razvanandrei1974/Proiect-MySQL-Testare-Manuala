# :pushpin: MySQL Database Project 
### :pushpin: Baza de date pentru patrimoniul unei localitati 
[Baza de date](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/Proiect_MySQL%20TM.sql)

### Software folosit : MySql Workbench

## :heavy_check_mark: Am creat baza date : InventarPatrimoniuLocalitate
```
create database InventarPatrimoniuLocalitate;
```

### :heavy_check_mark: Am creat tabelul " Patrimoniu " :
```
create table Patrimoniu 
(
ID int not null,
Departament varchar(30),
Denumire varchar(15),
UM varchar(15),
Cantitate_faptic int,
Cantitate_scriptic int,
Pret_unitar int,
Valoare int,
Diferenta_plus int,
Diferenta_minus int,
Observatii varchar(30),
primary key(ID)
);
```
### :heavy_check_mark: Am modificat denumirea coloanei din Observatii in Categorie
```
alter table Patrimoniu 
change Observatii Categorie varchar(20);
```
### :heavy_check_mark: Am vizualizat modificarea
```
select * from Patrimoniu;
```

### :heavy_check_mark: Am introdus date in tabelul "Patrimoniu":
[Baza de date](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/Proiect_MySQL%20TM.sql)

### :heavy_check_mark:Model cu introducerea in tabel: 

 |ID|Departament|Denumire|UM|Cantitate_faptic|Cantitate_scriptic|Pret_unitar|Valoare|Diferenta_plus|Diferenta_minus|Categorie|
 |:-:|:----:|:---:|:-:|:-:|:-:|:-:|:--:|:-:|:-:|:--:|
 |1|Birou Caserie|Dulap 2 usi|buc|1|1|450|450|0|0|Mobilier|

![Tabel Patrimoniu](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/TABEL%20PATRIMONIU.jpg)

### :heavy_check_mark: Am modificat numarul de carcatere text in coloana Denumire
```
alter table Patrimoniu
modify Denumire varchar(30);
```
### :heavy_check_mark: Am vizualizat datele din tabelul Patrimoniu
```
select * from Patrimoniu;
```
### :heavy_check_mark: Am corectat greseala de la randul 15 din tabel
```
UPDATE Patrimoniu
SET Valoare = 1 , Diferenta_minus = 0
WHERE ID = 15;
```
```
select * from Patrimoniu;
```
### :heavy_check_mark: Am mai introdus doua randuri in tabelul Patrimoniu
```
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(85,'Birou Secretar','Notebook McBook','buc',1,1,25900,25900,0,0,'Echipamente IT');
```
```
select * from Patrimoniu;
```
### :heavy_check_mark: Am interogat tabelul Patrimoniu pentru a vedea cea produsul cu cea mai mica valoare din patrimoniu. 
```
SELECT MIN(Valoare)
FROM Patrimoniu;
```
select * from Patrimoniu;

### :heavy_check_mark: Am interogat cate inregistrari avem in tabelul Patrimoniu 
```
SELECT COUNT(*)
FROM Patrimoniu;
```

### :heavy_check_mark: Am interogat cate ID-uri au valoarea mai mare de 2500 
```
SELECT COUNT(Valoare)
FROM Patrimoniu
WHERE Valoare > 2500;
```
### :heavy_check_mark: Am calculat valoarea totala a coloanei "Valoare" din tabelul Patrimoniu pentru a vedea valoarea totala a patrimoniului.
```
SELECT SUM(Valoare) AS total
FROM Patrimoniu;
```

### :heavy_check_mark: Am centralizat datele din tabelul Patrimoniu dupa Categorie. 
```
SELECT COUNT(ID), Categorie
FROM Patrimoniu
GROUP BY Categorie;
```
### :heavy_check_mark: Am corectat greselile de scriere din coloana Categorie.
```
UPDATE Patrimoniu
SET Categorie = 'Mobilier'
WHERE ID = 60;
```
### :heavy_check_mark: Am mai introdus un rand in tabelul Patrimoniu
```
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(88,'Birou Secretar','Multifunctional Brother','buc',1,1,2800,2800,0,0,'Echipamente IT');
```
### :heavy_check_mark: Am corectat numerotarea ID-urilor.
```
UPDATE Patrimoniu
SET ID = '86'
WHERE ID = 88;
```
```
SELECT * from Patrimoniu;
```
### :heavy_check_mark:  Am creat tabelul "AchizitiiPublice"
```
create table AchizitiiPublice
(
ID int not null,
Denumire varchar(30),
UM varchar(15),
Cantitate int not null,
Pret_unitar int,
Valoare int,
Departamentul varchar(30),
Document_intrare int,
Data_achizitiei date,
primary key(ID)
);
```

### :heavy_check_mark:  Stergem tabelul AchizitiPublice.
```
drop table AchizitiiPublice;
```
### :heavy_check_mark:  Am recreat tabelul AchizitiiPublice
```
create table AchizitiiPublice
(
ID int not null,
Denumire varchar(30),
UM varchar(15),
Cantitate int not null,
Pret_unitar int,
Valoare int,
Departamentul varchar(30),
Document_intrare int,
Data_achizitiei date,
primary key(ID)
);
```
### :heavy_check_mark:  Introducem date in tabelul AchizitiiPublice
```
insert into AchizitiiPublice(ID,Denumire,UM,Cantitate,Pret_unitar,Valoare,Departamentul,Document_intrare,Data_achizitiei) values
(1,'Server HP','buc',1,36800,36800,'BirouContabilitate',568989,'2024-01-18'),
(2,'Multifunctional Brother','buc',1,2800,2800,'BirouUrbanism',556322,'2024-01-20');
```
### :heavy_check_mark:  Adaugam in tabelul Patrimoniu achizitiile facute cu comanda Insert Into
```
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(89,'Birou Contabilitate','Server HP','buc',1,1,36800,36800,0,0,'Echipamente IT'),
(90,'BirouUrbanism','Multifunctional Brother','buc',1,1,2800,2800,0,0,'Echipamente IT');
```
### :heavy_check_mark:  Corectam ID-urile 
```
UPDATE Patrimoniu
SET ID = '88'
WHERE ID = 90;
```
### :heavy_check_mark:  Am comparat coloana Denumire cu comanda Inner Join din tabelele Patrimoniu si AchizitiiPublice.
```
 .SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
INNER JOIN Patrimoniu ON Patrimoniu.Denumire = AchizitiiPublice.Denumire;
```
### :heavy_check_mark:  Am comparat coloana Valoare cu comanda Inner Join din tabelele Patrimoniu si AchizitiiPublice.
```
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
INNER JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;
```

### :heavy_check_mark:  Am comparat coloana Valoare cu comanda Left Join din tabelele Patrimoniu si AchizitiiPublice.
```
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
LEFT JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;
```
### :heavy_check_mark:  Am comparat coloana Valoare cu comanda Right Join din tabelele Patrimoniu si AchizitiiPublice.
```
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
RIGHT JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;
```

### :heavy_check_mark:  Am comparat coloana Denumire cu comanda Right Join din tabelele Patrimoniu si AchizitiiPublice.
```
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
RIGHT JOIN Patrimoniu ON Patrimoniu.Denumire = AchizitiiPublice.Denumire;
```

### :heavy_check_mark:  Am comparat cu comanda Cross Join tabelele Patrimoniu si AchizitiiPublice.
```
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
CROSS JOIN Patrimoniu Where Patrimoniu.Denumire = AchizitiiPublice.Denumire;
```
### :heavy_check_mark:  Am comparat cu comanda Cross Join tabelele Patrimoniu si AchizitiiPublice
```
SELECT Patrimoniu.Pret_Unitar, Patrimoniu.Pret_Unitar
FROM AchizitiiPublice
CROSS JOIN Patrimoniu Where Patrimoniu.Pret_Unitar = AchizitiiPublice.ID;
```
### :heavy_check_mark:  Am interogat tabelul Patrimoniul pentru a vedea in care departamnete se regaseste produsul "scaun Papilon" .
```
SELECT * FROM Patrimoniu
WHERE Denumire = 'scaun papilon' OR departament = '*';
```
### :heavy_check_mark: Am interogat tabelul Patrimoniul pentru a vedea in care departamente se regasesc  produse din categoria Echipamente IT.
```
SELECT * FROM Patrimoniu
WHERE Categorie = 'Echipamente IT' OR departament = '*';
```
### :heavy_check_mark:  Am interogat tabelul Patrimoniul pentru a vedea in care departamente se regaseste produsul "Imprimanta Canon".
```
SELECT * FROM Patrimoniu
WHERE Denumire = 'Imprimanta Canon' OR departament = '*';
```
### :heavy_check_mark:  Am interogat tabelul Patrimoniul pentru a vedea in care departament nu se regasesc produse din categoria "Mobilier".
```
SELECT * FROM Patrimoniu
WHERE NOT Categorie = 'Mobilier';
```
### :heavy_check_mark:  Am selectat din tabelul Patrimoniu coloanele Denumire, Departament si Valoare
```
SELECT Denumire, Departament, Valoare
FROM Patrimoniu;
```
### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla care produse incep cu litera "i".
```
SELECT * FROM patrimoniu
WHERE Denumire LIKE 'i%';
```

### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla care produse incep cu litera "d".
```
SELECT * FROM patrimoniu
WHERE Denumire LIKE 'd%';
```
### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla media coloanei valoare.
```
SELECT AVG(Valoare)
FROM Patrimoniu;
```
### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla media coloanei valoare la produsele cu o valoare mai mare sau egala cu 100.
```
SELECT AVG(Valoare)
FROM Patrimoniu
WHERE Valoare >= 100;
```

### :heavy_check_mark: Am calculat valoarea totala a coloanei "Valoare".
```
SELECT SUM(Valoare)
FROM Patrimoniu;
```


























