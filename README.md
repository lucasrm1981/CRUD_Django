## Banco de Dados
Foi testadono mysqlLite do Django/Pycharm e com MySQL através do XAMPP

##### Programa
Projeto Criado através do PyCharm Professional

## Através do menu
Crie um novo projeto do tipo Django pelo PyCharm Professional
<img src="https://github.com/lucasrm1981/CRUD_Django/blob/master/CRUD_Django.png"><br/>
<h3>Caso utilize o PyCharm Comunnity Crie atravé do Link disponibilizado!<br/>
<a href="https://forum.lksistemas.com.br/criando-o-primeiro-projeto-com-django-atraves-do-pycharm-comunnity/">Criando seu Primeiro projeto pelo PyCharm Community</a></h3>
## Adicione ao interpretador o Django
<img src="https://github.com/lucasrm1981/CRUD_Django/blob/master/CRUD_Django-02.png">

**Comandos:**
### Atualização do pip Python
```pip install --upgrade pip```

### Instalação do Django
```pip install Django```

## Criação do Projeto
```django-admin startproject CRUD_Django```

## Criação da Aplicação
```django-admin startapp cursos```

## Arquivos alterados
**projeto/settings.py**

**cursos/models.py**

**cursos/admin.py**

### Criação do arquivo das tabelas
```python manage.py makemigrations```

### Instalação da Base de Dados e Tabelas
```python manage.py migrate```

## Criação do usuário no Python para acessar o Banco
```python manage.py createsuperuser```

## Rodando o servidor
```python manage.py runserver```

## Custom Fieds Data 
<a href='https://docs.djangoproject.com/en/5.0/ref/forms/fields/'>Custom Fields</a>
