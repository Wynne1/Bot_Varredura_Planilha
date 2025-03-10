# Integração de bot com planilha, usando openpyxl e scrapy

### Fazer a criação e ativação do ambiente virtual, logo em seguida das instalações necessárias para o projeto
    python -m venv "nome_do_ambiente_virtual"
    .\nome_do_ambiente_virtual\Scripts\activate
    pip install openpyxl scrapy
### Criando o projeto com scrapy e mudando para a pasta do projeto
    scrapy startproject nome_do_projeto
    cd .\nome_do_projeto\
### Dentro do projeto, navegar até a pasta que possui o nome do projeto e abrir spiders, criando um arquivo proxyspider.py
    O código presente aqui dentro faz a navegação até o site e extrai as informações da tabela:
    Proxy name; 
    domain; 
    country; 
    speed; 
    popularity
###  Criar uma pipeline para os dados serem retornados e processados:
    Definindo como a planilha será aberta:

    Definindo como a planilha será processada:

    Definindo como a planilha vai ser encerrada:
