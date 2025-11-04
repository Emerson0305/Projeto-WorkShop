-- Inserindo dados na tabela cliente;
use workshop;
select * from clients;
insert into clients (idclients,Pname,minit,Lname,CPF,Address,Email,typePersol)
values(1,'Emerson','D','Santos',01212345678,'Rua deputado jose tavares 147,São Paulo-SP','emersondddd@gmail.com','PF'),
	  (2,'Cleiton','S','Araujo',01234567891,'Avenida Barros 200,Campina Grande-PB','cleiton1246@hotmail.com','PF'),
      (3,'Gabriel','F','Camargo',32165478910,'Rua Campos godoi 145,Goias-GO','gabrielcamargo@gmail.com','PJ'),
      (4,'Ana Maria','S','Silva',45678912320,'Rua Pedro barros 4667,Paraido do Norte-PR',null,'PF'),
      (5,'Carla','P','Gomes',78945612350,'Avenida Brasil 1466,Cabo branco-PB',null,'PF'),
      (6,'Bianca','M','Maria',12398745610,'Rua treze de maio 4000,Niterói_RJ','biancamaria@hotmail.com','PF'),
      (7,'Douglas',null,'Santos',07346678941,'Rua Paranavai 5000,Blumenau-SC',null,'PF');
      
-- Inserindo dados na tabela Veiculos.
select * from vehicle;
insert into vehicle(idvehicle,idvehiclients,mark,model,plate,years)
values(1,1,'Gol','Volkswagen','asj1234561',2020),
      (2,2,'Polo','Volkswagen','ksi2000111',2009),
      (3,3,'Cruze','Chevrolet','kjhg14569',2018),
      (4,4,'Fusion','Ford','ghfty12345',2016),
      (5,5,'Corolla','Toyota','aaas12345',2022),
      (6,6,'Honda Civic','Honda','hhhhh45555',2024),
      (7,7,'Fiat Toro','Fiat','kkkkk20000',2025);
      
-- Inserindo dados na tabela funcionário.
select * from employee;
insert into employee(idemployee,Pname,CPF,positionn,salary,tell,Address)
values(1,'João',45145617122,'Gerente',4500,837894562,'Rua major 124,Cachoerinha-SP'),
      (2,'Mario',45678912312,'Mecânico',3000,834567892,'Rua Bento freitas 2000,Bela Vista-SP'),
      (3,'Pedro',12345678912,'Mecânico',3500,834567891,'Avenida Grajau 124,Paranavai_SP'),
      (4,'Marcio',56666145679,'Atendente',2500,834561232,'Rua Camargo azul 1245,Brás_Sp'),
      (5,'Everton',99999456789,'Mecânico',3200,831234567,'Avenida Bras 500,Marilia-SP'),
      (6,'Caique',44556124566,'Mecânico',3300,834561234,'Rua Gonçalves 600,Sorocaba-SP'),
      (7,'Paulo',55456789124,'Atendente',2600,831245785,'Rua Brasil 400,Campinas_SP');
      
-- inserindo dados na tabela serviço.
select * from service;
insert into service(idservice,description_service,valuess)
values(1,'Troca de óleo',20),
      (2,'Manutenção',150),
      (3,'Alinhamento',100),
      (4,'Troca de Parabrisa',250),
      (5,'Troca de Pneu',600),
      (6,'Troca da bateria',500),
      (7,'Troca do motor',1000);
      
-- inserindo dados na tabela Ordem de serviço.
select * from orderservice;
insert into orderService(idOrderService,idorclients,idoremployee,idorvehicle,openingDate,closeningDate,statusOrder)
values(1,1,1,1,'2020-05-03','2020-05-20',default),
      (2,2,2,2,'2019-10-10','2019-11-05','Concluido'),
      (3,3,3,3,'2022-06-30','2022-08-01','Em andamento'),
      (4,4,4,4,'2020-11-03','2020-11-30','Cancelado'),
      (5,5,5,5,'2021-10-25','2021-11-01','Aberta'),
      (6,6,6,6,'2025-04-20','2025-05-10','Em andamento'),
      (7,7,7,7,'2023-06-04','2023-06-25','Concluido');
      
-- inserindo dados na tabela;
select * from orderservice_service;
insert into orderservice_service (idosorder_service,idosservice,quantity)
values(1,1,30),
      (2,2,10),
      (3,3,15),
      (4,4,40),
      (5,5,12),
      (6,6,25),
      (7,7,45);
      
-- inserindo dados na tabela Pagamento;
select * from payment;
insert into payment (idpayment,idclients_pay,idOrderservice_pay,totalValue,typePayment,statusPayment)
values(1,1,1,1200,'Pix','Pago'),
      (2,2,2,2000,'Dinheiro','Pago'),
      (3,3,3,2500,'Boleto',default),
      (4,4,4,3000,'Cartão de Débito','Pago'),
      (5,5,5,6000,'Cartão de Crédito','Pendente'),
      (6,6,6,3500,'Pix','Pago'),
      (7,7,7,1000,'Boleto',default);
      
-- inserindo dados na tabela Produto;
select * from product;
insert into Product(idproduct,nameProduct,description_product,unit_price)
values(1,'Motor','Motor de carro',800),
      (2,'Bateria','Bateria de carro',300),
      (3,'Óleo','Troca de óleo',10),
      (4,'Pneu','Troca de pneu',400),
      (5,'Parabrisa','Troca de parabrisa',150),
      (6,'Banco','Banco do carro',450),
      (7,'Volante','Volante do carro',100);
      
-- inserindo dados na tabela Fornecedor;
select * from supplier;
insert into supplier(idsupplier,SocialName,CNPJ,tell,email,Address)
values(1,'Auto Peças Brandão',00080012345,117894561,'autopeças@gmail.com','Rua Beltrão 500,Lagoa seca_PB'),
      (2,'Mauro Peças',80004561000,447894567,null,'Rua das Graças 100,Curitiba_PR'),
      (3,'Freita auto peças',50078945612,557894561,'freitas_peças@hotmail.com','Avenida Santos 600,Rio de janeiro-RJ'),
      (4,'Auto Peças Gomes',45610012312,837894561,'autopeçasgomes@hotmail.com','Avenida Campos 700,Natal-RN'),
      (5,'Cícero Peças',12345678945,661234561,'ciceropeças@gmail.com','Rua da flores 500,Campina Grande-PB'),
      (6,'Marcio auto Peças',78945612312,311234564,'marciopeças@gmail.com','Rua bento freitas 120,Fortaleza-CE'),
      (7,'Auto Peças Bento',60004567456,127894564,'autopeçasbento@hotmail.com','Rua carmo dois 4566,Porto Alegre-RS');
      
-- inserindo dados na tabela Produto fornecedor;
select * from product_supplier;
insert into product_supplier(idpsProduct,idpsSupplier,quantity)
values(1,1,100),
      (2,2,150),
      (3,3,200),
      (4,4,250),
      (5,5,500),
      (6,6,450),
      (7,7,350);
      
-- inserindo dados na tabela Estoque;
select * from stocks;
insert into stocks(idstocks,quantity)
values(1,200),
      (2,150),
      (3,600),
      (4,650),
      (5,700),
      (6,450),
      (7,800);
      
-- inserindo dados na tabela Produto estoque;
select * from product_storage;
insert into product_storage(idpgProduct,idpsStorage,location)
values(1,1,'Rj'),
      (2,2,'PR'),
      (3,3,'RN'),
      (4,4,'PB'),
      (5,5,'CE'),
      (6,6,'SP'),
      (7,7,'SP');

