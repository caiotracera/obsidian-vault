O Docker é um dos [[Container Runtime|container runtime]] mais utilizados no mercado e no dia-a-dia das empresas. Ele foi criado em 2013 por uma empresa chamada dotCloud, que funcionava como um *PaaS*, para uso interno. A partir do momento que o Docker Engine foi lançado no mercado, houve uma grande adoção da tecnologia por parte de outras empresas. Com a popularidade do Docker, a dotCloud foi renomeada para Docker Inc.

É importante notar que existe uma diferença entre o Docker Engine (ou Docker Community Edition) e o Docker Desktop. O primeiro é o [[Container Runtime|container runtime]] que é *open-source* e capaz de rodar os container. Já o segundo é um outro software vendido pela Docker Inc para auxiliar no desenvolvimento de aplicações.

Para funcionar, o Docker utiliza os recursos do [[Linux]] e outros componentes, como o *runc* e o *containerd*, que são [[Container Runtime|container runtime]] de mais baixo nível para fazer o gerenciamento dos containers. Ou seja, o Docker é um [[Container Runtime|container runtime]], mas é um [[Container Runtime|container runtime]] de mais alto nível. A grande sacada da Docker Inc durante a criação do Docker foi aproveitar tudo que já existe relacionado ao mundo de containers e recursos do [[Linux]] e criar uma ferramenta de alto nível que qualquer pessoa consiga utilizar de forma fácil.

- Ferramenta completa: gerenciamento de containers, rede e disco, além da criação e build de images;
- Trabalha no formato cliente-servidor:
	- Daemon (também chamado de *[[dockerd]]*) responsável por fazer o gerenciamento de todos os containers;
	- Client responsável por fazer chamadas para o daemon;
	- Daemon acaba se tornando um ponto único de falha;
	- Root vs rootless:
		- Para que o daemon seja executado, por padrão, é preciso ter permissão de super usuário (sudo ou root), tornando-o menos seguro;
		- No entanto, é possível fazer uma configuração para que o Docker execute como um usuário local da máquina, sem permissões de root;