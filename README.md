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
- `sudo docker inspect <nome-do-conteiner>`: Trazer de forma detalhada as informações do contêiner
- `sudo docker stop <id-do-contêiner>`: Para um contêiner através do id
- `sudo docker start <apelido-ou-id-do-conteiner-parado>`: Para retomar a execução`
- `sudo docker run -it ubuntu`: Permite que seja executado comandos e interaja com o ambiente Ubuntu dentro do container em tempo real. Pode executar          comandos, instalar pacotes, criar arquivos, etc
- `sudo docker run -dti --name Ubuntu-A ubuntu`: Permite execução e interação em segundo plano, além de criar um "apelido" para a imagem ubuntu chamada:      Ubuntu-A
- `sudo docker exec -it <id-imagem-ubuntu> /bin/bash`: Executa o terminal do ubuntu
- `sudo docker rm <id-do-contêiner>`: Remove um contêiner por id
- `sudo docker rmi <nome-da-imagemr>`: Remove uma imagem 

##  👨‍🔧Mão Na Massa

> Objetivo: Criar um contêiner com o MySQL

1. Como já existe uma imagem do MySQL vamos baixa-la:
```
docker pull mysql`
```

2. Acionar o _Help_ do _run_ para visualizar os comandos para realizar as configurações do banco(liberar a porta e setar as variáveis de ambiente)
```
docker run --help
```
![Captura de tela de 2023-04-09 10-11-06](https://user-images.githubusercontent.com/83992158/230774657-be1f3687-a091-48b8-a0bb-5fffaa65d7c0.png)

![Captura de tela de 2023-04-09 10-12-10](https://user-images.githubusercontent.com/83992158/230774671-7a3b9d1c-37b1-44fa-9c55-19dbb66204a4.png)


3. Setar as variáveis de ambiente e configurar a porta(porta padrão):
```
docker run -e MYSQL_ROOT_PASSWORD=root --name mysql-conteiner -d -p 3306:3306 mysql
```

4. Executar o bash do contêiner do Mysql e acessar o banco de dados:
```
docker exec -it mysql-conteiner bash
```
![Captura de tela de 2023-04-09 10-40-01](https://user-images.githubusercontent.com/83992158/230776070-1be5b6f5-fbb5-48da-ac6e-ef08015fddde.png)


5. Criar um database no conteiner e conectar-se externamente:

- Criando um database no conteiner
> ![Captura de tela de 2023-04-09 11-27-24](https://user-images.githubusercontent.com/83992158/230778539-82ec19eb-a28c-4c1b-9c93-bebb8e30f2c5.png)

- Conectando ao banco criando no conteiner
> ![Captura de tela de 2023-04-09 11-31-35](https://user-images.githubusercontent.com/83992158/230779007-ed0b7fdf-bc4f-4d76-9f8e-c1fc729708b3.png)

- Executando algumas queries para testar a conexao com o conteiner
> ![Captura de tela de 2023-04-09 11-40-15](https://user-images.githubusercontent.com/83992158/230779273-a006fda2-8d37-4e73-a33e-7b29e2b67717.png)

- Insert feito com sucesso
> ![Captura de tela de 2023-04-09 11-40-48](https://user-images.githubusercontent.com/83992158/230779298-23b50d3c-c12e-47fd-8d5e-fd4f0c5baf3d.png)
