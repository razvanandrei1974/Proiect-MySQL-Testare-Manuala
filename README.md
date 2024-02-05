# :pushpin: MySQL Database Project 
### :pushpin: Baza de date pentru patrimoniul unei localitati 

### Software folosit : MySql Workbench

## :heavy_check_mark: Am creat baza date : InventarPatrimoniuLocalitate

create database InventarPatrimoniuLocalitate;

### :heavy_check_mark: Am creat tabelul " Patrimoniu " :

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

### :heavy_check_mark: Am modificat denumirea coloanei din Observatii in Categorie

alter table Patrimoniu 
change Observatii Categorie varchar(20);

### :heavy_check_mark: Am vizualizat modificarea
select * from Patrimoniu;


### :heavy_check_mark: Am introdus date in tabelul "Patrimoniu"

insert into Patrimoniu(ID,Departament,Denumire,UM,Cantitate_faptic,Cantitate_scriptic,Pret_unitar,Valoare,Diferenta_plus,Diferenta_minus,Categorie) values
(1,'Birou Caserie','Dulap 2 usi','buc',1,1,450,450,0,0,'Mobilier'),
(2,'Birou Caserie','Cuier perete','buc',1,1,250,250,0,0,'Mobilier'),
(3,'Birou Caserie','Birou','buc',1,1,420,420,0,0,'Mobilier'),
(4,'Birou Caserie','Scaun negru Lido','buc',1,1,48,48,0,0,'Mobilier'),
(5,'Birou Caserie','Scaun directorial Apollo','buc',1,1,196,196,0,0,'Mobilier'),
(6,'Birou Caserie','Monitor LED','buc',1,1,847,847,0,0,'Echipamenet IT'),
(7,'Birou Caserie','Imprimanta Canon','buc',1,1,1735,1735,0,0,'Echipamenet IT'),
(8,'Birou Caserie','Multifunctional HP','buc',1,1,330,330,0,0,'Echipamenet IT'),
(9,'Birou Caserie','Sistem calcul ACER','buc',1,1,1654,1654,0,0,'Echipamenet IT'),
(10,'Birou Caserie','Dulap mic 2 sertare','buc',1,1,450,450,0,0,'Mobilier'),
(11,'Birou Urbanism','Birou','buc',1,1,400,400,0,0,'Mobilier'),
(12,'Birou Urbanism','Dulap cu doua usi','buc',1,1,450,450,0,0,'Mobilier'),
(13,'Birou Urbanism','Cuier perete','buc',1,1,250,250,0,0,'Mobilier'),
(14,'Birou Urbanism','Scaun Papilon','buc',1,1,274,274,0,0,'Mobilier'),
(15,'Birou Urbanism','Scaun negru Lido','buc',1,1,48,0,0,48,'Mobilier'),
(16,'Birou Urbanism','Sistem Packard Bell','buc',1,1,4100,4100,0,0,'Echipamente IT'),
(17,'Birou Urbanism','Imprimanta Lexmark','buc',1,1,994,994,0,0,'Echipamente IT'),
(18,'Birou Urbanism','Imprimanta HP','buc',1,1,836,836,0,0,'Echipamenet IT'),
(19,'Birou Urbanism','Laptop ASUS','buc',1,1,3400,3400,0,0,'Echipamente IT'),
(20,'Birou Viceprimar','Dulap etajat','buc',1,1,480,480,0,0,'Mobilier'),
(21,'Birou Viceprimar','Dulap mic cu doua usi','buc',1,1,350,350,0,0,'Mobilier'),
(22,'Birou Viceprimar','Dulap mare cu vitrina','buc',1,1,1500,1500,0,0,'Mobilier'),
(23,'Birou Viceprimar','Birou','buc',1,1,410,410,0,0,'Mobilier'),
(24,'Birou Viceprimar','Masa mica rotile','buc',1,1,360,360,0,0,'Mobilier'),
(25,'Birou Viceprimar','Fotoliu','buc',1,1,420,420,0,0,'Mobilier'),
(26,'Birou Viceprimar','Scaun Papilon','buc',1,1,273,273,0,0,'Mobilier'),
(27,'Birou Viceprimar','Aer conditionat','buc',1,1,1205,1205,0,0,'Climatizare'),
(28,'Birou Viceprimar','Sistem supraveghere video','buc',1,1,3500,3500,0,0,'Echipamenet IT'),
(29,'Birou Viceprimar','Monitor Dell','buc',1,1,925,925,0,0,'Echipamenet IT'),
(30,'Birou Viceprimar','Unitate HP Intel','buc',1,1,4700,4700,0,0,'Echipamenet IT'),
(31,'Birou Viceprimar','Imprimanta laser HP','buc',1,1,826,836,0,0,'Echipamenet IT'),
(32,'Birou Viceprimar','Telefon Nokia','buc',1,1,338,338,0,0,'Echipamenet IT'),
(33,'Birou Cabinet Primar','Dulap etajat','buc',2,2,550,1100,0,0,'Mobilier'),
(34,'Birou Cabinet Primar','Dulap vitrina etajata','buc',1,1,880,880,0,0,'Mobilier'),
(35,'Birou Cabinet Primar','Birou mare dublu ','buc',1,1,570,570,0,0,'Mobilier'),
(36,'Birou Cabinet Primar','Multifunctional HP','buc',1,1,924,924,0,0,'Nu este cazul'),
(37,'Birou Cabinet Primar','Laptop Lenovo','buc',1,1,4700,4700,0,0,'Echipamenet IT'),
(38,'Birou Cabinet Primar','Dulap 4 usi','buc',1,1,900,900,0,0,'Mobilier'),
(39,'Birou Cabinet Primar','Scaun Papilon','buc',1,1,273,273,0,0,'Mobilier'),
(40,'Birou Cabinet Primar','Multifunctional Lexmark','buc',1,1,950,950,0,0,'Nu este cazul'),
(41,'Birou Cabinet Primar','Monitor Lenovo','buc',1,1,1230,1230,0,0,'Echipamenet IT'),
(42,'Birou Cabinet Primar','Calculator HP','buc',1,1,1900,1900,0,0,'Echipamenet IT'),
(43,'Birou Contabilitate','Birou mare','buc',1,1,600,600,0,0,'Mobilier'),
(44,'Birou Contabilitate','Dulap sase usi','buc',1,1,1350,1350,0,0,'Mobilier'),
(45,'Birou Contabilitate','Aer conditionat ','buc',1,1,1205,1205,0,0,'Climatizare'),
(46,'Birou Contabilitate','Sursa curent','buc',1,1,285,285,0,0,'Echipamenet IT'),
(47,'Birou Contabilitate','Multifunctional Epson','buc',1,1,2049,2049,0,0,'Echipamenet IT'),
(48,'Birou Contabilitate','Dulap 2 usi','buc',1,1,450,450,0,0,'Mobilier'),
(49,'Birou Contabilitate','Scaun Papilon','buc',1,1,273,273,0,0,'Mobilier'),
(50,'Birou Contabilitate','Laptop Asus I7','buc',1,1,4300,4300,0,0,'Echipamenet IT'),
(51,'Birou Contabilitate','Geanta Laptop','buc',1,1,150,150,0,0,'Accesorii IT'),
(52,'Birou Contabilitate','Masa rotile','buc',3,3,900,900,0,0,'Mobilier'),
(53,'Birou Registru Agricol','Dulap 2 usi','buc',1,1,450,450,0,0,'Mobilierl'),
(54,'Birou Registru Agricol','Birou','buc',1,1,400,400,0,0,'Mobilier'),
(55,'Birou Registru Agricol','Cuier perete ','buc',1,1,250,250,0,0,'Mobilier'),
(56,'Birou Registru Agricol','Sistem Brand HP','buc',1,1,2315,2315,0,0,'Echipamenet IT'),
(57,'Birou Registru Agricol','Boxe Genius','buc',1,1,165,165,0,0,'Accesorii IT'),
(58,'Birou Registru Agricol','Imprimanta color Epson','buc',1,1,1428,1428,0,0,'Echipamenet IT'),
(59,'Birou Registru Agricol','Scaun Papilon','buc',1,1,273,273,0,0,'Mobilier'),
(60,'Birou Registru Agricol','Dulap 2 usi','buc',1,1,450,450,0,0,'Mobilierl'),
(61,'Birou Registru Agricol','Geanta Laptop','buc',1,1,150,150,0,0,'Accesorii IT'),
(62,'Birou Registru Agricol','Masa rotile','buc',2,2,440,880,0,0,'Mobilier'),
(63,'Birou Asistenta Sociala','Birou dublu','buc',1,1,580,580,0,0,'Mobilier'),
(64,'Birou Asistenta Sociala','Raft','buc',1,1,450,450,0,0,'Mobilier'),
(65,'Birou Asistenta Sociala','Cuier perete ','buc',1,1,250,250,0,0,'Mobilier'),
(66,'Birou Asistenta Sociala','Monitor Philips','buc',3,3,490,1470,0,0,'Echipamenet IT'),
(67,'Birou Asistenta Sociala','Procesor AMD','buc',1,1,453,453,0,0,'Echipamenet IT'),
(68,'Birou Asistenta Sociala','Carcasa','buc',1,1,191,191,0,0,'Echipamenet IT'),
(69,'Birou Asistenta Sociala','Placa de baza','buc',1,1,435,435,0,0,'Echipamenet IT'),
(70,'Birou Asistenta Sociala','Calorifer Zeis','buc',1,1,622,622,0,0,'Climatizare'),
(71,'Birou Asistenta Sociala','Imprimanta Cannon','buc',1,1,277,277,0,0,'Echipamenet IT'),
(72,'Birou Asistenta Sociala','Masa rotile','buc',2,2,250,500,0,0,'Mobilier'),
(73,'Birou Asistenta Sociala','Monitor led','buc',1,1,792,792,0,0,'Echipamenet IT'),
(74,'Birou Asistenta Sociala','Hard disk','buc',1,1,756,756,0,0,'Echipamenet IT'),
(75,'Birou Secretar','Dulap 2 usi','buc',2,2,470,940,0,0,'Mobilier'),
(76,'Birou Secretar','Dulap 3 usi','buc',1,1,550,550,0,0,'Mobilier'),
(77,'Birou Secretar','Scaun birou','buc',1,1,600,600,0,0,'Mobilier'),
(78,'Birou Secretar','Scaun','buc',2,2,273,546,0,0,'Mobilier'),
(79,'Birou Secretar','Calorifer','buc',1,1,625,625,0,0,'Climatizare'),
(80,'Birou Secretar','Birou colt','buc',1,1,850,850,0,0,'Mobilier'),
(81,'Birou Secretar','Sistem calcul HP','buc',1,1,5100,5100,0,0,'Echipamenet IT'),
(82,'Birou Secretar','Multifunctional Lexmark','buc',1,1,5500,5500,0,0,'Echipamenet IT'),
(83,'Birou Secretar','UPS','buc',1,1,625,625,0,0,'Echipamenet IT'),
(84,'Birou Secretar','Aer conditionat','buc',1,1,1205,1205,0,0,'Climatizare');

