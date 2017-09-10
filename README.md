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


