Imagine que precisamos testar uma integração que cobra por uso. Ou seja, toda vez que o teste é executado e batemos nessa integração ocorre uma cobrança. Para resolver esse problema podemos usar os stubs.

Os stubs são utilizados para substituir algum comportamento do sistema por objetos estáticos, onde podemos criar diferentes [[Mocks|mocks]] para cada serviço específico. Dessa forma nossos testes não ficam dependentes dessa integração estar de pé e funcionando.

> Os [[Unit tests|testes unitários]] não devem dependentes de outros testes e nem de serviços externos.

