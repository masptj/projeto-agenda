Configurar o git

```
git config --global user.name 'Seu nome'
git config --global user.email 'seu_email@gmail.com'
git config --global init.defaultBranch main
# Configure o .gitignore
git init
git add .
git commit -m 'Mensagem'
git remote add origin URL_DO_GIT
```


Iniciar o projeto Django

```
python -m venv venv
. venv/bin/activate
pip install django
django-admin startproject project .
python manage.py startapp contact
```

-Criado o app,  com (python manage.py startapp contact) atualizar INSTALLED_APPS com o nome do app
-Criado duas pastas, base_template e base_static
-Criado dentro de base_template, global e dentro de global, base.html (Será o arquivo que será extendido)
-Criado dentro de base_static, global, css, style.css (Será carregado no base.html com {% Load static %} e demais arquivos estaticos serão carregados com {% static 'global/css/style.css' %} )
-Após criar as pastas é necessário configurar no settings a entrada TEMPLATES -> DIRS
-Após criar as pastas é necessário configurar no settings a entrada após STATIC_URL, STATICFILES_DIRS
-Criar a pasta 'templates' com o name space do app "contact"
-Na pasta Contact criar o index.html com o {% extends "global/base.html" %} para extender o base.html 
-Criar na pasta do app, o arquivo urls.py (pode copiar o urls.py do app, porém sem o admin)
-No arquivo urls.py em contact importar as views da app, criar o namespace e criar a rota vazia "", para o index da app
-No arquivo urls.py do projeto atualizar para incluir (include) as urls e views da app contact, desta maneira a raiz do site será a rais da app 'contact'
-carregar no arquivo base.html primeiro o {% load static %} e depois incluir no caso o style.css em global/css
-Cuidado: nos arquivos views.py informo um caminho com / em urls.py informo o caminho com . como atributos de um objeto

-Fazer a migração das migrations

```
python manage.py makemigrations (não será necessário agora)
python manage.py migrate
```

Criando e modificando a senha de um super usuário Django

```
python manage.py createsuperuser
python manage.py changepassword USERNAME
```

-Criando um model no arquivo model da app
-O id é criado automaticamente

Como foi usado a função timezone, foi alterado em settings o LANGUAGE_CODE e TIME_ZONE para respectivamente pt-br e America/Sao_Paulo

-Como foi criado um model é necessário criar uma migração e fazer a migração

-Criado o model, é necessário registrar no admin

```

```