## Banco de Dados
Foi testadono mysqlLite do Django/Pycharm e com MySQL através do XAMPP

##### Programa
Projeto Criado através do PyCharm

## Através do menu
Crie um novo projeto do tipo Django
<img src="https://github.com/lucasrm1981/CRUD_Django/blob/master/CRUD_Django.png">

## Adicione ao interpretado o Django
<img src="https://github.com/lucasrm1981/CRUD_Django/blob/master/CRUD_Django-02.png">

Comandos:
### Atualização do pip Python
pip install --upgrade pip

### Instalação do Django
pip install django==4.2.9

## Criação da Aplicação
django-admin startapp cursos

## Arquivos alterados
projeto/settings.py
cursos/models.py
cursos/admin.py

### Criação do arquivo das tabelas
python manage.py makemigrations

### Instalação das bases e Tabelas
python manage.py migrate

## Criação do usuário no Pyhon para o Banco
python manage.py createsuperuser

## Rodando o servidor
python manage.py runserver
