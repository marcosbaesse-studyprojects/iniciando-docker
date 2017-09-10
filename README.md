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

# Trabalhando de forma interativa com exec

* docker exec <container> <comando>: executa um comando linux dentro de um container
* docker exec -it <container> bash: executa o container de forma interativa, como se fosse uma conexão ssh, mas não é.




