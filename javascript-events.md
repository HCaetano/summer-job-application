# JavaScript - Eventos

## O que vamos aprender?

Antes de começarmos a estudar **JavaScript**, as nossas páginas já estavam ficando bem bonitas, mas ainda eram um pouco **paradas**, não é mesmo? Desde então, você começou a estudar JavaScript, aprendeu a usar ```for``` e ```if```, entre outras coisas. Com qual objetivo, você pode se perguntar. Esses conhecimentos são necessários para serem utilizados em conjunto com **eventos**, a fim de criar páginas ~~que fazem coisas!~~ dinâmicas.

Nada tema! Chegou a hora! Hoje você vai aprender a criar ~~ações~~ eventos para que as suas páginas tornem-se não só bonitas como também interativas.

## Você será capaz de:

- Modificar, de forma ~~interativa~~ dinâmica, aspectos da sua página (fonte, cores, propriedades de elementos);
- Utilizar elementos **JavaScript** como ```click```, ```mouseover```, ```mouseout``` e ```input```;
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

Seu primeiro evento! Que legal, não é mesmo? :sunglasses:

Note que a ação causada pelo evento é também uma função, neste caso chamada ```acaoDisparadaPeloClique```. No entanto, como ela existe única e exclusivamente para ser chamada por este botão sendo clicado, ela não precisa existir em sua forma atual, declarada com nome próprio e isolada do eventListener. Sendo assim, é mais comum que a função disparada pelo evento, quando não for ser reaproveitada em outras partes do código, seja declarada de forma anônima no interior do eventListener. A seguir, veremos como isso pode ser feito: 

```
button.addEventListener('click', function () {
    alert('Botão clicado!');
});
```

Você acabou de ver o seu primeiro evento em ação! Você pode ter achado simples, mas toda jornada tem um começo. :wink:

### Eventos

Pare e pense em uma definição para eventos. Pode ser um bom exercício para ajudar a consolidar o entendimento sobre este conteúdo. Quem sabe você pode trocar uma ideia com outros colegas sobre o que vocês entenderam a respeito?

Levando em consideração o que vimos até aqui, podemos entender que eventos são ações resultantes de interações da pessoa usuária com a nossa página. Sua gestão é realizada pela função ```addEventListener```, quando corretamente associada a um elemento HTML. Eventos possuem nomes que descrevem como serão disparados, tais como ```click``` e ```mouseover``` e necessitam de uma função para especificar o seu comportamento.

Parece confuso? Não se preocupe, vamos praticar agora para você chegar com tudo na aula ao vivo! :heart_eyes:

Aproveite aquele mesmo arquivo HTML que você acabou de criar para os exercícios a seguir. 

1) Faça com que, em vez de criar um ```alert```, a função do exemplo agora mostre a mensagem no console do navegador ~~pois hoje em dia ninguém mais aguenta pop-ups~~.

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

Instruções: Você receberá um documento com dois parágrafos repletos de lorem ipsum, um botão para cada período/alteração do texto, e a estilização já pronta. Sua tarefa é criar eventos de clique que troquem a fonte do texto para as fontes fornecidas logo acima da *tag* ```title```. A escolha de qual fonte será associada a qual botão deixaremos por sua conta, mas você vai notar que algumas se encaixam melhores do que as outras. :wink:

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

Instruções: Você receberá um documento com quatro ```div```s vazias delimitadas por bordas pretas. Cada uma delas possui logo abaixo de si um campo de ```input``` do tipo ```text``` no qual você deverá digitar os nomes das cores. Feito isto, o ```input``` alterará o valor de ```background-color``` da ```div``` logo acima dele próprio a medida que você for digitando. Teste cores legais como Aquamarine, Maroon e MidnightBlue.

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

3) Você acolheu um gato fofinho que parecia não ter lar. Depois de muito carinho, percebeu que ele estava sentado lhe dirigindo o olhar. Em seguida, ele começa a falar! Não só isso, ele também lhe fez alguns pedidos!

