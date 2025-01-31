Toda vez que criamos um novo container, a gente baixa uma imagem que é feita em diversas camadas (também conhecido como [[Overlay Filesystem]]) e, na hora que o container entra em execução, são criadas duas separações dentro dele:

- A primeira separação chamamos de "camada de imagem", que é imutável. Ou seja, não pode ser alterada, pois faz parte da imagem que foi utilizada para criar o container;
- A segunda separação chamamos de "camada de container", onde temos permissão de leitura e de escrita. No entanto, tudo que escrevemos na camada de container é perdido quando o container é removido.

## Bind-mounts

O bind-mount é, basicamente, mapear uma pasta da maquina host para dentro do container. Isso significa que todas as vezes que algum dado é alterado na pasta mapeada, essa alteração vai ser refletida no container.

O grande ponto negativo do bind-mount é que, como eu estou compartilhando uma pasta que está nativamente no computador host, usando todas as permissões, filesystem e outras configurações do computador host, isso pode resultar em erros e incompatibilidades com o container.

No entanto, o bind-mount se destaca pela baixa latência entre o computador host e o container, facilitando atividades como desenvolvimento de software.

## Volumes

O volume é uma funcionalidade gerenciada pelo Docker. Ou seja, ao criar um novo volume, o Docker cria uma pasta interna que será utilizada para armazenar os dados do container.

O volume tem como finalidade o armazenamento de dados, e por isso deve ser usado principalmente em produção, e em situações em que é essencial armazenar dados, como em um banco de dados, por exemplo.