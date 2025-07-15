# Barulho-Divertido
Barulhos divertidos para todos.

<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Barulho Divertido</title>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background-color: #f9f9f9;
      text-align: center;
      padding: 20px;
    }
    h1 span:first-child {
      color: black;
      font-size: 2rem;
    }
    h1 span:last-child {
      color: limegreen;
      font-size: 2.5rem;
    }
    nav a {
      margin: 0 15px;
      font-weight: bold;
      color: #444;
      text-decoration: none;
    }
    .hidden {
      display: none;
    }
    #roleta, #lista {
      margin-top: 30px;
    }
    .lista-palavras button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 1.2rem;
      border: none;
      background-color: #90ee90;
      border-radius: 12px;
      cursor: pointer;
    }
    .roleta {
      margin-top: 20px;
    }
    .roleta button {
      font-size: 1.5rem;
      padding: 15px;
      background-color: #87cefa;
      border: none;
      border-radius: 10px;
      cursor: pointer;
    }
    .resultado {
      font-size: 2rem;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1><span>BARULHO</span> <span style="color:blue;">DIVERTIDO</span></h1>

  <nav>
    <a href="#" onclick="mostrar('roleta')">Roleta</a>
    <a href="#" onclick="mostrar('lista')">Lista</a>
  </nav>

  <div id="roleta" class="hidden">
    <h2>Gire a Roleta!</h2>
    <div class="roleta">
      <button onclick="girarRoleta()">Girar</button>
      <div class="resultado" id="resultadoRoleta"></div>
    </div>
  </div>

  <div id="lista" class="hidden">
    <h2>Toque para ouvir!</h2>
    <div class="lista-palavras">
      <script>
        const sons = {
          'Cachorro': 'Au au',
          'Vaca': 'Muu',
          'Porco': 'Oinc oinc',
          'Cavalo': 'Pocotó',
          'Corneta': 'Póóó',
          'Buzina': 'Bii bii',
          'Campainha': 'Ding dong',
          'Risada': 'Hahaha',
          'Telefone': 'Trim trim',
          'Passarinho': 'Piu piu',
          'Eletricidade': 'Bzzzz',
          'Assobio': 'Fiu fiu'
        };

        for (let palavra in sons) {
          document.write(`<button onclick="falar('${sons[palavra]}')">${palavra}</button>`);
        }
      </script>
    </div>
  </div>

  <script>
    function mostrar(secao) {
      document.getElementById('roleta').classList.add('hidden');
      document.getElementById('lista').classList.add('hidden');
      document.getElementById(secao).classList.remove('hidden');
    }

    function girarRoleta() {
      const palavras = Object.keys(sons);
      const escolhida = palavras[Math.floor(Math.random() * palavras.length)];
      document.getElementById('resultadoRoleta').innerHTML = `${escolhida}: <strong>${sons[escolhida]}</strong>`;
      falar(sons[escolhida]);
    }

    function falar(som) {
      const msg = new SpeechSynthesisUtterance(som);
      msg.lang = 'pt-BR';
      window.speechSynthesis.speak(msg);
    }
  </script>
</body>
</html>


Aqui está o site Barulho Divertido, com as seguintes seções:

🎡 Roleta: gira e ouve o som correspondente.

📜 Lista: clique nas palavras para ouvir os sons.

🎨 Cores e estilo divertido.

📱 Funciona em celular.


Você quer que eu exporte em arquivos prontos para você usar ou quer que publiquemos em alguma plataforma (como GitHub Pages ou Netlify)?

