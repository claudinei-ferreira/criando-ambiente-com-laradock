# Criando ambiente de desenvolvimento com Laradock
Confira neste guia como criar um ambiente de desenvolvimento Laravel, utilizando o LaraDock.

## Requisitos necessários:
 - [GIT](https://git-scm.com/downloads) 
 - [Docker](https://www.docker.com/products/docker/)

## Clonar o Repositório do Laradoc
Clone o repositório do Laradock em qualquer lugar de sua máquina – eu aconselho a clonar na pasta onde mantém seus projetos, no mesmo nível deles:

```bash
$ cd my-workspace
$ git clone https://github.com/laradock/laradock.git
```

A estrutura de pastas deve ficar parecida com a seguinte:
```bash
- my-workspace
  - laradock
  - projects
       - projeto-a
       - projeto-b
       ...
      - demais-projetos
```
## Editar o arquivo de ambiente
Edite o arquivo de configuração de seu ambiente Docker Laradock. Copie o arquivo .env.example para .env
```bash
$ cd laradock
$ cp .env.example .env
```

Abra o arquivo .env e certifique-se de que a variável APP_CODE_PATH_HOST, no início do arquivo, está apontando para o caminho de path anterior:
```bash
APP_CODE_PATH_HOST=../
```

Esta configuração define o caminho das suas aplicações na máquina local, isto significa que estão em um nível anterior de pasta em relação à pasta do Laradock. Por isso você deve fazer o clone como explicado no passo 1.

4. Configure o arquivo .env com as demais definições que deseja para esta instalação. Como servidor web a utilizar e extensões do interpretador php-fpm e workspace.

## Configurar os caminhos dos sites / projetos








