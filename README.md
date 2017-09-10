# Iniciando com Docker
Meu resumo do Curso Iniciando com Docker da School of Net

# Instalando Docker

Há detalhes e instruções para instalação do docker na página official. No Linux o processo é mais simples, visto que ele foi feito pra rodar no Linux.

# Instalação no Windows.

Caso tenha o Windows 10 Pro, basta habilitar o HyperV e instalar o Docker.msi

Em outras versões, deve-se instalar um aplicativo de máquina virtual (como o virtualbox) e o DockerToolbox.

# Fazendo Hello World e comandos básicos

Imagem é diferente de container!

* docker run <image>: baixa, se não estiver instalada, e executa a imagem
* docker images: lista as imagens
* docker ps: lista os containners ativos
* docker ps -a: lista todos os containers, inclusive que não estão rodando, com os detalhes.
* docker rm <CONTAINER ID>: remove um containner.

# Criando container do Nginx e expondo porta

No docker hub, é possível pesquisar imagens de docker disponíveis.
Nele também é possível publicar uma imagem docker

* docker run <imagem>: baixa e roda a imagem informada
* docker run <imagem> -d: roda a imagem em background
* docker run -d -p porta-host:porta-container <imagem>: informa em qual porta da máquina será correspondente à porta do serviço instalado com o docker.i
* docker-machine ls: mostra configurações do docker
* --name <contanier-name>: parâmetro que atribui um nome a um container, ao invés de permitir que o docker crie um automaticamente.
* docker rm <container> -f: para e deleta o container

# Trabalhando de forma interativa com exec

* docker exec <container> <comando>: executa um comando linux dentro de um container
* docker exec -it <container> bash: executa o container de forma interativa, como se fosse uma conexão ssh, mas não é.

# Compartilhando volumes

É possível substituir pastas que encontram-se dentro do container, por pastas existentes dentro do host.

* docker run -d --name webserver2 -p 8081:80 -v /home/user-host/workspace:/usr/share/nginx/html: Cria um link da pasta html do container webserver2 para a pasta workspace do usuário user-host da host
	* na hora de especificar a pasta do host, pode-se utilizar $(pwd)/workspace:/usr/share/nginx/

# Linkando containers na prática com wordpress

* -e "VARIAVEL_X" -e "VARIAVEL_Y": alguns containers dependem de variáveis de ambiente, e várias variáveis podem ser passadas para um container.
* --link <nome-container>:<nome-aplicacao-no-novo-container> : através do link pode-se linkar containers, informando o nome do container a ser linkado: nome da aplicação no container a ser criado.
	* a partir do nome do servidor linkado (qualquer um dos dois nomes do mesmo servidor) é possível realizar o acesso a aplicação. Por exemplo, se essa aplicação linkada for um banco de dados mysql, basta informar o nome desta aplicação como host, para que a conexão seja estabelecida.

# Trabalhando com dockerfile

O dockerfile é um arquivo que orienta na criação de imagens.

é necessário criar um arquivo Dockerfile (não possui extensão). Nele deve-se definir configurações para o arquivo.

configurações comuns no Dockerfile:

* FROM: indica imagem de origem do dockerfile. Exemplo: `FROM php:7.0-apache`
* MAINTAINER: indica o email do administrador da imagem
* RUN: informa comandos a serem executados aṕós a criação da imagem. Exemplo `RUN apt update && apt install -y vim`
* WORKDIR <diretório>: informa o diretório de trabalho
* ADD <arquivo> <destino>: adiciona um arquivo da máquina local (ou host) para o destino informado no container.
* CMD ["<arquivo>"]: executa scripts existentes no container.

Comandos para se buildar o container
* docker build -t <usuario-docker-hub>/<nome-imagem> <diretorio-dockerfile>: 
* docker build <usuario-docker-hub>/<nome-imagem>:v2 : esse v2 é apenas uma descrição de nova versão, pode ser v1, v3, vX, xpto, charlinho e teresa.
