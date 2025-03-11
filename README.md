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
###  Criar uma pipeline para os dados serem retornados e processados(pipelines.py):
    Definindo como a planilha será aberta:
    - Abre a planilha na página atual
    - Adiciona os CAMPOS que são exatamente os que estão no arquivo proxyspider.py
    
    Definindo como a planilha será processada:
    - Processa os "item" na classe ItemAdapter
    - Obtem o item de acordo com o nome da coluna -> self.sheet.append([adapter.get('Proxy name', adapter.get('domain') e faz para todos os outros...]

    Definindo como a planilha vai ser encerrada:
    - Passa o caminho específico através do arquivo settings.
    - No settings.py cria-se uma variável XLSX_PATH ='projetoproxies.xlsx"
    - Ainda dentro do settings.py descomentar "ITEM_PIPELINES" e colocar o nome da classe criada no pipelines.py, no caso do projeto : .XLSXPipeline
    - Fazer a importação do settings no pipelines.py : projetobotproxies.settings
    - Passa o valor do settings na variável save
### Rodar a aplicação:
    scrapy crawl nome_do_bot
