Esse arquivo lista alguns dos principais comandos [[Docker & Docker Inc|Docker]] que podem ser usados através da CLI.

---

- `docker run` - cria um novo container que executa a imagem especificada;
	- `docker run {PARAMS} {IMAGE} {COMMAND}`;
	- `--name` - define um nome para o container;
	- `--rm` - deleta automaticamente o container quando ele para de executar;
	- `-d` - executa um container sem prender o terminal;
	- `-p {HOST_PORT}:{CONTAINER_PORT}` - Faz com que seja possível acessar uma porta do container a partir de uma porta do computador host;
	- `-v {CAMINHO_ABSOLUTO_PARA_PASTA_DO_HOST}:{CAMINHO__NO_CONTAINER}` - cria um volume ou bind-mount do host para o container;
	- `--mount type=bind(ou volume),source={CAMINHO_HOST},target={CAMINHO_CONTAINER}` - assim como o `-v`, cria um bind-mount ou volume, só que de forma mais descritiva;

- `docker ps` - mostra os containers em execução;
	- `-a` - mostra todos os containers, independente de estarem em execução ou não;
	- `-q` - mostra apenas os IDs dos containers;

- `docker start {container_id}` - inicia um container que já tenha sido criado anteriormente;
	- `-d` - executa um container sem prender o terminal;

- `docker stop {container_id}` - para um container que está em execução;

- `docker rm {container_id}` - deleta um container que não está em execução;
	- `-f` - força a remoção de um container que está em execução;

- `docker attach {container_id}` - linka o terminal ao container;

- `docker cp {FOLDER} {CONTAINER_NAME}:{CONTAINER_FOLDER}` - copia uma pasta pra dentro de um container;
  
- `docker exec {container_id} {command}` - executa um comando dentro de um container;
	- `-i` - executa o container de forma interativa;
	- `-t` - ativa o TTY, que permite que o meu terminal se comunique com o container;
	- `-it` - é a junção dos comandos `-i` e `-t`, e faz com que seja possível interagir com um container diretamente do terminal;

- `docker volume` - permite gerenciar os volumes que são gerenciados pelo Docker;
	- `create {volume_name}` - cria um volume gerenciado pelo Docker;
	- `ls` - lista os volumes criados;
	-  `prune` - remove todos os volumes;
	- `inspect` - tras um JSON com todos os detalhes do volume;