Instruções: Você receberá um documento com uma imagem inicial do gato misterioso em uma ```section```. Ao lado desta, há outra ```section```, que contém três sentenças proferidas pelo gato apresentadas em elementos ```p```. Ao passar o *mouse* sobre estas sentenças, o atributo ```source``` da imagem inicial deve ser alterada para uma das outras três imagens do gato disponibilizadas. A nova imagem só deve permanecer visível enquanto o *mouse* estiver sobre o elemento que contém a sentença. Ao retirar o *mouse* de cima da sentença, a imagem inicial do gato sentado deve ser restaurada. Dica: use 'mouseover'.

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: auto;
      width: 90%;
    }

    h1,
    section {
      margin: 25px;
      padding: 10px;
      text-align: center;
    }

    section {
      display: flex;
      flex-direction: row;
      height: 600px;
    }

    div,
    img {
      height: 100%;
    }

    img {
      max-width: 100%;
    }

    div:first-of-type {
      width: 60%;
    }

    div:last-of-type {
      align-items: center;
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      width: 40%;
    }

    p {
      align-items: center;
      background-image: linear-gradient(to right, #a1c4fd, #c2e9fb);
      border-radius: 10%;
      display: flex;
      font-size: 20px;
      height: 100px;
      justify-content: center;
      width: 75%;
    }
  </style>
  <title>Gato fofo</title>
</head>

<body>
  <h1>Interaja comigo, pessoa!</h1>
  <section>
    <div>
      <!-- Accreding the author: <a href="http://www.freepik.com">Designed by Freepik</a> -->
      <img src="https://i.ibb.co/HHYrw6D/cats-02.jpg" alt="Cute cat in different positions">
    </div>
    <div>
      <h2>Minhas falas</h2>
      <p>"Vem brincar comigo!"</p>
      <p>"Tô de olho em você, hein?"</p>
      <p>"Joga o meu ratinho de pelúcia, pessoa!"</p>
    </div>
  </section>
  <script></script>
</body>

</html>

A seguir, encontra-se uma lista com as outras três imagens do gato misterioso.

<img src="https://i.ibb.co/Bz9fspD/cats-01.jpg" alt="Cute cat in different positions">
<img src="https://i.ibb.co/y5wdwpf/cats-03.jpg" alt="Cute cat in different positions">
<img src="https://i.ibb.co/4gGnp3r/cats-04.jpg" alt="Cute cat in different positions">

4) Chegou a hora das férias. Você trabalhou duro no seu primeiro ano como pessoa desenvolvedora e fez por merecer um belo descanso. Você viu online que está na moda passear de barco pelo Caribe e decidiu experimentar. Pesquisou bastante online e encontrou um lindo barquinho por um bom preço e começou a contar os dias para sair por aí desbravando os mares cristalinos da América Central. Chegando lá, no entanto, que azar! O navio tem três furos enormes em seu casco. No atracadouro onde se encontra o se navio, você encontrou uma caixa chamativa. Nela, encontrou três curativos e um bilhete: "Eles são mágicos! Tapam qualquer buraco". Meio rindo, mas meio no desespero, você decide colar os adesivos no navio e magicamente os buracos foram tapados!

Instruções: Você receberá um documento com a imagem de um navio que, por sua vez, possui sobreposto a si três imagens de furos em seu casco. O navio é a imagem de fundo de uma ```section``` e os curativos ficam em outra ```section```. Exceto pelo navio, as imagens são todas elementos ```img``` com um atributo ```source```. Ao clicar em um curativo, a página deve "lembrar" dele, de forma que se a pessoa usuária clicar em cima de um ou mais buracos, estes tenham sua imagem substituída pela imagem do curativo clicado. 

