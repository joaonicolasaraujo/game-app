# game-app

O projeto é um aplicativo mobile para a plataforma Android que tem como objetivo exibir uma lista de jogos, imagens do jogo e suas notas no Metacritic que é uma plataforma de avaliação e crítica de jogos eletrônicos.
Como o projeto está organizado e seu funcionamento:
O projeto utiliza arquiteturas modernas e boas práticas de software, primeiramente, podemos mencionar a utilização da arquitetura MVVM em conjunto com Clean, a utilização base do MVVM se dá pela separação clara de responsabilidades entre o modelo “Model”, onde ficam todas as entidades, objetos de transferência de dados, fonte de dados local e remota; a visão “View” que é onde todos os componentes da nossa interface e lógica de exibição da mesma ficam localizados, não deve saber de nenhum detalhe de implementação e lógica de negócio, sendo unicamente responsável por operações de interface do usuário, delegando uma tarefa adicional para o meio de campo que é a visão-modelo “ViewModel”, essa camada trabalha em conjunto com o repositório que faz a ponte entre ela e o modelo, sendo sua principal atribuição prover dados para a “view”.
A adição de Clean ao ModelViewViewModel serve justamente para melhorar a reusabilidade de código, inibir sua duplicação, melhorar a testabilidade do programa ou aplicativo, promover um alto desacoplamento entre todos os seus componentes, facilitar a adição de novas funcionalidades e melhorar o entendimento da estrutura de pacotes e sua legibilidade, tudo isso é alcançado graças a adição de uma camada adicional entre o repositório e o ViewModel, sendo essa camada adicional a de domínio onde ficará os casos de uso que serão executados no ViewModel e “definições” de repositórios, ou seja, suas interfaces para implementação na camada de modelo. Podemos separar a aplicação agora entre 3 principais pacotes: model, domain, presentation.

Principais tecnologias e dependências utilizadas no projeto:
* ViewModel: A classe ViewModel foi projetada para armazenar e gerenciar dados relacionados à IU considerando o ciclo de vida. A classe ViewModel permite que os dados sobrevivam às mudanças de configuração, como a rotação da tela.
* LiveData: LiveData é uma classe armazenadora de dados observável. Diferente de um observável comum, o LiveData conta com reconhecimento de ciclo de vida, ou seja, ele respeita o ciclo de vida de outros componentes do app, como atividades, fragmentos ou serviços. Esse reconhecimento garante que o LiveData atualize apenas os observadores de componente do app que estão em um estado ativo no ciclo de vida.
* Room: A biblioteca de persistência Room oferece uma camada de abstração sobre o SQLite para permitir um acesso mais robusto ao banco de dados, aproveitando toda a capacidade do SQLite. 
* Retrofit: Retrofit é a classe por meio da qual suas interfaces de API são transformadas em objetos que podem ser chamados. Por padrão, o Retrofit fornecerá padrões lógicos para sua plataforma, mas permite a personalização.
* Coroutines: Coroutines são um padrão de projeto de simultaneidade que você pode usar no Android para simplificar o código que é executado de forma assíncrona.
* Dagger: Dagger é uma estrutura de injeção de dependência de tempo de compilação totalmente estática para Java, Kotlin e Android. É uma adaptação de uma versão anterior criada pela Square e agora mantida pelo Google.
* Data Binding: Data Binding Library é uma biblioteca de apoio que permite vincular componentes de IU dos seus layouts a fontes de dados do app usando um formato declarativo, em vez de programático.
* Glide: Glide é uma biblioteca de carregamento de imagens rápida e eficiente para Android focada em rolagem suave. O Glide oferece uma API fácil de usar, um pipeline de decodificação de recursos extensível e de alto desempenho e pool automático de recursos.