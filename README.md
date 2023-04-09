# 📦Docker Fundamentals
<hr />

## O que é Docker?

Com o docker, é possível lidar com os contêiners como se fossem máquinas virtuais modulares e extremamente leves. Além disso, os contêiners oferecem maior flexibilidade para você criar, implantar, copiar e migrar um contêiner de um ambiente para outro. Isso otimiza as aplicações em nuvem(privada e pública)

## O que é um contêiner?

Os contêiners são uma tecnologia usada para reunir um aplicativo e todos os seus arquivos necessários em um ambiente de tempo de execução. Como uma unidade, o contêiner pode ser facilmente movido e executado em qualqer sistema operacional, em qualquer contexto.

![Captura de tela de 2023-04-08 02-11-55](https://user-images.githubusercontent.com/83992158/230704878-71359e99-2834-4036-8bfb-83d7bb04bd3f.png)

## Comandos básicos do Docker

_OBS: Como estou utilizando o Linux é necessário digitar **sudo** para executar comandos com privilégios de superusuário._

- `sudo docker version`: Com o version é possível ver a versão do nosso Client
- `sudo docker images`: Lista todas as imagens que estão na máquina
- `sudo docker pull <parametro>`: Baixa a imagem para o host
- `sudo docker ps`: Lista todos os containers em execução
- `sudo docker ps -a`: Com a flag **-a** irá listar todos os contêiners que foram executados
- `sudo docker run <imagem>`: É o comando que inicializa um container, passando o nome da imagem que o container irá utilizar
- `sudo docker stop <id-do-contêiner>`: Para um contêiner através do id
- `sudo docker run -it ubuntu`: Permite que seja executado comandos e interaja com o ambiente Ubuntu dentro do container em tempo real. Pode executar          comandos, instalar pacotes, criar arquivos, etc
- `sudo docker run -dti --name Ubuntu-A ubuntu`: Permite execução e interação em segundo plano, além de criar um "apelido" para a imagem ubuntu chamada:      Ubuntu-A
- `sudo docker exec -it <id-imagem-ubuntu> /bin/bash`: Executa o terminal do ubuntu
- `sudo docker rm <id-do-contêiner>`: Remove um contêiner por id
- `sudo docker rmi <nome-da-imagemr>`: Remove uma imagem 
