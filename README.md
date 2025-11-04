create database workshop;

use workshop;

show tables;

desc clients;

desc vehicle;



-- Criando a tabela cliente.

create table clients(

&nbsp;	idclients int primary key not null,

&nbsp;   Pname varchar(45),

&nbsp;   Minit char(3),

&nbsp;   Lname varchar(45),

&nbsp;   CPF char(11),

&nbsp;   Address varchar(255),

&nbsp;   Email varchar(45),

&nbsp;   typePersol enum('PF','PJ'),

&nbsp;   constraint unique\_cpf unique (CPF)

);



-- Criando a tabela Veículo.

create table vehicle(

&nbsp;	idvehicle int primary key not null,

&nbsp;	idvehiclients int,

&nbsp;	mark varchar(45),

&nbsp;   model varchar(45),

&nbsp;   plate char(10),

&nbsp;   years int,

&nbsp;   constraint fk\_vehiclients foreign key (idvehiclients) references clients (idclients)

);



-- Criando a tabela funcionário.

&nbsp; create table employee(

&nbsp;	idemployee int primary key not null,

&nbsp;	Pname varchar(45),

&nbsp;	CPF char(11),

&nbsp;	positionn varchar(45),

&nbsp;	salary float,

&nbsp;	tell char(9),

&nbsp;	Address varchar(255),

&nbsp;   constraint unique\_cpf unique (CPF)

&nbsp; );

&nbsp; 

&nbsp; -- Criando a tabela serviço.

&nbsp;create table service(

&nbsp;	idservice int primary key not null,

&nbsp;	description\_Service varchar(100),

&nbsp;	valuess float

&nbsp;);

&nbsp;

&nbsp;-- Criando a tabela Ordem de serviço.

&nbsp;create table orderService(

&nbsp;	idOrderService int primary key not null,

&nbsp;	idorclients int,

&nbsp;	idoremployee int,

&nbsp;	idorvehicle int,

&nbsp;	openingDate date not null,

&nbsp;	closeningDate date,

&nbsp;	statusOrder enum('Aberta','Em andamento','Concluído','Cancelado') default 'Aberta',

&nbsp;	constraint fk\_orclients foreign key (idorclients) references clients (idclients),

&nbsp;	constraint fk\_oremployee foreign key (idoremployee) references employee (idemployee),

&nbsp;	constraint fk\_orvehicle foreign key (idorvehicle) references vehicle (idvehicle)

&nbsp;);

&nbsp;

&nbsp;-- Criando a tabela Order de serviço\_serviço.

&nbsp;create table orderservice\_service(

&nbsp;	idosorder\_service int,

&nbsp;	idosservice int ,

&nbsp;	quantity int default 1 ,

&nbsp;	primary key (idosorder\_service,idosservice),

&nbsp;	constraint fk\_osorder\_service foreign key (idosorder\_service) references orderservice(idorderservice),

&nbsp;	constraint fk\_osservice foreign key (idosservice) references service (idservice)

&nbsp;);

&nbsp;

&nbsp;-- Criando a tabela Pagamento.

&nbsp;drop table payment;

&nbsp;create table payment(

&nbsp;	idpayment int primary key not null,

&nbsp;   idclients\_pay int,

&nbsp;   idOrderservice\_pay int,

&nbsp;   totalValue float,

&nbsp;   typePayment enum('Pix','Dinheiro','Boleto','Cartão de Débito','Cartão de Crédito'),

&nbsp;   statusPayment enum ('Pago','Pendente') default 'Pendente',

&nbsp;   constraint fk\_clients\_pay foreign key (idclients\_pay) references clients (idclients),

&nbsp;   constraint fk\_orderservice\_pay foreign key (idorderservice\_pay) references orderservice (idorderservice)

);



-- Criando a tabela Produto.

create table product(

&nbsp;	idproduct int primary key not null,

&nbsp;   NameProduct varchar(45),

&nbsp;   description\_Product varchar(45),

&nbsp;   unit\_price float

);



-- Criando a tabela Fornecedor.

create table supplier(

&nbsp;	idsupplier int primary key not null,

&nbsp;   SocialName varchar(45),

&nbsp;   CNPJ char(11),

&nbsp;   tell char(9),

&nbsp;   email varchar(45),

&nbsp;   Address varchar(255),

&nbsp;   constraint unique\_cnpj unique (CNPJ)

);



-- Criando a tabela Produto\_fornecedor.

create table product\_supplier(

&nbsp;	idpsProduct int,

&nbsp;	idpsSupplier int,

&nbsp;   quantity int,

&nbsp;   primary key(idpsProduct,idpsSupplier),

&nbsp;   constraint fk\_psProduct foreign key (idpsProduct) references product (idProduct),

&nbsp;   constraint fk\_psSupplier foreign key (idpsSupplier) references supplier (idsupplier)

);



-- Criando a tabela Estoque.

&nbsp; create table stocks(

&nbsp;	idstocks int primary key not null,

&nbsp;   Quantity int not null

);



-- Criando a tabela Produto\_estoque.

create table product\_storage(

&nbsp;	idpgProduct int,

&nbsp;   idpsStorage int,

&nbsp;   Location varchar(45),

&nbsp;   primary key (idpgProduct,idpsStorage),

&nbsp;   constraint fk\_pgProduct foreign key (idpgProduct) references product (idProduct),

&nbsp;   constraint fk\_psStorage foreign key (idpsStorage) references stocks (idstocks)

);

&nbsp;   

