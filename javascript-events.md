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

    1) Imagine você encontrou um artefato estranho, com um botão. A curiosade bate e você aperta o botão. Olhando ao redor, vê decorações de *Halloween*. Após alguns passos, vê um cartaz promovendo uma festa. Imediatamente, você percebe que a letra está diferente, esquisita e escorrida ~~, como se fosse sangue falso~~, bem no clima do momento. Cada vez que você apertar o botão, viajará no tempo e terá contato com formas diferentes de escrita, que refletem aquele momento da história em que você se encontra.

    Você receberá um documento com dois parágrafos repletos de lorem ipsum, um botão para cada período/alteração do texto, e a estilização já pronta. Sua tarefa é criar eventos de clique que troquem a fonte do texto para as fontes fornecidas logo acima da *tag* ```title```. A escolha de qual fonte será associada a qual botão deixaremos por sua conta, mas testando você vai notar que algumas se encaixam melhores do que as outras. :wink:

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

            button {
                margin-right: 10px;
                padding: 5px;
            }

            p {
                font-size: 20px;
                line-height: 20px;
                text-align: justify;
            }
        </style>
        <link href='https://fonts.googleapis.com/css?family=Butcherman' rel='stylesheet'>
        <link href='https://fonts.googleapis.com/css?family=Give You Glory' rel='stylesheet'>
        <link href='https://fonts.googleapis.com/css?family=Astloch' rel='stylesheet'>
        <link href='https://fonts.googleapis.com/css?family=Caesar Dressing' rel='stylesheet'>
        <link href='https://fonts.googleapis.com/css?family=Ewert' rel='stylesheet'>
        <link href='https://fonts.googleapis.com/css?family=Orbitron' rel='stylesheet'>
        <title>Tipos de escrita por época</title>
    </head>

    <body>
    <h1>Tipos de escrita que você veria viajando no tempo</h1>
    <section>
        <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
        magna aliqua Porttitor lacus luctus accumsan tortor posuere. Turpis cursus in hac habitasse platea dictumst.
        Vulputate enim nulla aliquet porttitor lacus luctus. Amet facilisis magna etiam tempor orci. Et leo duis ut diam.
        Mattis molestie a iaculis at erat pellentesque. Est ultricies integer quis auctor elit sed vulputate mi. Elementum
        sagittis vitae et leo duis ut. Ornare quam viverra orci sagittis eu volutpat odio facilisis mauris. Proin nibh
        nisl condimentum id venenatis a. Sed arcu non odio euismod lacinia. Commodo elit at imperdiet dui. Morbi tristique
        senectus et netus. Amet est placerat in egestas erat. Scelerisque eleifend donec pretium vulputate sapien nec
        sagittis. Dapibus ultrices in iaculis nunc sed. Odio pellentesque diam volutpat commodo sed egestas egestas. Morbi
        tristique senectus et netus. Risus feugiat in ante metus dictum at.
        </p>
        <p>
        Amet dictum sit amet justo donec. Ut consequat semper viverra nam libero justo laoreet sit amet. Purus in massa
        tempor nec feugiat nisl pretium fusce id. Integer enim neque volutpat ac tincidunt vitae semper quis. Nunc sed
        blandit libero volutpat sed. Dui id ornare arcu odio ut sem nulla. Non curabitur gravida arcu ac tortor dignissim
        convallis aenean et. Consequat interdum varius sit amet mattis vulputate enim nulla. A diam sollicitudin tempor id
        eu nisl nunc mi ipsum. Proin sagittis nisl rhoncus mattis. Viverra justo nec ultrices dui sapien. Tortor at risus
        viverra adipiscing at in. Justo eget magna fermentum iaculis eu.
        </p>
    </section>
    <section>
        <button>Halloween</button>
        <button>Velho oeste</button>
        <button>Roma antiga</button>
        <button>Quinta série</button>
        <button>Europa, ano 1423</button>
        <button>Futuro distópico</button>
    </section>

    <script></script>
    </body>

    </html>
    
    Note os links entre as *tags* ```style``` e ```title```. Eles servem para obter fontes especiais que serão necessárias nesta atividade. O que está escrito após "family=" é o **nome** da fonte e é este valor que deve ser utilizado na atividade. Em vez de usar ```elemento.style.fontFamily = 'Arial'```, use 'Butcherman', ok?

    2) Agora você ganhará o poder de, ao escrever o nome de cores em inglês, fazer com que os quadros na sua tela fiquem preenchidos com esta cor.

    Você receberá um documento com quatro ```div```s vazias delimitadas por bordas pretas. Cada uma delas possui logo abaixo de si um campo de ```input``` do tipo ```text``` no qual você deverá digitar os nomes das cores. Feito isto, o ```input``` alterará o valor de ```background-color``` da ```div``` logo acima dele próprio a medida que você for digitando. Teste cores legais como Aquamarine, Maroon e MidnightBlue.
    
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

            section {
                display: flex;
                flex-flow: row;
                justify-content: space-evenly;
            }

            .color-block {
                border: 1px solid black;
                height: 250px;
                width: 250px;
            }

            button,
            div:last-of-type {
                padding: 5px;
            }
        </style>
        <title>Gerador de cores</title>
    </head>

    <body>
        <h1>Este é o gerador de cores!</h1>
        <section>
            <div class="color-block"></div>
            <div class="color-block"></div>
            <div class="color-block"></div>
            <div class="color-block"></div>
        </section>
        <section>
            <div>
            <label for="insert-color-1">Escolha uma cor:</label>
            <input type="text" id="insert-color-1">
            </div>
            <div>
            <label for="insert-color-2">Escolha uma cor:</label>
            <input type="text" id="insert-color-2">
            </div>
            <div>
            <label for="insert-color-3">Escolha uma cor:</label>
            <input type="text" id="insert-color-3">
            </div>
            <div>
            <label for="insert-color-4">Escolha uma cor:</label>
            <input type="text" id="insert-color-4">
            </div>
        </section>
        <script></script>
    </body>

    </html>