(!),[https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/TABEL%20PATRIMONIU.jpg]

### :heavy_check_mark: Am modificat numarul de carcatere text in coloana Denumire

alter table Patrimoniu
modify Denumire varchar(30);

### :heavy_check_mark: Am vizualizat datele din tabelul Patrimoniu
select * from Patrimoniu;

### :heavy_check_mark: Am corectat greseala de la randul 15 din tabel
UPDATE Patrimoniu
SET Valoare = 1 , Diferenta_minus = 0
WHERE ID = 15;

select * from Patrimoniu;

### :heavy_check_mark: Am mai introdus doua randuri in tabelul Patrimoniu
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(85,'Birou Secretar','Notebook McBook','buc',1,1,25900,25900,0,0,'Echipamente IT');

select * from Patrimoniu;

### :heavy_check_mark: Am interogat tabelul Patrimoniu pentru a vedea valoarea minima
SELECT MIN(Valoare)
FROM Patrimoniu;

select * from Patrimoniu;

### :heavy_check_mark: Am interogat cate inregistrari avem in tabel 
SELECT COUNT(*)
FROM Patrimoniu;

### :heavy_check_mark: Am interogat cate ID-uri au valoarea mai mare de 2500 

SELECT COUNT(Valoare)
FROM Patrimoniu
WHERE Valoare > 2500;

