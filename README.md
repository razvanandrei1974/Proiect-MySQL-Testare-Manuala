![MySql](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/MySQL1.jpg) 


# :pushpin: MySQL Database Project 

# :pushpin: Database description: 
We created a database in which we recorded all inventory objects and fixed assets in the patrimony of a locality. We created a main table with all inventory objects and fixed assets and another secondary table for the purchase of other inventory objects and fixed assets. This database was created to manage the patrimony of the locality divided by departments and categories.

# :pushpin: Database Schema

You can find below the database schema that was generated through Reverse Engineer and which contains all the tables and the relationships between them.
The tables are connected in the following way:
### :heavy_check_mark: Reverse Engineering Diagram pentru Baza de date : Patrimoniu :

![Reverse Engineering Diagram](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/Reverse%20Engineering%20Diagram%201.jpg)


**nume tabela 1** is connected with **nume tabela 2** through a **tip relatie** relationship which was implemented through **nume_tabela.nume_coloana_cheie_primara** as a primary key and **nume_tabela.nume_coloana_cheie_secundara** as a foreign key
**nume tabela 3** is connected with **nume tabela 4** through a **tip relatie** relationship which was implemented through **nume_tabela.nume_coloana_cheie_primara** as a primary key and **nume_tabela.nume_coloana_cheie_secundara** as a foreign key
**nume tabela 5** is connected with **nume tabela 6** through a **tip relatie** relationship which was implemented through **nume_tabela.nume_coloana_cheie_primara** as a primary key and **nume_tabela.nume_coloana_cheie_secundara** as a foreign key
...........
**nume tabela n** is connected with **nume tabela n+1** through a **tip relatie** relationship which was implemented through **nume_tabela.nume_coloana_cheie_primara** as a primary key and **nume_tabela.nume_coloana_cheie_secundara** as a foreign key

# :pushpin: Database Queries

## :white_check_mark: DDL Data Definition Language 
Statements are used to manipulate MySQL database schema objects. Examine the use of the CREATE, ALTER, and DROP statements to create, modify, and maintain MySQL databases, tables, and views.
The following instructions were written in the scope of CREATING the structure of the database (CREATE INSTRUCTIONS)

### :heavy_check_mark: 1.We created the database : InventoryPatrimonyLocality
```
create database InventarPatrimoniuLocalitate;
```
### :heavy_check_mark: 2.We have created the table " Patrimoniu " :
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
### :heavy_check_mark: 3.We have created the table "AchizitiiPublice"
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
### :heavy_check_mark: 4.Delete table AchizitiPublice.
```
drop table AchizitiiPublice;
```
### :heavy_check_mark:  5.I recreated the table AchizitiiPublice
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
#### :white_check_mark: After the database and the tables have been created, a few ALTER instructions were written in order to update the structure of the database, as described below:

### :heavy_check_mark: I changed the number of text cases in the "Denumire" column :
```
alter table Patrimoniu
modify Denumire varchar(30);
```
### :heavy_check_mark: I changed the column name from "Observatii" to "Categorie".
```
alter table Patrimoniu 
change Observatii Categorie varchar(20);
```
### :heavy_check_mark: I changed the number of text cases in the "Denumire" column.
```
alter table Patrimoniu
modify Denumire varchar(30);
```
### :heavy_check_mark: I visualized the data in the "Patrimoniu" table
```
select * from Patrimoniu;
```




## :white_check_mark: DML (Data Manipulation Language)
In order to be able to use the database I populated the tables with various data necessary in order to perform queries and manipulate the data. In the testing process, this necessary data is identified in the Test Design phase and created in the Test Implementation phase.

Below you can find all the insert instructions that were created in the scope of this project:
### :heavy_check_mark: We entered data in the "Patrimoniu" table:
```
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
```
### :heavy_check_mark:Model with data entry in the table by department: 

 |ID|Departament|Denumire|UM|Cantitate_faptic|Cantitate_scriptic|Pret_unitar|Valoare|Diferenta_plus|Diferenta_minus|Categorie|
 |:-:|:----:|:---:|:-:|:-:|:-:|:-:|:--:|:-:|:-:|:--:|
 |1|Birou Caserie|Dulap 2 usi|buc|1|1|450|450|0|0|Mobilier|

 ![Tabel Patrimoniu](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/TABEL%20PATRIMONIU.jpg)

 ### :heavy_check_mark: I have inserted two more rows in the table "Patrimoniu".
