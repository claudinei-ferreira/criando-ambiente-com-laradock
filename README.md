# Criando ambiente de desenvolvimento com Laradock
Confira neste guia como criar um ambiente de desenvolvimento Laravel, utilizando o LaraDock.

## Requisitos necessários:
 <b>Ferramentas</b>
 - [GIT](https://git-scm.com/downloads) 
 - [Docker](https://www.docker.com/products/docker/)
 - [Laradock no GitHub](https://github.com/laradock/laradock)
 - [Documentação do Laradock](http://laradock.io/)
 - [Cmder](https://cmder.net/)
 - [Visual Studio Code](https://code.visualstudio.com/)


## Passo 01: Clonar o Repositório do Laradoc
Clone o repositório do Laradock em qualquer lugar de sua máquina. <br>
Particularmente eu prefiro criar um pasta com a seguinte estrutura:<br> 
 - D:/docker/laradock
 - D:/docker/projects/laravel-app1
 - D:/docker/projects/laravel-app2
 - D:/docker/projects/laravel-app3

```bash
$ cd docker
$ git clone https://github.com/laradock/laradock.git
```

A estrutura de pastas deve ficar parecida com a seguinte:
```bash
- D:/docker
  - laradock
  - projects
       - laravel-app1
       - laravel-app2
       - laravel-app3
       ...
      - demais-projetos
```
## Passo 02: Editar o arquivo de ambiente
Edite o arquivo de configuração de seu ambiente Docker Laradock. Copie o arquivo .env.example para .env
```bash
$ cd laradock
$ cp .env.example .env
```

Abra o arquivo .env e certifique-se de que a variável APP_CODE_PATH_HOST, no início do arquivo, está apontando para o caminho de path anterior:
```bash
APP_CODE_PATH_HOST=../
```

## Passo 03: Subir os containers do Laradock
Com o comando abaixo iremos subir os seguintes containers: nginx mysql e phpmyadmin. <br>
Atenção!  Para rodar este comando você precisa estar dentro da pasta "laradock", aquela que você clonou no inicio deste tutorial. <br>
Obs: Ao subir o nginx ele sobe o container de php junto.
```bash
cd laradock
docker-compose up -d nginx mysql phpmyadmin
```

Ao rodar este comando a primeira vez, pode ser que demore um pouco para baixar todos os pacotes.

Para conferir se todos os container este rodando com sucesso, digite o comando a seguir:
```bash
docker ps
```

## Passo 04: Instalar uma aplicação laravel

Acessar o container workspace. (D:\docker\laradock)
```bash
docker-compose exec workspace bash
```
Ao executar o comando acima você terá uma saída da tela: /var/www#



## Passo 05: Configurar os caminhos dos sites / projetos
As configurações de hosts do projetos criados ficam no diretório a seguir:
D:\docker\laradock\nginx\sites\default.conf <br>

default.conf é responsável por carregar o caminho principal do servidor. <br>
Este arquivo possui uma configurante semelhante a esta:
```bash
server_name localhost; #Nome do nosso host padrão
root /var/www/public; # Caminho do arquivo ou projeto que será carregado no navegador
index index.php index.html index.htm;
```
Para testar este caminho faça o seguinte:
 1) Navegue até a pasta D:/docker, e crie uma pasta "public"
 2) Dentro desta pasta public crie um arquivo index.php
 3) Abra este arquivo no seu editor vs code e adicione o seguinte conteúdo:
 ```bash
 <?php
 phpinfo();
 ```
Agora abra seu navegador e acesse: http://localhost/ <br>
Se tudo estiver correto você verá uma página com as configurações do seu PHP


## Créditos
Para criar este guia usei referências da web e principalmente do site [EspecializaTi](https://academy.especializati.com.br/). <br>
As informações apresentadas neste guia foram consumidas neste [link](https://academy.especializati.com.br/aula/criando-ambiente-com-docker). 


    