### :heavy_check_mark: Am calculat valoarea totala a coloanei "Valoare" din tabel

SELECT SUM(Valoare) AS total
FROM Patrimoniu;


### :heavy_check_mark: Am centralizat datele din tabelul Patrimoniu dupa Categorie
SELECT COUNT(ID), Categorie
FROM Patrimoniu
GROUP BY Categorie;

### :heavy_check_mark: Am corectat greselile de scriere din coloana Categorie

UPDATE Patrimoniu
SET Categorie = 'Mobilier'
WHERE ID = 60;

### :heavy_check_mark: Am mai introdus un rand in tabel
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(88,'Birou Secretar','Multifunctional Brother','buc',1,1,2800,2800,0,0,'Echipamente IT');

### :heavy_check_mark: Am corectat numerotarea ID
UPDATE Patrimoniu
SET ID = '86'
WHERE ID = 88;

SELECT * from Patrimoniu;


### :heavy_check_mark:  Am creat tabelul "AchizitiiPublice"
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


### :heavy_check_mark:  Stergem tabelul AchizitiPublice

drop table AchizitiiPublice;

### :heavy_check_mark:  Am recreat tabelul AchizitiiPublice
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

### :heavy_check_mark:  Introducem date in tabelul AchizitiiPublice

insert into AchizitiiPublice(ID,Denumire,UM,Cantitate,Pret_unitar,Valoare,Departamentul,Document_intrare,Data_achizitiei) values
(1,'Server HP','buc',1,36800,36800,'BirouContabilitate',568989,'2024-01-18'),
(2,'Multifunctional Brother','buc',1,2800,2800,'BirouUrbanism',556322,'2024-01-20');

