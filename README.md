# ionic-sqlite
Criando uma app Android com IONIC acessando banco de dados via SQLITE (ngCordova)

## Pré requisitos (Ambiente)
Ter instalado e configurado as variaveis de ambiente: 
(postarei aqui depois como montar o ambiente)
* nodejs
* ionic
* android-sdk (API Level 19)
* cordova
* Ter um dispositivo android ou AVD emulador configurado

Considerando que tudo esta configurado, seguiremos com o tutorial

## Criando o projeto básico
-PS: todos os comandos devem ser executados no prompt de comando

Crie um projeto ionic vazio

    ionic start ionic-sqlite blank
    cd ionic-sqlite
  
Incluir a plataforma Android ao projeto

    ionic platform add android

Caso esteja rodando em um Mac, pode incluir a plataforma ios tambem (não abordaremos essa plataforma)

    ionic platform add ios
  
Incluir o plugin de acesso a banco de dados SQLite

    cordova plugin add https://github.com/brodysoft/Cordova-SQLitePlugin.git

## Customizando o projeto
Ate aqui seu projeto esta criado, vamos agora configurar o acesso ao banco de dados usando AngularJS, edite os seguintes arquivos de acordo com o fonte deste repositorio:
* app.js (criamos aqui o controller, database, create table, insert e select
* index.html (aqui criamos a chamada do controller e incluimos os botoes de inserir e selecionar)

## Deploy do app Android
Vamos gerar o .apk correspondente ao aplicativo

    ionic build android
  
## Instalar no device/smartphone android
Temos que testar nosso app no nosso celular, basta pluga-lo no usb e ativar o modo de depuração e executar o seguinte comando para instalar no aparelho:

    adb install -r platforms/android/ant-build/CordovaApp-debug.apk
  
(OPCIONAL) Caso queira monitorar as atividades do celular, inclusive todos os logs que incluimos no Console (codigo do app.j controllers), basta ativar o logcat pelo comando:

    adb logcat

### Pronto, criamos uma aplicação com acesso a banco de dados do zero usando o ionic e fizemos o deploy para o celular android!
Quem quiser dar um fork no projeto e melhorar ele, criando novas funcionalidades, como delete ou update, etc.. fiquem a vontade, vamos deixar esse exemplo o mais completo possivel!

Duvidas podem enviar email para contato@charlesmendes.com

## Créditos
Esse código foi elaborado com base no tutorial do Nic Raboy:
https://blog.nraboy.com/2014/11/use-sqlite-instead-local-storage-ionic-framework/

##License
MIT, see LICENSE.
