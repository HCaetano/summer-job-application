# JavaScript - Eventos - Gabarito

## Exercício 1

  Você receberá um documento com dois parágrafos repletos de lorem ipsum, um botão para cada período/alteração do texto, e a estilização já pronta. Sua tarefa é criar eventos de clique que troquem a fonte do texto para as fontes fornecidas logo acima da *tag* ```title```. A escolha de qual fonte será associada a qual botão deixaremos por sua conta, mas testando você vai notar que algumas se encaixam melhores do que as outras.

### Gif

  <img src="https://shorturl.at/gpCY6" alt="" height="400px">

### Solução:

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

  <script>
    const textSection = document.querySelector('section');
    const buttons = document.querySelectorAll('button');

    buttons[0].addEventListener('click', function () {
      textSection.style.fontFamily = 'Butcherman';
    })
    buttons[1].addEventListener('click', function () {
      textSection.style.fontFamily = 'Ewert';
    })
    buttons[2].addEventListener('click', function () {
      textSection.style.fontFamily = 'Caesar Dressing';
    })
    buttons[3].addEventListener('click', function () {
      textSection.style.fontFamily = 'Give You Glory';
    })
    buttons[4].addEventListener('click', function () {
      textSection.style.fontFamily = 'Astloch';
    })
    buttons[5].addEventListener('click', function () {
      textSection.style.fontFamily = 'Orbitron';
    })
  </script>
</body>

</html>

## Exercício 2

  Você receberá um documento com quatro ```div```s vazias delimitadas por bordas pretas. Cada uma delas possui logo abaixo de si um campo de ```input``` do tipo ```text``` no qual você deverá digitar os nomes das cores. Feito isto, o ```input``` alterará o valor de ```background-color``` da ```div``` logo acima dele próprio a medida que você for digitando. Teste cores legais como Aquamarine, Maroon e MidnightBlue.

### Gif

  <img src="https://shorturl.at/cxzJR" alt="" height="400px">

### Solução:
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
    <script>
      const colorBlocks = document.querySelectorAll('.color-block');
      const textInputs = document.querySelectorAll('input');

      textInputs[0].addEventListener('input', function () {
        const chosenColor = textInputs[0].value;
        colorBlocks[0].style.backgroundColor = chosenColor;
      });

      textInputs[1].addEventListener('input', function () {
        const chosenColor = textInputs[1].value;
        colorBlocks[1].style.backgroundColor = chosenColor;
      });

      textInputs[2].addEventListener('input', function () {
        const chosenColor = textInputs[2].value;
        colorBlocks[2].style.backgroundColor = chosenColor;
      });

      textInputs[3].addEventListener('input', function () {
        const chosenColor = textInputs[3].value;
        colorBlocks[3].style.backgroundColor = chosenColor;
      });
    </script>
  </body>

  </html>

## Exercício 3

  Você receberá um documento com uma imagem inicial do gato misterioso em uma ```section```. Ao lado desta, há outra ```section```, que contém três sentenças proferidas pelo gato apresentadas em elementos ```p```. Ao passar o *mouse* sobre estas sentenças, o atributo ```source``` da imagem inicial deve ser alterada para uma das outras três imagens do gato disponibilizadas. A nova imagem só deve permanecer visível enquanto o *mouse* estiver sobre o elemento que contém a sentença. Ao retirar o *mouse* de cima da sentença, a imagem inicial do gato sentado deve ser restaurada. Dica: use 'mouseover'.

### Gif

  <img src="https://shorturl.at/rvIZ6" alt="" height="400px">

### Solução:

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
    <script>
      const catDialogues = document.querySelectorAll('p');
      const image = document.querySelector('img');

      catDialogues[0].addEventListener('mouseover', function () {
        image.src = 'https://i.ibb.co/Bz9fspD/cats-01.jpg';
      });

      catDialogues[1].addEventListener('mouseover', function () {
        image.src = 'https://i.ibb.co/y5wdwpf/cats-03.jpg';
      });

      catDialogues[2].addEventListener('mouseover', function () {
        image.src = 'https://i.ibb.co/4gGnp3r/cats-04.jpg';
      });

      for (let index = 0; index < catDialogues.length; index += 1) {
        catDialogues[index].addEventListener('mouseout', function () {
          image.src = 'https://i.ibb.co/HHYrw6D/cats-02.jpg';
        });
      }
    </script>
  </body>

  </html>
    

## Exercício 4

  Você receberá um documento com a imagem de um navio que, por sua vez, possui sobreposto a si três imagens de furos em seu casco. O navio é a imagem de fundo de uma ```section``` e os curativos ficam em outra ```section```. 

### Gif

  <img src="https://shorturl.at/vDHQ3" alt="" height="400px">

