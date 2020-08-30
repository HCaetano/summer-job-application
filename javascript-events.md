# JavaScript - Eventos

## O que vamos aprender?

    Antes de começarmos a estudar **JavaScript**, as nossas páginas já estavam ficando bem bonitas, mas ainda eram um pouco **paradas**, não é mesmo? Desde então, você começou a estudar JavaScript, aprendeu a usar ```for``` e ```if```, entre outras coisas. Para quê, você pode se perguntar. Esses conhecimentos são necessários para serem utilizados em conjunto com **eventos**, a fim de criar páginas ~~que fazem coisas!~~ dinâmicas.

    Nada tema! Chegou a hora! Hoje você vai aprender a criar ~~ações~~ eventos para que as suas páginas tornem-se não só bonitas como também interativas.

## Você será capaz de:

    - Modificar, de forma ~~interativa~~ dinâmica, aspectos da sua página (fonte, cores, propriedades de elementos);
    - Utilizar elementos **JavaScript** como ```click```, ```*mouse*over```, ```*mouse*out``` e ```input```;
    - Compreender o que é e utilizar o parâmetro ```target```.

## Por que isso é importante?

    Quer fazer um experimento de viagem no tempo? Pense em uma internet em que as páginas são estáticas, somente apresentam conteúdo. Sem botões, sem efeitos quando você põe o *mouse* sobre algo, ~~sem pop-ups que disparam quando você vai fechar a aba~~ sem interatividade! Imagine uma *web* sem botões! :flushed: Este deixou de ser o padrão das páginas da *web* há tanto tempo que talvez você nem lembre mais ou nunca a tenha visto desta forma. :joy:

    JavaScript é um dos pilares das páginas modernas e hoje você está dando um passo importante na obtenção deste superpoder! :muscle: Além disso, a linguagem é o motor dos navegadores. **Eventos** integram o conjunto de ferramentas que JS nos oferece. O conteúdo de hoje é responsável por controlar muitas das ações que fazemos em uma página, como clique simples, duplo clique, pressionar teclas do teclado, passar o *mouse* em cima de algo, entre outros. A lista de eventos é vasta, mas não se preocupe, pois hoje veremos alguns dos mais importantes. :wink:

## Conteúdos

    A seguir, aprenderemos a funcionalidade responsável por monitorar eventos a fim de garantir que eles disparem no momento certo, e não só conheceremos alguns, como também faremos nosso primeiro evento.

### Monitor de eventos

    Como já sabemos, eventos são responsáveis pela interação das pessoas usuárias com as nossas páginas, porém o que não sabemos é como o navegador sabe o que fazer quando clicamos em um botão, por exemplo. Pois saberemos agora! O reconhecimento que um evento foi acionado ou **disparado** (*triggered*, em inglês) acontece porque a pessoa desenvolvedora, ao criar um evento, o **associa** ao elemento HTML **alvo** daquela ação (voltaremos a essas duas palavras depois da aula). A partir de então, o navegador passa a **monitorar** aquele elemento no aguardo da ação indicada acontecer.

    Vamos dar um passo para trás e pensar em uma analogia: o controle remoto de uma TV. Ele é um instrumento muito versátil, capaz de realizar diversas ações, seja aumentar ou diminuir o volume, trocar de canal, ~~abrir a Netflix~~ e, é claro, ligar e desligar a TV. Porém, se deixado parado em cima do sofá, não faz nada sozinho. Ele precisa do componente mais importante: a pessoa usuária. É ela quem aciona os eventos programados no controle ao clicar nos diversos botões que o controle possui. Ele é construído de forma a monitorar constantemente se o usuário pressionou seus botões. A seguir, veremos como é o dia a dia de um controle remoto.

    > Estou aqui só no aguardo. Até agora nada de clique. Queria tanto um clique! :pensive:

    Assim que isso acontece, ele percebe.

     > Um clique! Ótimo! :grin: Vejamos qual foi o botão.

    Então ele verifica qual foi o botão clicado, qual a ação que este botão deve realizar, e a executa.

    > Hmmm, este botão remove todo o volume da TV. Então toma aí um silêncio!

    Após identificar que ação deve tomar, o controle a executa assim que puder.

    > Pronto, a TV tá silenciada. Terminei meu trabalho. :relieved: Agora é só esperar o próximo clique.

    Concluída a sua tarefa, o controle passa a monitorar novamente os botões, para garantir que estará pronto quando a pessoa usuária decidir apertar algum botão novamente.

    Em termos técnicos, este monitor é uma função do JavaScript chamada ```addEventListener```. Ela é chamada por um elemento HTML e recebe dois parâmetors: 1) qual será ~~a ação~~ o evento que causará o disparo e 2) o que será feito quando acontecer o disparo.

    Veremos ela em ação a seguir. Crie um documento HTML simples e substitua o elemento ```body``` por este aqui:

        <body>
            <button>Clique aqui!</button>

            <script>
                const button = document.querySelector('button');

                function acaoDisparadaPeloClique() {
                    alert('Botão clicado!');
                }

                button.addEventListener('click', acaoDisparadaPeloClique);
            </script>
        </body>

    Note que a ação causada pelo evento é também uma função, neste caso chamada ```acaoDisparadaPeloClique```. No entanto, como ela existe única e exclusivamente para ser chamada por este botão sendo clicado, ela não precisa existir em sua forma atual, declarada com nome próprio e isolada do eventListener. Sendo assim, é mais comum que a função disparada pelo evento, quando não for ser reaproveitada em outras partes do código, seja declarada de forma anônima no interior do eventListener. A seguir, veremos como isso pode ser feito: 

        button.addEventListener('click', function () {
            alert('Botão clicado!');
        });

    Você acabou de ver o seu primeiro evento em ação! Você pode ter achado simples, mas toda jornada tem um começo. :wink:

### Eventos

    Pare e pense em uma definição para eventos. Pode ser um bom exercício para ajudar a consolidar o entendimento sobre este conteúdo. Quem sabe você pode trocar uma ideia com outros colegas sobre o que vocês entenderam a respeito?

    Levando em consideração o que vimos até aqui, podemos entender que eventos são ações resultantes de interações da pessoa usuária com a nossa página. Sua gestão é realizada pela função ```addEventListener```, quando corretamente associada a um elemento HTML. Eventos possuem nomes que descrevem como serão disparados, tais como ```click``` e ```mouseover``` e necessitam de uma função para especificar o seu comportamento.

    Parece confuso? Não se preocupe, vamos praticar agora para você chegar com tudo na aula ao vivo! :heart_eyes:

    Aproveite aquele mesmo arquivo HTML que você acabou de criar para os exercícios a seguir. 

    1) Faça com que, em vez de criar um alert, a função do exemplo agora mostre a mensagem no console do navegador ~~pois hoje em dia ninguém mais aguenta pop-ups~~.

    2) Troque a fonte de um texto para outra de sua preferência ao clicar no botão. Use o código a seguir como um ponto de partida.

        <body>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos similique, nam maiores dolores aspernatur nostrum aliquid deleniti sapiente ipsa placeat itaque laboriosam ut dolorum, quisquam ratione dolorem accusantium dignissimos.</p>
            <button>Clique aqui!</button>
            <script>
                const button = document.querySelector('button');
                const paragraph = document.querySelector('p');

                // seu evento aqui!
            </script>
        </body>

    3) Mas não só de cliques vivem as pessoas desenvolvedoras. Remova o código relacionado ao botão e agora faça com que a fonte do texto seja trocada ao passar o *mouse* em cima do mesmo. Dica: o evento chama-se ```mouseover```.
    
    4) Agora faça com que, em vez de trocar a fonte, a cor do texto seja trocada ao passar o *mouse* em cima do mesmo. 

    5) Vamos chegar na aula ao vivo voando :rocket:: crie um elemento ```input``` do tipo ```text``` e, ao digitar nele, faça com que o texto digitado apareça no console do navegador. Dica: o evento chama-se ```input```.

### Vamos fazer juntos!

    Depois de ~~termos a ajuda do nosso amigo controle remoto~~ termos estudado e praticado o conteúdo, vamos mandar bem demais na aula ao vivo!

    Aguarde a facilitação enviar o link para a aula no Slack e vamos decolar juntos!

### Exercícios

    E aí, entendeu muito mais agora, não é mesmo? :smiley:

    Para ficarmos ainda melhores no conteúdo, que tal praticarmos um pouco mais? Você vai ter a oportunidade de: viajar no tempo, pintar partes da sua tela somente com o poder da palavra, interagir com um gato fofo :smiley_cat: e reparar o casco de um navio. Para isso, só precisaremos de duas coisas: imaginação e o seu novo superpoder: **eventos em JavaScript**.

    Para os exercícios a seguir, utilize este documento HTML como ponto de partida. Cuide o conteúdo da tag ```style```, pois modificá-la pode fazer com que a estrutura fornecida pare de funcionar. 

    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>
            body {
            margin: auto;
            width: 80%;
            }

            h1,
            section {
            text-align: center;
            margin: 25px;
            padding: 10px;
            }
        </style>
    </head>

    <body>
        <script>
        </script>
    </body>

    </html>

