-- Introdução ao Armazenamento e Análise de Dados (IAAD) - BSI/UFRPE
-- Script do Banco de Dados Empresa 

begin;
create schema startup_Abilio; 

use startup_Abilio;

-- Criando as tabelas

create table startup(
	id_startup int not null auto_increment,
	nome_startup varchar(30),
	cidade_sede varchar(30),
	primary key(id_startup));
	
create table linguagem_programacao(
	id_linguagem int not null,
	nome_linguagem varchar(20),
	ano_lancamento year,
	primary key(id_linguagem));
	
create table programador(
	id_programador int not null,
	id_startup int not null,
	nome_programador varchar(30),
	genero char,
	data_nascimento date not null,
	email varchar(35) not null,
	unique(email),
	primary key(id_programador));
	
create table programador_linguagem(
	id_programador int not null,
	id_linguagem int not null,
	
-- populando/carregando as tabelas do banco de dados

insert into startup values
	(10001, "Tech4Toy", "Porto Alegre"),
	(10002, "Smart123", "Belo Horizonte"),
    (10003, "KnowledgeUp", "Rio de Janeiro"),
    (10004, "BSI Next Level", "Recife"),
    (10005, "QualiHealth", "Sao Paulo"),
    (10006, "ProEdu", "Florianopolis");

insert into linguagem_programacao values
	(20001, "Python", 1991),
    (20002, "PHP", 1995),
    (20003, "Java", 1995),
    (20004, "C", 1972),
    (20005, "JavaScript", 1995),
    (20006, "Dart", 2011);
    
insert into programador values
	(30001, 10001, "Joao Pedro", "M", 23/06/1993, "joaop@mail.com"),
    (30002, 10001, "Paula Silva", "F", 10/01/1986, "paulas@mail.com"),
    (30003, 10003, "Renata Vieira", "F", 05/07/1991, "renatav@mail.com"),
    (30004, 10004, "Felipe Santos", "M", 25/11/1976, "felipes@mail.com"),
    (30005, 10001, "Ana Cristina", "F", 19/02/1968, "anac@mail.com"),
    (30006, 10004, "Alexandre Alves", "M", 07/07/1988, "alexandrea@mail.com"),
    (30007, 10002, "Laura Marques", "F", 04/10/1987, "lauram@mail.com");

-- Aplicando a restrição de integridade referencial (chaves estrangeiras - FK)
alter table programador add foreign key(id_startup) references startup(id_startup);
alter table programador_linguagem add foreign key(id_programador) references programador(id_programador);
alter table programador_linguagem add foreign key(id_linguagem) references linguagem_programacao(id_linguagem);