```
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(85,'Birou Secretar','Notebook McBook','buc',1,1,25900,25900,0,0,'Echipamente IT');
```

### :heavy_check_mark: I inserted another row in the table "Patrimoniu".
```
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(88,'Birou Secretar','Multifunctional Brother','buc',1,1,2800,2800,0,0,'Echipamente IT');
```
### :heavy_check_mark:  We entered data in the "AchizitiiPublice" table:
```
insert into AchizitiiPublice(ID,Denumire,UM,Cantitate,Pret_unitar,Valoare,Departamentul,Document_intrare,Data_achizitiei) values
(1,'Server HP','buc',1,36800,36800,'BirouContabilitate',568989,'2024-01-18'),
(2,'Multifunctional Brother','buc',1,2800,2800,'BirouUrbanism',556322,'2024-01-20');
```
### :heavy_check_mark:  We add to the "Patrimoniu" table the purchases made with the Insert into command.
```
INSERT INTO Patrimoniu (ID,Departament, Denumire, UM, Cantitate_faptic, Cantitate_scriptic, Pret_unitar, Valoare, Diferenta_plus, Diferenta_minus, Categorie)
VALUES 
(89,'Birou Contabilitate','Server HP','buc',1,1,36800,36800,0,0,'Echipamente IT'),
(90,'BirouUrbanism','Multifunctional Brother','buc',1,1,2800,2800,0,0,'Echipamente IT');
```

#### :white_check_mark: After the insert, in order to prepare the data to be better suited for the testing process, I updated some data in the following way:

### :heavy_check_mark: I corrected the mistake in row 15 of the table.
```
UPDATE Patrimoniu
SET Valoare = 1 , Diferenta_minus = 0
WHERE ID = 15;
```

### :heavy_check_mark: I corrected typos in the column "Categorie".
```
UPDATE Patrimoniu
SET Categorie = 'Mobilier'
WHERE ID = 60;
```
### :heavy_check_mark: We corrected the numbering of IDs.
```
UPDATE Patrimoniu
SET ID = '86'
WHERE ID = 88;
```
### :heavy_check_mark:  Corrected IDs. 
```
UPDATE Patrimoniu
SET ID = '88'
WHERE ID = 90;
```

## :white_check_mark: DQL (Data Query Language)
After the testing process, I deleted the data that was no longer relevant in order to preserve the database clean:

In order to simulate various scenarios that might happen in real life I created the following queries that would cover multiple potential real-life situations:

### :heavy_check_mark: We queried the Heritage table to see the product with the lowest value in the heritage of the locality.
```
SELECT MIN(Valoare)
FROM Patrimoniu;
```
select * from Patrimoniu;

### :heavy_check_mark: We questioned how many records we have in the table "Patrimoniu".
```
SELECT COUNT(*)
FROM Patrimoniu;
```

### :heavy_check_mark: We questioned how many IDs of the products registered in the "Patrimoniu" table have a value greater than 2500 lei.
```
SELECT COUNT(Valoare)
FROM Patrimoniu
WHERE Valoare > 2500;
```
### :heavy_check_mark: We've calculated the total value of the "Value" column in the "Patrimoniu" table to see the total heritage value.
```
SELECT SUM(Valoare) AS total
FROM Patrimoniu;
```

### :heavy_check_mark: We have centralized the data from the "Patrimoniu" table by Category. 
```
SELECT COUNT(ID), Categorie
FROM Patrimoniu
GROUP BY Categorie;
```

### :heavy_check_mark: I made an Inner Join between the "Patrimoniu" and "Achizitii Publice" tables based on the name field in order to check all the patrimony investments were made through public aquisitions
```
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
INNER JOIN Patrimoniu ON Patrimoniu.Denumire = AchizitiiPublice.Denumire;
```
### :heavy_check_mark:  We compared the Value column with the Inner Join command in the "Patrimoniu" and "Achizitii Publice" tables to see if the value of the products registered in the "Achizitii publice" table corresponds to the value of the products purchased and registered in the "Patrimoniu" table.
```
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
INNER JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;
```

