# Formula1 DB

# Modelo de Banco de Dados para Fórmula 1
Este script SQL cria um modelo de banco de dados para armazenar informações relacionadas à Fórmula 1, incluindo países, equipes, pilotos, circuitos, corridas e resultados de corridas. A seguir, uma descrição detalhada de cada tabela:

# Tabela paises
Armazena informações sobre países relacionados à Fórmula 1.
Colunas:
sigla (varchar(3)): Sigla do país (chave primária).
nome (varchar(100)): Nome do país.
bandeira (varchar(255)): Caminho para a imagem da bandeira.
hino (varchar(255)): Caminho para o arquivo de áudio do hino nacional.

# Tabela equipes
Registra as equipes que participam da Fórmula 1.
Colunas:
id (int): Identificador único da equipe (chave primária, autoincremento).
nome (varchar(100)): Nome da equipe.
escudo (varchar(255)): Caminho para o escudo da equipe.
id_pais (varchar(3)): Sigla do país da equipe (chave estrangeira referenciando paises).

# Tabela pilotos
Armazena informações sobre os pilotos de Fórmula 1.
Colunas:
id (int): Identificador único do piloto (chave primária, autoincremento).
nome (varchar(255)): Nome do piloto.
altura (decimal(9,2)): Altura do piloto.
peso (decimal(9,2)): Peso do piloto.
dt_nascimento (date): Data de nascimento do piloto.
numero_carro (int): Número do carro do piloto.
id_pais (varchar(3)): Sigla do país de origem do piloto (chave estrangeira referenciando paises).
id_equipe (int): Identificador da equipe do piloto (chave estrangeira referenciando equipes).

# Tabela circuitos
Armazena informações sobre os circuitos onde ocorrem corridas.
Colunas:
id (int): Identificador único do circuito (chave primária, autoincremento).
nome (varchar(255)): Nome do circuito.
id_paises (varchar(3)): Sigla do país onde o circuito está localizado (chave estrangeira referenciando paises).

# Tabela corridas
Registra informações sobre corridas específicas.
Colunas:
id (int): Identificador único da corrida (chave primária, autoincremento).
nome (varchar(255)): Nome da corrida.
id_circuito (int): Identificador do circuito onde a corrida ocorre (chave estrangeira referenciando circuitos).

# Tabela pilotos_corridas
Armazena os resultados das corridas para cada piloto.
Colunas:
id_piloto (int): Identificador do piloto (chave estrangeira referenciando pilotos).
id_corrida (int): Identificador da corrida (chave estrangeira referenciando corridas).
dt_corrida (date): Data da corrida.
posicao (int): Posição final do piloto na corrida.
pontos (int): Pontuação obtida pelo piloto na corrida.
tempo (varchar(100)): Tempo total da corrida para o piloto.

# Consultas e Visualização
SHOW COLUMNS FROM paises;: Exibe as colunas da tabela paises.
SHOW COLUMNS FROM equipes;: Exibe as colunas da tabela equipes.
SHOW TABLES;: Lista todas as tabelas no banco de dados.

Este modelo de banco de dados permite armazenar e consultar informações detalhadas sobre países, equipes, pilotos, circuitos, corridas e resultados de corridas relacionados à Fórmula 1. Pode ser estendido e adaptado conforme necessário para atender aos requisitos específicos de um sistema de informações para a Fórmula 1.
