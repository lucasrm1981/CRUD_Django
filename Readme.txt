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
<b>projeto/settings.py</b>
import os ## Importado para funcionamento das alterações
from pathlib import Path ## Importado para funcionamento das alterações

'cursos', ## Rota para o cursos

LANGUAGE_CODE = 'pt-br' # Idioma Pt Br

TIME_ZONE = 'America/Sao_Paulo' # Timezone Brasil


STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles') # Mapeamentos do sistema
MEDIA_URL = 'media/' # Mapeamento de imagens
MEDIA_ROOT = os.path.join(BASE_DIR, 'media') # Mapeamento de midia

**cursos/models.py**
from django.db import models

class Base(models.Model):
    criacao = models.DateTimeField(auto_created=True)
    atualizacao = models.DateTimeField(auto_now=True)
    ativo = models.BooleanField(default=True)

    class Meta:
        abstract = True

class Curso(Base):
    titulo = models.CharField(max_length=255)
    url = models.URLField(unique=True)

    class Meta:
        verbose_name  = 'Curso'
        verbose_name_plural = 'Cursos'

    def __str__(self):
        return self.titulo

class Avaliacao(Base):
    curso = models.ForeignKey(Curso, related_name='avaliacoes', on_delete=models.CASCADE)
    nome = models.CharField(max_length=255)
    email = models.EmailField()
    comentario = models.TextField(blank=True, default='')
    avaliacao = models.DecimalField(max_digits=2, decimal_places=1)

    class Meta:
        verbose_name = 'Avaliação'
        verbose_name_plural = 'Avaliações'
        unique_together = ['email', 'curso']

        def __str__(self):
            return f'{self.nome} avaliou o curso {self.curso} com a nota {self.avaliacao}'


**cursos/admin.py**
from django.contrib import admin

from .models import Curso, Avaliacao

@admin.register(Curso)
class CursoAdmin(admin.ModelAdmin):
    list_display = ('titulo', 'url', 'criacao', 'atualizacao', 'ativo')

@admin.register(Avaliacao)
class AvaliacaoAdmin(admin.ModelAdmin):
    list_display = ('curso', 'nome', 'email','avaliacao', 'criacao', 'atualizacao', 'ativo')

### Criação do arquivo das tabelas
python manage.py makemigrations

### Instalação das bases e Tabelas
python manage.py migrate

## Criação do usuário no Pyhon para o Banco
python manage.py createsuperuser

## Rodando o servidor
python manage.py runserver