### :heavy_check_mark:  We compared the Value column with the Left Join command in the "Patrimoniu" and "Achizitii Publice" tables to see if the value of the products registered in the "Patrimoniu" table corresponds to the value of the products purchased and registered in the "Achizitii Publice" table.
```
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
LEFT JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;
```
### :heavy_check_mark: We compared the Value column with the Left Join command in the "Patrimoniu" and "Achizitii Publice" tables to see if the value of the products registered in the Heritage table corresponds to the value of the products purchased and registered in the"Achizitii Publice" table.
```
SELECT Patrimoniu.Valoare, Patrimoniu.Valoare
FROM AchizitiiPublice
RIGHT JOIN Patrimoniu ON Patrimoniu.Valoare = AchizitiiPublice.Valoare;
```

### :heavy_check_mark:  We compared the Name column with the Right Join command in the "Patrimoniu" and "Achizitii Publice" tables to see if the names of the products registered in the "Achizitii Publice" table correspond to the names of the products purchased and registered in the "Patrimoniu" table.
```
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
RIGHT JOIN Patrimoniu ON Patrimoniu.Denumire = AchizitiiPublice.Denumire;
```

### :heavy_check_mark:  We compared with the Cross Join command the "Patrimoniu" and "Achizitii Publice" tables to see if the names of the products registered in the "Achizitii Publice" table correspond to the names of the products purchased and registered in the "Patrimoniu" table.
```
SELECT Patrimoniu.Denumire, Patrimoniu.Denumire
FROM AchizitiiPublice
CROSS JOIN Patrimoniu Where Patrimoniu.Denumire = AchizitiiPublice.Denumire;
```
### :heavy_check_mark:  We compared with the Cross Join command the "Patrimoniu" and "Achizitii Publice" tables to see if the ID of the products registered in the "Achizitii Publice" table corresponds to the IDs of the purchased products and registered in the "Patrimoniu" table.
```
SELECT Patrimoniu.Pret_Unitar, Patrimoniu.Pret_Unitar
FROM AchizitiiPublice
CROSS JOIN Patrimoniu Where Patrimoniu.Pret_Unitar = AchizitiiPublice.ID;
```
### :heavy_check_mark:  We queried the "Patrimoniu" table to see in which departments the product "Papilon chair" is found.
```
SELECT * FROM Patrimoniu
WHERE Denumire = 'scaun papilon' OR departament = '*';
```
### :heavy_check_mark: We queried the "Patrimoniu" table to see in which departments there are products from the IT Equipment category.
```
SELECT * FROM Patrimoniu
WHERE Categorie = 'Echipamente IT' OR departament = '*';
```
### :heavy_check_mark:  We queried the "Patrimoniu" table to see in which departments the product "Canon Printer" is found.
```
SELECT * FROM Patrimoniu
WHERE Denumire = 'Imprimanta Canon' OR departament = '*';
```
### :heavy_check_mark:  We queried the "Patrimoniu" table to see in which department there are no products from the "Mobilier" category.
```
SELECT * FROM Patrimoniu
WHERE NOT Categorie = 'Mobilier';
```
### :heavy_check_mark:  We selected from the "Patrimoniu" table the headings Name, Department and Value
```
SELECT Denumire, Departament, Valoare
FROM Patrimoniu;
```
### :heavy_check_mark:  We queried the "Patrimoniu" table to find out which products begin with the letter "i".
```
SELECT * FROM patrimoniu
WHERE Denumire LIKE 'i%';
```

### :heavy_check_mark:  We queried the "Patrimoniu" table to find out which products begin with the letter "d".
```
SELECT * FROM patrimoniu
WHERE Denumire LIKE 'd%';
```
### :heavy_check_mark:  We queried the Heritage table to find out the average value column.
```
SELECT AVG(Valoare)
FROM Patrimoniu;
```
### :heavy_check_mark:  We queried the "Patrimoniu" table to find out the average value column for products with a value greater than or equal to 100.
```
SELECT AVG(Valoare)
FROM Patrimoniu
WHERE Valoare >= 100;
```

### :heavy_check_mark: We calculated the total value of the "Value" column.
```
SELECT SUM(Valoare)
FROM Patrimoniu;
```


# :pushpin: Subquery

## :heavy_check_mark: We created two more tables for querying them with the subquery function

### :heavy_check_mark: We created the table " Angajati".
```
Create table Angajati
(angajat_id varchar(10),
nume_angajat varchar(30),
oras varchar(20),
stare_civila varchar(25),
id_departament varchar(10),
departament varchar(25),
salar int,
data_angajarii date
);
```
### :heavy_check_mark: We created the table "Departamente".

