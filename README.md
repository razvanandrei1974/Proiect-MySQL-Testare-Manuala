create database Guru99Aplication;

create table NewCustomer
( CustomerName varchar(25) not null,
Gender varchar(25) not null,
DateOfBird date not null,
Adress varchar(25) not null,
City varchar(25) not null,
State varchar(25) not null,
PIN int not null,
MobileNumber varchar(25) not null,
Email varchar(25) not null,
Password varchar(25) not null
);

desc NewCustomer;

alter table NewCustomer
drop column newcustomer;

desc NewCustomer;


create table NewAccount
(
ID int primary key not null,
CustomerID varchar(25) not null,
AccountType varchar(25) not null,
InitialDeposit int not null
);

desc NewAccount;

create table Deposit (
ID int not null primary key,
AccountNo int not null,
Amount int not null,
DescriptionA varchar(25) not null
); 

desc Deposit;

alter table NewCustomer 
change DateOfBird DateOfBirth varchar(20);

select * from NewCustomer;

alter table NewCustomer 
change Password PasswordID varchar(20);

alter table NewCustomer
add ID int;

desc NewCustomer;


insert into NewCustomer(CustomerName,Gender,DateOfBirth,Adress,City,State,PIN,MobileNumber,Email,PasswordID,ID) values
('Ungar Razvan','Male','1974-08-27','Ciocarlei 5','Resita','Caras Severin',658985,'0774903493','r.u@gmail.com',123456,1),
('Ungar Laura','Female','1977-12-23','Ciocarlei 5','Resita','Caras Severin',321654,'0727253635','u.l.r@gmail.com',654321,2);


select * from newcustomer;


insert into NewCustomer(CustomerName,Gender,DateOfBirth,Adress,City,State,PIN,MobileNumber,Email,PasswordID,ID) values
('Fildan Pavel','Male','1983-11-08','Ghurghiului 2','Resita','Caras-Severin',558885,'0753355658','f.p@gmail.com',589898,3);

select * from newcustomer;

insert into NewAccount(ID,CustomerID,AccountType,InitialDeposit) values
(1,207128,'Current',2850),
(2,209858,'Saving',14650);

select * from NewAccount;

insert into Deposit(ID,AccountNo,Amount,DescriptionA) values
(1,123456789,13650,'Cont deschis');

select * from Deposit;
