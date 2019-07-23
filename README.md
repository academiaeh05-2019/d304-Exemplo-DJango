# Exemplo DJango #

## Como criar um ambiente para o DJango ##
 1. Crie uma pasta para o DJango
 2. Dentro da pasta, crie um ambiente com o comando ```python -m venv <pasta_do_ambiente>```
 3. Ative o ambiente usando ```. <pasta_do_ambiente>/bin/activate```, se você estiver no windows use ```.\<pasta_do_ambiente>\Scripts\activate```

## Como instalar DJango no seu ambiente ##
 DJango pode ser instalado em qualquer ambiente python usando ```pip install django```

## Como usar o DJango ##

### 1- Crie um projeto DJango ###
 Uma vez dentro do ambiente DJango, ele desponibiliza um comando chamado ```django-admin``` use esse comando para criar um projeto DJango dessa forma: ```django-admin startproject <nome_do_projeto>```

### 2- Crie um App dentro do DJango ###
 O Django trabalha com estrutura de aplicações dentro de um projeto, ou seja, cada funcionalidade ou contexto do nosso projeto, deve ser separado em um App aparte. 

 DJango também adiciona um arquivo chamado manage.py, ele é o reponsável por gerenciar tudo que acontece com seu projeto. No linux ele é usado da seguinte forma ```./manage.py```, já no windows, precimos especificar que o arquivo vai ser rodado com o python, por isso usamos ```python manage.py```

 Para criar um app use ```./manage.py startapp <nome_do_aplicativo>```

### 3- Crie uma view para seu app ###
 DJango usa a arquitetura MTV, ou seja, Model, Template e View. Então tudo referente a Objetos fica em Model, tudo refente a HTML, fica na pasta templates, e o que é relacionado a regra de negócio fica na View.
 
 Adicione seu HTML a pasta templates do seu app, e então no seu arquivo de views, crie uma função que receba um parametro ```request``` e retorne o render do seu html que você adicionou (um exemplo dessa função pode ser encontrado dentro do app home dentro desse mesmo repositório)

 Agora, cadastre seu app dentro do DJango, para isso acesse o arquivo settings.py e dentro da sua chamada ```INSTALLED_APPS``` coloque o nome do seu app.

 Por último, só falta falarmos para o DJango qual é a URL que deve chamar nossa função dentro de view, para isso vá no arquivo ```urls.py``` do DJango e adicione um Path para sua view. (Obs: não esqueça de importar sua função antes de usar. Caso haja dúvidas em como fazer, um exemplo disso pode ser encontrado no app deste mesmo repositório)

### 4- Pronto ###
Agora basta rodar seu servidor e você verá sua página HTML sendo exibida na url que você configurou :)
Para rodar seu servídor DJango use o comando ```./manage.py runserver```, e para parar, basta apertar Ctrl + C

## Extra ##

### Como colocar CSS, JS e imagens do projeto? ###
Já que sabemos que somente o html pode ficar dentro de templates, surge uma dúvida, onde devemos colocar nossos outros arquivos do site?
Resposta: Para isso devemos colocar nossos arquivos dentro de uma pasta chamada ```static``` que deve ser criada dentro do seu app. Ela será responsável por guardar esses tipos de arquivos.

E como usamos esses arquivos no HTML?
Para usar um arquivo estatico dentro do HTML, você precisa fazer duas coisas sendo elas:
 1. No começo do HTML escreva ```{% load static %}``` - Isso informa para o DJango que esse arquivo usará arquivos estaticos,
 2. Onde você precisar colocar o caminho do seu arquivo, coloque no lugar ```{% static "<nome_do_arquivo>"%}``` - Isso indica para o DJango que ali ele deve substituir esse texto pelo caminho real do arquivo. Obs: se o arquivo estiver dentro de uma pasta em static, coloque também a pasta junto com o nome do arquivo Ex: ```{% static "<pasta>/<nome_do_arquivo>"%}```

 ## Exercícios ##
Agora que você já está apto a utilizar o DJango, Realize os exercícios contidos dentro do arquivo ```Exercicios.html```.
Não esqueça da diferença entre arquivos de template e arquivos que vão para o static como vimos em aula! :)