```
Create table Departamente
(nr_crt int,
nume_departament varchar(30),
id_departament varchar(20),
primary key(id_departament)
);
```
### :heavy_check_mark: We enter data in the "Angajati" table.
```
Insert into Angajati(angajat_id,nume_angajat,oras,stare_civila,id_departament,departament,salar,data_angajarii) VALUES
('001','Popescu Ioan','Cluj-Napoca','Casatorit','1001','Resurse Umane',5800,'2018-05-13'),
('002','Fildan Pavel','Timisoara','Casatorit','1005','Administratie',7300,'2015-06-01'),
('003','Filip Alexandru','Botosani','Necasatorit','1002','Departamnet IT',8500,'2021-03-17'),
('004','Serbanescu Paul','Bucuresti','Casatorit','1003','Marketing',5100,'2017-08-01'),
('005','Popovici Ioan','Arad','Casatorit','1002','Departamnet IT',8500,'2021-04-21'),
('006','Csortan Gabriela','Oradea','Casatorita','1004','Vanzari',6350,'2012-05-22'),
('007','Paraschivescu Claudia','Bucuresti','Divortata','1003','Marketing',5750,'2014-09-01'),
('008','Maletici Florin','Alba Iulia','Necasatorit','1002','Departamnet IT',9500,'2011-02-22'),
('009','Popa Elena','Timisoara','Casatorita','1005','Administratie',10500,'2011-08-17'),
('010','Maris Alina','Cluj Napoca','Necasatorita','1004','Vanzari',6400,'2019-11-05');
```
### :heavy_check_mark: We enter data in the "Departamente" table.
```
Insert Into Departamente(nr_crt,nume_departament,id_departament) VALUES
('001','Resurse Umane','1001'),
('002','Departament IT','1002'),
('003','Marketing','1003'),
('004','Vanzari','1004'),
('005','Administratie','1005');
```
### :heavy_check_mark: Subquery that returns multiple columns as output to the parent query.
```
select nume_angajat, salar, oras, departament
FROM Angajati
WHERE (angajat_id, departament) in
(SELECT angajat_id, nume_departament FROM
Departamente);
```
### :heavy_check_mark: Retrieve salary details for salarys higher that the average.
```
select nume_angajat, salar, stare_civila
from Angajati
Where angajat_id IN 
(SELECT angajat_id FROM
Angajati Where salar > (SELECT avg(salar) FROM Angajati));
```

# C.R.U.D
### :pushpin: C=Create, R=Read, U=Update, D=Delete

### :heavy_check_mark: Create
```
Insert into Angajati(angajat_id,nume_angajat,oras,stare_civila,id_departament,departament,salar,data_angajarii) VALUES
('011','Vasile Lucian','Brasov','Necasatorit','1001','Resurse Umane',6150,'2023-06-05');
```

### :heavy_check_mark: Read
```
select nume_angajat, oras, salar, departament
from angajati
where departament = (
   select departament
   from Angajati
   where nume_angajat = 'Filip Alexandru'
   );
  ```
 
### :heavy_check_mark: Update 
```
update angajati
set departament = (
select departament
from angajati
where nume_angajat = 'Fildan Pavel'
)
where nume_angajat = 'Filip Alexandru';
```

### :heavy_check_mark: Delete
```
delete from angajati
where departament = (
select departament
from angajati
where nume_angajat = 'Popa Elena'
);
```

![Reverse Engineering Diagram](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/Reverse%20Engineering%20Diagram%201.jpg)

# :pushpin: Conclusion

In the Mysql course we learned to create a database with the help of MySQL Workbench. 
In the first phase I learned the three languages used to create a database correctly.
### :heavy_check_mark: DDL - The Data Definition Language, or DDL, is made up of the commands responsible for creating, editing and deleting SQL tables. These commands are CREATE TABLE, ALTER TABLE, and DROP TABLE.
### :heavy_check_mark: DML - The Data Manipulation Language, or DML for short, is the group of commands responsible for manipulating data in a database; this generally entails inserting, editing, or deleting rows in SQL tables.The commands described above (INSERT, UPDATE, and DELETE) represent the main SQL operations for data manipulation and thus make up the Data Manipulation Language.
### :heavy_check_mark: DQL - The Data Query Language, or DQL for short, is the group of commands responsible for querying data from a database. The principal DQL command in SQL is the SELECT command, which retrieves data from one or more tables.
### We learned to populate a table with data, modify data in a table, delete data from tables, delete tables, use primary_key, query tables, modify data in columns, link tables, query columns or rows in a table.






































