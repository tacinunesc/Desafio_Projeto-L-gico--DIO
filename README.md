# Desafio Projeto Lógico da DIO

##

## Criação das tabelas:

````bash
$ Create table cliente(
idCliente INT AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(45),
cpf VARCHAR(11),
contato VARCHAR(20),
CONSTRAINT unique_cpf_cliente UNIQUE (cpf));
````

````bash
$ Create table pedido(
idPedido INT AUTO_INCREMENT PRIMARY KEY,
servico VARCHAR(30),
descricao VARCHAR(255),
confirmado ENUM( '1- Pedido confirmado', '2- Pedido recusado'),
data VARCHAR(10),
idCliente INT,
codEquipe INT);
````

````bash
$ Create table servico(
idServico INT AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(30),
descricao VARCHAR(255),
disponivel BOOLEAN,
valor FLOAT,
idOrdem_Servico INT);
````

````bash
$ Create table peca(
idPeca INT AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(30),
descricao VARCHAR(255),
disponivel BOOLEAN,
valor FLOAT,
idOrdem_Servico INT);
````

````bash
$ Create table Ordem_Servico(
idOrdem_Servico INT AUTO_INCREMENT PRIMARY KEY,
valor FLOAT,
STATUS ENUM('Finalizado', 'Em andamento'),
data_de_emissao DATE,
data_de_conclusao DATE,
idPedido INT);
````

````bash
$ Create table equipe(
codEquipe INT  PRIMARY KEY,
nome VARCHAR(30),
endereco VARCHAR(60),
especialidade varchar(30),
equipe ENUM('1- Manutenção Detectiva', '2- Manutenção Corretiva', '3- Manutenção Preventiva', '4- Manutenção Preditiva');
````
##

## Inserção das chaves estrangeiras

````bash
$ ALTER TABLE pedido ADD FOREIGN KEY(idCliente) REFERENCES cliente (idCliente)
ALTER TABLE pedido ADD FOREIGN KEY(codEquipe) REFERENCES equipe (codEquipe)
ALTER TABLE servico ADD FOREIGN KEY(idOrdem_Servico) REFERENCES Ordem_Servico (idOrdem_Servico)
ALTER TABLE peca ADD FOREIGN KEY(idOrdem_Servico) REFERENCES Ordem_Servico (idOrdem_Servico)
ALTER TABLE Ordem_Servico ADD FOREIGN KEY(idPedido) REFERENCES pedido (idPedido)
````
##

## Inserção de dados na tabela

````bash
$
````