Dicas: 
    - Note que ```holes``` e ```bandages``` são **classes**, use isto a seu favor na hora de selecioná-los; :wink
    - Quem sabe você possa guardar o ```src``` da imagem da bandagem clicada em uma variável ~~selectedBandage~~? Aí, ao clicar em um dos elementos ```hole``` você possa trocar o conteúdo do ```src``` dele pelo que está contido na variável ~~selectedBandage~~.

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: auto;
      width: 90%;
    }

    h1,
    section {
      margin: 25px;
      padding: 10px;
    }

    h1 {
      text-align: center;
    }

    section {
      display: flex;
      justify-content: space-around;
    }

    section:first-of-type {
      background-position: center;
      background-repeat: no-repeat;
      background-size: contain;
      background-image: url(https://i.ibb.co/BcV5VZQ/ship.jpg);
      align-items: flex-end;
      height: 500px;
    }

    section:last-of-type {
      height: 60px;
    }

    .hole {
      border-radius: 50%;
      height: 50px;
      width: 50px;
      margin-bottom: 40px;
    }

    img {
      width: 60px;
    }
  </style>
  <title>Conserte os buracos do navio</title>
</head>

<body>
  <h1>Escolha um curativo e tape os buracos!</h1>
  <section>
    <img class="hole" src="https://i.ibb.co/LYFgssT/hole.png" alt="Hole in ship's hull">
    <img class="hole" src="https://i.ibb.co/LYFgssT/hole.png" alt="Hole in ship's hull">
    <img class="hole" src="https://i.ibb.co/LYFgssT/hole.png" alt="Hole in ship's hull">
  </section>
  <section class="bandages">
    <img src="https://i.ibb.co/2hvX3z8/green-bandage.png" alt="Green bandage">
    <img src="https://i.ibb.co/0F6k8FJ/red-bandage.png" alt="Red bandage">
    <img src="https://i.ibb.co/3RqMP1W/violet-bandage.png" alt="Violet bandage">
  </section>
  <script></script>
</body>
    <!-- Accrediting the author:
    <a href="https://www.vecteezy.com/free-vector/ship-vector">Ship Vector Vectors by Vecteezy</a>
    <a href="https://www.vecteezy.com/free-vector/band">Band Vectors by Vecteezy</a> -->
</html>

### Bônus

Você sabe o que é um relógio solar? Em tempos passados, antes da invenção de relógios mecânicos, media-se a passagem do tempo durante o dia com a posição do Sol no céu :sunny:. A medida que o Sol cruza o céu, seu ângulo muda a sombra produzida por ele. O relógio solar possui um objeto em seu centro, podendo ser uma vareta ou uma lâmina triangular, e pode-se medir a hora aproximada pela sombra deste objeto, que fica em cima de um dos 12 números que indicam as horas. Para ficar mais claro, veja uma imagem:

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/Melbourne_sundial_at_Flagstaff_Gardens.JPG/1280px-Melbourne_sundial_at_Flagstaff_Gardens.JPG" alt="Relógio solar" width="631" height="400"/>

Faremos algo inspirado em um relógio solar. Imagine que você ficou sabendo da existência deste curioso objeto e, na sua segunda oportunidade de férias, decidiu não arriscar com barcos e foi para a Austrália conhecer um autêntico relógio deste tipo. Chegando lá, visitou o objeto quatro vezes, a fim de ver a projeção da sombra no relógio: ao nascer do Sol, às 6 da manhã; ao meio-dia; ao por do Sol, às 6 da tarde; e à meia-noite. Pôde notar que a sombra projetada pela lâmina residia aproximadamente na hora certa, exceto à noite, em que, como é de se esperar, não havia sombra e nem horário marcado.

Instruções: Você receberá um documento com uma ```section``` com classe "sky" cuja cor de fundo é controlada pela classe "night" e é preta, para simbolizar o céu durante a noite. Secretamente, esta ```section``` possui três ```div```s vazias: uma em cada canto inferior e outra no meio da ```section```, colada ao topo deste elemento. Estas ```div```s simbolizam a posição do Sol ao longo dia: canto inferior esquerdo, 6 da manhã; topo, meio-dia; canto inferior direito, 6 da tarde. 

Na segunda ```section```, encontram-se um botão, uma imagem que representa o relógio solar, e um ```input``` do tipo ```time``` que representa um relógio moderno :watch:. O botão, ao ser clicado pela primeira vez, mostrará uma imagem do Sol na ```div``` mais à esquerda, o nascer do dia. Na segunda vez, removerá o Sol da primeira ```div``` e o mostrará na segunda, no topo. Na terceira vez, removerá o Sol da posição anterior e o mostrará na ```div``` mais à direita. Em um quarto clique, o Sol deverá desaparecer do céu, pois anoiteceu. Em um quinto clique, é um novo dia e o Sol nascerá novamente. E assim por diante, o ciclo eterno de nascer e por do Sol.

É importante notar que o céu muda ao longo dia e da noite. Sendo assim, ao nascer do Sol, a ```section``` de classe "sky" deve receber a classe "sunrise", que possui um gradiente de cores que tenta simular o espetáculo do nascer do Sol. Ao meio dia, deve ter esta classe trocada por "midday". Ao por do Sol, deve perder esta classe e ganhar aquela chamada "sunset", que também possui um gradiente de cores. Quando anoitecer, a classe "night" deve retornar ao elemento ```section``` de classe "sky". É importante ressaltar que a classe "sky" deve sempre permanecer, pois ela contém estilo próprio e, se removida, quebrará a página. Note que as ```div```s onde o Sol aparece possuem uma classe ("quadrant"), então use isso a seu favor quando for selecioná-las.

Ao passar o *mouse* em cima da imagem do relógio solar, o ```input``` do tipo ```time``` terá o seu atributo ```value``` alterado para mostrar um horário entre as seguintes opções: '06:00', '12:00', '18:00', dependendo da posição do Sol. Se o Sol avançar para outra posição no céu, o atributo ```value``` deste ```input``` deve ficar vazio. Lembrando que à noite não deve ser possível descobrir as horas no relógio solar, então o valor do relógio moderno deve permanecer vazio.

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: auto;
      width: 90%;
    }

    h1 {
      text-align: center;
    }

    section {
      border: 1px solid aquamarine;
      display: flex;
      flex-direction: row;
      margin: 10px auto;
      width: 1200px;
    }

    .sky {
      align-items: flex-end;
      height: 500px;
      justify-content: space-between;
    }

    section:last-of-type {
      align-items: center;
      height: 100px;
      justify-content: space-evenly;
    }

    .quadrant:nth-of-type(2) {
      align-self: flex-start;
    }

  .quadrant>img {
      border-radius: 50%;
      height: 200px;
    }

    section>img {
      height: 100px;
    }

    .quadrant {
      height: 200px;
      width: 200px;
    }

    button {
      padding: 10px;
    }

    .sunrise {
      background: linear-gradient(to top, #58151A, #BC2909, #BA6D09, #71A8EE, #3072EB, #1552C6, #0542A8);
    }

    .sunset {
      background: linear-gradient(to top, #040308, #AD4A28, #DD723C, #FC7001, #DCB697, #9BA5AE, #3E5879, #020B1A);
    }

    .night {
      background-color: black;
    }

    .midday {
      background-color: rgb(221, 245, 255)
    }
  </style>
  <title>Relógio solar</title>
</head>

<body>
  <h1>Relógio solar</h1>
  <section class="sky night">
    <div class="quadrant"></div>
    <div class="quadrant"></div>
    <div class="quadrant"></div>
  </section>
  <section>
    <button>Avançar</button>
    <img src="https://i.ibb.co/Bnxrb6z/sundial.png" alt="Sundial">
    <div>
      <label for="time">Relógio moderno:</label>
      <input type="time" id="time">
    </div>
  </section>
  <script></script>
</body>

</html>

A imagem do sol que você deve utilizar é esta: <img src="https://i.ibb.co/MhqWgJd/sun.png" alt="Sun">.

Dica: você pode criar uma variável numérica para guardar a posição do Sol no céu. Assim, ao clicar no botão, você pode incrementá-la em ```1```. A partir de então, poderá usá-la como índice caso você decida tratar as ```divs``` que guardam as posições no céu como um array.