Os mocks são utilizados principalmente em [[Unit tests|testes de unidade]].

Testes, em geral, são como um jogo: quando você chega até um ponto A, você atinge um checkpoint. Caso você morra por algum motivo, você volta para o último checkpoint alcançado. Nos testes automatizados esse processo é similar e bastante recorrente: você testa a sua função do ponto A para o ponto B. E aí, quando você quer testar a sua função do ponto B para o ponto C, você não precisa testar do ponto A para o ponto B novamente, já que aquele caminho já foi testado. É aí que entram os mocks:

Ao invés de replicar os testes, você cria objetos que partem do principio que o teste A está funcionando, guarda o resultado desse teste em um objeto fixo para que seja possível testar o caminho do ponto B ao ponto C.

---

Imagina que você precisa criar uma função responsável por converter o conteúdo de um arquivo `CSV` em `JSON`. Uma regra de negócio comum nesse tipo de operação é validar o conteúdo, verificando se ele está vazio, se está no formato correto e/ou se possui as propriedades desejadas. Para cada uma das operações podemos criar um mock diferente para testar o comportamento, fazendo com que os testes fiquem desacoplados e sem replicação.