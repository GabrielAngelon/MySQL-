create database clientes;
use clientes;

drop table cadastro;
create table cadastro (
ID int primary key auto_increment,
nome varchar(40) not null,
endereco varchar(40) not null,
telefone bigint not null
);
desc cadastro;
select * from cadastro;

alter table cadastro modify column foto longblob null;

insert into cadastro (nome, foto) values ( 'Magno', null);

create database OS;
create table tblusers (
	iduser int primary key,
    usuario varchar(50) not null,
    fone varchar(15),
    login varchar(15) not null unique,
    senha varchar(15) not null
);

create table tbclientes (
	idcli int primary key AUTO_INCREMENT,
    nomecli varchar(50) not null,
    endcli varchar(100),
    fonecli varchar(50) not null,
    email varchar(50) default null
);

drop table tblos;
create table tblos (
	os int primary key auto_increment,
    data_os timestamp default current_timestamp,
    equipamento varchar(150) not null,
    defeito varchar(150) not null,
    servico varchar(150),
    tecnico varchar(150),
    valor varchar(150),
    idcli int not null,
foreign key (idcli) references tbclientes(idcli)
);

insert into tblusers(iduser, usuario, fone, login, senha)
values 
(1, 'Gabriel', '93335-2116', 'admin', '123456'),
(2, 'usuario', '3333-3333', 'user', '123456'),
(3, 'Bill Gates', '3333-3333', 'bill', '123456');

insert into tbclientes(nomecli, endcli, fonecli, email)
values
('Linus Torvaldis', 'Rua Shell, 508', '1111-1111', 'linus@lunux.com'),
('Bill Gates', 'Rua Cmd, 508', '2222-2222', 'windows@windows.com'),
('Jeff Bezos', 'Rua Alexa, 508', '3333-3333', 'aws@aws.com'),
('Mark Zuck', 'Rua Insta, 508', '4444-4444', 'face@book.com');

desc table  tblos;
insert into tblos (equipamento, defeito, servico, tecnico, valor, idcli)
values
 ('notebook', 'travado', 'troca de memória', 'Gabriel', 82.30, 1),
 ('computador', 'não liga', 'troca de fonte', 'Bill', 155.50, 2);

select * from tblusers;
select * from tbclientes;
select * from tblos;

