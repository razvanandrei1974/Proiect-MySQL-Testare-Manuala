# MySQL
# Creare baza de date
create database CinemaTMTA12 ;
use cinemaTMTA12;

create table Filme 
(
ID int not null auto_increment,
NumeFilm varchar(25) not null,
IDGen int not null,
DataStart date,
DataFinal date,
Durata int,
IDRating int,
IDSala int,
primary key(ID)
);

# descrie structura unei tabele
select * from filme;

# vizualizare tabele
desc filme;

create table GenFilm
(
ID int not null,
TipGen varchar(15)
);

# redenumire nume tabele
rename table GenFilm to GenFilme;

# modificare tip date din coloana
alter table GenFilme 
modify TipGen varchar(20);

desc GenFilme;

# modificare nume coloana din tabel 
alter table GenFilme 
change TipGen Gen varchar(20);

desc GenFilme;

select * from GenFilme;

# Stergere coloana
alter table GenFilme
drop column Gen;

# adaugare coloana
alter table GenFilme
add TipGen varchar(20);

# adaugare PK primary-key
alter table GenFilme
add primary key(ID);

desc GenFilme;

# bool true or false
create table Sala
(
ID int not null auto_increment primary key,
Nr_locuri int not null,	
VIP bool 
);

create table Rating
(
ID int auto_increment,
Valoare_Rating int 
);

create table Test
(
ID int 
);

#stergere tabele
drop table Test;

# legatura intre tabele si coloane -adaugare chei straine
alter table Filme
add foreign key(IDGen) references Sala(ID);

alter table Filme
add foreign key(IDSala) references GenFilme(ID);

# Curs 27.10.2023

select * from Filme;
insert into filme(NumeFilm,IDGen,DataStart,DataFinal,Durata,IDRating,IDSala) values
('Titanic',3,'2023-10-28','2023-11-03',120,4,6),
('Indiana Jones',2,'2023-11-05','2023-11-10',185,4,2),
('Mission Imposibile',2,'2023-11-09','2023-11-16',90,5,4),
('The Godfather',5,'2023-11-18','2023-11-25',240,5,2);

insert into GenFilme(ID,TipGen) values
(2,'actiune'),
(3,'horror'),
(4,'comedie'),
(5,'drama'),
(6,'dragoste'),
(7,'mister'),
(8,'sci fi');


select * from genfilme;

select * from rating;

insert into rating(Valoare_Rating) values
(0),
(1),
(2),
(3),
(4),
(5);

select * from rating;

select * from sala;

insert into sala(Nr_locuri,VIP) values
(100,true),
(125,false),
(75,true),
(85,true),
(185,false),
(130,false);

select * from filme;

select * from filme;


create table TabelaTest
(ID int auto_increment primary key,
test varchar(10));

ALTER TABLE tabelatest AUTO_INCREMENT = 1;

select * from tabelatest;

# Afisati toate datele pentru filmul Titanic

select * from filme where NumeFilm='Titanic';

select * from filme where id=10;

# Afisati toate filmele a caror durata este de doua ore

select * from filme where durata=2;

# Afisati toate datele din tabela Sala
select * from sala;

# Afisati numele tuturor filmelor care ruleaza in cinema 

select NumeFilm from filme;

# Afisati detaliile despre toate filmele a caror durata este mai mica de 4 ore

select * from filme where durata < 3;

select * from filme;

select * from filme where DataStart > 2023-11-05;

# Afisati numele filmelor
select NumeFilm from filme where DataStart between '2023-10-28' and '2023-11-18';   

select NumeFilm from filme where (DataStart between '2023-10-28' and '2023-11-18') 
and (DataFinal between '2023-11-09' and '2023-11-18');

select NumeFilm from filme where DataStart > '2023-10-28' and DataStart <'2023-11-18';

# Afisati numarul total de filme a caror durata este de 2 ore

select count(*)from filme where durata=2;