### :heavy_check_mark:  Adaugam in tabelul Patrimoniu achizitiile facute cu comanda Insert Into

INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(89,'Birou Contabilitate','Server HP','buc',1,1,36800,36800,0,0,'Echipamente IT'),
(90,'BirouUrbanism','Multifunctional Brother','buc',1,1,2800,2800,0,0,'Echipamente IT');

### :heavy_check_mark:  Corectam ID 

UPDATE Patrimoniu
SET ID = '88'
WHERE ID = 90;


### :heavy_check_mark:  Am comparat coloana Denumire cu comanda Inner Join din tabelele Patrimoniu si AchizitiiPublice
 .SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
INNER JOIN Patrimoniu ON Patrimoniu.Denumire = AchizitiiPublice.Denumire;

### :heavy_check_mark:  Am comparat coloana Valoare cu comanda Inner Join din tabelele Patrimoniu si AchizitiiPublice
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
INNER JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;

### :heavy_check_mark:  Am comparat coloana Valoare cu comanda Left Join din tabelele Patrimoniu si AchizitiiPublice
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
LEFT JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;

### :heavy_check_mark:  Am comparat coloana Valoare cu comanda Right Join din tabelele Patrimoniu si AchizitiiPublice
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
RIGHT JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;

### :heavy_check_mark:  Am comparat coloana Denumire cu comanda Right Join din tabelele Patrimoniu si AchizitiiPublice
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
RIGHT JOIN Patrimoniu ON Patrimoniu.Denumire = AchizitiiPublice.Denumire;

### :heavy_check_mark:  Am comparat cu comanda Cross Join tabelele Patrimoniu si AchizitiiPublice
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
CROSS JOIN Patrimoniu Where Patrimoniu.Denumire = AchizitiiPublice.Denumire;

### :heavy_check_mark:  Am comparat cu comanda Cross Join tabelele Patrimoniu si AchizitiiPublice

SELECT Patrimoniu.Pret_Unitar, Patrimoniu.Pret_Unitar
FROM AchizitiiPublice
CROSS JOIN Patrimoniu Where Patrimoniu.Pret_Unitar = AchizitiiPublice.ID;

### :heavy_check_mark:  Am interogat tabelul Patrimoniul pentru a vedea in care departamnete se regaseste produsul "scaun Papilon" .
SELECT * FROM Patrimoniu
WHERE Denumire = 'scaun papilon' OR departament = '*';

### :heavy_check_mark: Am interogat tabelul Patrimoniul pentru a vedea in care departamente se regasesc  produse din categoria Echipamente IT
SELECT * FROM Patrimoniu
WHERE Categorie = 'Echipamente IT' OR departament = '*';

### :heavy_check_mark:  Am interogat tabelul Patrimoniul pentru a vedea in care departamente se regaseste produsul "Imprimanta Canon".
SELECT * FROM Patrimoniu
WHERE Denumire = 'Imprimanta Canon' OR departament = '*';

### :heavy_check_mark:  Am interogat tabelul Patrimoniul pentru a vedea in care departament nu se regasesc produse din categoria "Mobilier".
SELECT * FROM Patrimoniu
WHERE NOT Categorie = 'Mobilier';

### :heavy_check_mark:  Am selectat din tabelul Patrimoniu coloanele Denumire, Departament si Valoare
SELECT Denumire, Departament, Valoare
FROM Patrimoniu;

### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla care produse incep cu litera "i" .
SELECT * FROM patrimoniu
WHERE Denumire LIKE 'i%';

### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla care produse incep cu litera "d".
SELECT * FROM patrimoniu
WHERE Denumire LIKE 'd%';

### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla media coloanei valoare.
SELECT AVG(Valoare)
FROM Patrimoniu;

### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla media coloanei valoare.
FROM Patrimoniu;

### :heavy_check_mark:  Am interogat tabelul Patrimoniu pentru a afla media coloanei valoare la produsele cu o valoare mai mare sau egala cu 100.
SELECT AVG(Valoare)
FROM Patrimoniu
WHERE Valoare >= 100;

### :heavy_check_mark: Am calculat valoarea totala a coloanei "Valoare"
SELECT SUM(Valoare)
FROM Patrimoniu;



























