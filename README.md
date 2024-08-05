# ToDo List🚀

Este projeto é uma aplicação de lista de tarefas (ToDo List) que permite aos usuários gerenciar suas tarefas 
de forma eficiente. Com um backend robusto em Django e um frontend dinâmico em React, a aplicação é dockerizada 
para facilitar o desenvolvimento e a implantação.



## Tecnologias Utilizadas 🛠️

 ![Django Logo](https://img.shields.io/badge/Django-092E20?style=flat&logo=django&logoColor=white)
![React Logo](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
 ![PostgreSQL Logo](https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Docker Logo](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![JWT Logo](https://img.shields.io/badge/JWT-000000?style=flat&logo=json-web-tokens&logoColor=white)


## Backend - Django 🐍

O backend é desenvolvido com Django e utiliza PostgreSQL como banco de dados. Ele oferece uma API RESTful 
que implementa autenticação baseada em JWT para proteger endpoints e gerenciar a segurança dos usuários. 
A API é projetada para interagir de forma eficiente com o frontend React, fornecendo os dados e 
funcionalidades necessários para uma experiência de usuário completa.


### Estrutura do Projeto

- `todo_project/`: Diretório principal do Django.
  - `Dockerfile`: Arquivo para construir a imagem Docker do backend.
  - `manage.py`: Comando principal para gerenciar o projeto Django.
  - `todo_project/`: Contém a configuração do projeto Django.
    - `settings.py`: Configurações do Django.


## Frontend - React ⚛️

O frontend é desenvolvido com React e se comunica com o backend Django via API.

### Estrutura do Projeto

- `todo_frontend/`: Diretório principal do frontend React.

## Docker 🐳

Docker é utilizado para orquestrar os containers do backend e do frontend.

### Estrutura dos Arquivos Docker

- **Dockerfile (Backend)**: Define como construir a imagem Docker para o Django.
- **Dockerfile (Frontend)**: Define como construir a imagem Docker para o React.
- **docker-compose.yml**: Arquivo de orquestração que define como os containers interagem e são configurados.
- **Makefile**: Arquivo para facilitar o gerenciamento de comandos Docker e outras tarefas.


## Como Executar o Projeto

1. **Clone o Repositório**:
   ```
   git clone https://github.com/vitoriarntrindade/todo-list.git
   cd todo-list

  
2. **Crie um arquivo .env na raiz do seu repositório com placeholders para todas as variáveis de ambiente necessárias. Certifique-se de ter PostgreSQL instalado e configurado e uma SECRET_KEY do Django:**
   ```
   DATABASE_NAME='nome do seu banco de dados'
   DATABASE_USER='seu username'
   DATABASE_PASSWORD='sua senha'
   DATABASE_HOST='localhost'
   DATABASE_PORT=5434
   SECRET_KEY ='sua chave secreta gerada pelo django'
   DEBUG=TRUE
   REACT_APP_BACKEND_URL=http://127.0.0.1:8000

3. **Para gerar uma nova SECRET_KEY, você pode executar o seguinte comando Python:**
   ```
   from django.core.management.utils import get_random_secret_key
   print(get_random_secret_key())
   
4. **Comando make file para construir e subir as imagens dos containers**:
 ```
    make build-up
```
   
    
Este comando constrói as imagens dos containers e os inicia. Ele é equivalente a executar **docker-compose 
build seguido por docker-compose up --build**. 

Isso garante que as últimas mudanças no código e na configuração 
sejam aplicadas e que todos os containers necessários (backend, frontend e banco de dados) sejam iniciados.

5. **Aplicar Migrações no Banco de Dados**
 
 ```
    make migrate
```

Este comando aplica as migrações do Django ao banco de dados. 

Migrações são uma maneira de aplicar
alterações no esquema do banco de dados, como criar tabelas e colunas, e garantir que o banco de dados 
esteja atualizado com as últimas mudanças definidas nos arquivos de migração do Django.

6. **Criar um Superusuário para o Django Admin**

 ```
    make createsuperuser
```


Este comando cria um superusuário para o Django Admin. 

O superusuário é um usuário com permissões administrativas completas que pode acessar a interface de administração do Django para 
gerenciar o conteúdo e a configuração do site. Você será solicitado a fornecer um nome de usuário,
e-mail e senha para o superusuário.

7. **Abra seu navegador e acesse**:

   ```
   http://localhost:3000
   ```

  🌐  A aplicação react estará rodando na porta 3000.
  
  🌐  O backend estará rodando na porta 8000.
