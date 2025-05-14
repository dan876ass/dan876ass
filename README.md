<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grand World</title>
  
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #fff8dc;
      text-align: center;
    }
    .header {
      padding: 40px 20px;
    }
    .header img {
      max-width: 250px;
    }
    .tagline {
      margin: 20px 0;
      font-size: 1.2em;
      color: #ff5722;
      font-weight: bold;
    }
    .launch-year {
      color: #ff9800;
      margin-bottom: 30px;
      font-size: 1.1em;
    }
    .btn {
      display: inline-block;
      margin: 10px auto;
      padding: 15px 30px;
      background-color: #4CAF50;
      color: white;
      text-decoration: none;
      font-size: 1.2em;
      border-radius: 5px;
    }
    .menu {
      position: fixed;
      bottom: 0;
      width: 100%;
      background: #fff;
      border-top: 1px solid #ccc;
      padding: 10px 0;
      cursor: pointer;
    }
    .menu-content {
      display: none;
      background: #fff;
      padding: 20px 0;
    }
    .menu-content a {
      display: block;
      color: #333;
      text-decoration: none;
      font-size: 1.1em;
      padding: 10px 0;
    }
  </style>
  <script>
    function toggleMenu() {
      var content = document.getElementById("menuContent");
      content.style.display = content.style.display === "block" ? "none" : "block";
    }
  </script>
</head>
<body>

  <div class="header">
    <img src="https://upload.wikimedia.org/wikipedia/commons/2/2d/Placeholder_logo.svg" alt="Grand World Logo">
    <div class="tagline">LANÇADO EM 2025 TRAZENDO</div>
    <div class="launch-year">AVENTURAS PRA VOCÊ!</div>
    <a href="#" class="btn">ENTRAR NO MUNDO</a>
  </div>

  <div class="menu" onclick="toggleMenu()">
    <span>&#8962; Menu</span>
  </div>

  <div class="menu-content" id="menuContent">
    <a href="novidade.html">Novidades</a>
    <a href="classe.html">Classes</a>
    <a href="raça.html">Raças</a>
    <a href="aprimorar.html">Melhorar Arma</a>
    <a href="Bestiario.html">Bestiário</a>
    <a href="evolução.html">Evolução</a>
    <a href="loja.html">Loja</a>
    <a href="parceiros.html">Parceiros</a>
    <a href="treinos.html">Treinos</a>
    <a href="casamento.html">Casamento</a>
    <a href="guias.html">Outros Guias</a>
    <a href="viagem.html">Viagem</a>
  </div>

</body>
</html>