### Solução:

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
    <script>
      const holes = document.querySelectorAll('.hole');
      const bandages = document.querySelectorAll('.bandages');
      let selectedBandage;

      for (let index = 0; index < bandages.length; index += 1) {
        bandages[index].addEventListener('click', function (event) {
          selectedBandage = event.target.src;
        })
      }

      for (let index = 0; index < holes.length; index += 1) {
        holes[index].addEventListener('click', function (event) {
          holes[index].src = selectedBandage;
        })
      }
    </script>
  </body>
      <!-- Accrediting the author:
      <a href="https://www.vecteezy.com/free-vector/ship-vector">Ship Vector Vectors by Vecteezy</a>
      <a href="https://www.vecteezy.com/free-vector/band">Band Vectors by Vecteezy</a> -->
  </html>

## Exercício bônus

  Você receberá um documento com uma ```section``` com classe "sky" cuja cor de fundo é controlada pela classe "night" e é preta, para simbolizar o céu durante a noite. Secretamente, esta ```section``` possui três ```div```s vazias: uma em cada canto inferior e outra no meio da ```section```, colada ao topo deste elemento. Estas ```div```s simbolizam a posição do Sol ao longo dia: canto inferior esquerdo, 6 da manhã; topo, meio-dia; canto inferior direito, 6 da tarde. 

  Na segunda ```section```, encontram-se um botão, uma imagem que representa o relógio solar, e um ```input``` do tipo ```time``` que representa um relógio moderno :watch:. O botão, ao ser clicado pela primeira vez, mostrará uma imagem do Sol na ```div``` mais à esquerda, o nascer do dia. Na segunda vez, removerá o Sol da primeira ```div``` e o mostrará na segunda, no topo. Na terceira vez, removerá o Sol da posição anterior e o mostrará na ```div``` mais à direita. Em um quarto clique, o Sol deverá desaparecer do céu, pois anoiteceu. Em um quinto clique, é um novo dia e o Sol nascerá novamente. E assim por diante, o ciclo eterno de nascer e por do Sol.

  É importante notar que o céu muda ao longo dia e da noite. Sendo assim, ao nascer do Sol, a ```section``` de classe "sky" deve receber a classe "sunrise", que possui um gradiente de cores que tenta simular o espetáculo do nascer do Sol. Ao meio dia, deve ter esta classe trocada por "midday". Ao por do Sol, deve perder esta classe e ganhar aquela chamada "sunset", que também possui um gradiente de cores. Quando anoitecer, a classe "night" deve retornar ao elemento ```section``` de classe "sky". É importante ressaltar que a classe "sky" deve sempre permanecer, pois ela contém estilo próprio e, se removida, quebrará a página. Note que as ```div```s onde o Sol aparece possuem uma classe ("quadrant"), então use isso a seu favor quando for selecioná-las.

  Ao passar o *mouse* em cima da imagem do relógio solar, o ```input``` do tipo ```time``` terá o seu atributo ```value``` alterado para mostrar um horário entre as seguintes opções: '06:00', '12:00', '18:00', dependendo da posição do Sol. Se o Sol avançar para outra posição no céu, o atributo ```value``` deste ```input``` deve ficar vazio. Lembrando que à noite não deve ser possível descobrir as horas no relógio solar, então o valor do relógio moderno deve permanecer vazio.

### Gif

  <img src="https://shorturl.at/ejMV8" alt="" height="400px">

### Solução:

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
    <script>
      const button = document.querySelector('button');
      const quadrants = document.querySelectorAll('.quadrant');
      const sky = document.querySelector('.sky');
      const sundial = document.querySelector('section > img');
      const modernClock = document.querySelector('input');
      const sun = 'https://i.ibb.co/MhqWgJd/sun.png';
      let position = -1;
      let previousPosition;

      function changeSkyColor(position) {
        switch (position) {
          case 0:
            sky.classList.add('sunrise');
            break;
          case 1:
            sky.classList.remove('sunrise');
            sky.classList.add('midday');
            break;
          case 2:
            sky.classList.remove('midday');
            sky.classList.add('sunset');
            break;
          case 3:
            sky.classList.remove('sunset');
            sky.classList.add('night');
            break;
          default:
            break;
        }
      }

      function handleSunAppearance(position) {
        const image = document.createElement('img');
        image.src = sun;

        if (position > -1) {
          previousPosition = position - 1;

          if (position > 0) {
            quadrants[previousPosition].innerHTML = '';
          }

          if (position < 3) {
            quadrants[position].appendChild(image);
          }
        }

        modernClock.value = '';
      }

      button.addEventListener('click', function () {
        position = position > 2 ? 0 : position + 1;
        changeSkyColor(position);
        handleSunAppearance(position);
      });

      function whatTimeIsIt(position) {
        switch (position) {
          case 0:
            modernClock.value = '06:00'
            break;
          case 1:
            modernClock.value = '12:00'
            break;
          case 2:
            modernClock.value = '18:00'
            break;
          default:
            break;
        }
      }

      sundial.addEventListener('mouseover', function () {
        whatTimeIsIt(position);
      })
    </script>
  </body>

  </html>