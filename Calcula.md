<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Grand Calculadora</title>  
 
  <style>
    body {
      background-color: #111;
      color: #fff;
      font-family: 'Arial', sans-serif;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 600px;
      margin: 40px auto;
      background-color: #1b1f3a;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.1);
    }

    h1 {
      text-align: center;
      color: #f54266;
      margin-bottom: 30px;
      font-size: 28px;
    }

    .section {
      margin-bottom: 20px;
    }

    label {
      display: block;
      margin-bottom: 8px;
      font-weight: bold;
      color: #ddd;
    }

    input {
      width: 100%;
      padding: 10px;
      margin-bottom: 12px;
      border-radius: 8px;
      border: none;
      background-color: #333;
      color: white;
    }

    .resultado {
      background-color: #262626;
      padding: 20px;
      border-radius: 10px;
      margin-top: 20px;
      font-size: 18px;
      text-align: center;
    }

    button {
      background-color: #f54266;
      color: white;
      border: none;
      padding: 10px 20px;
      font-size: 16px;
      border-radius: 10px;
      cursor: pointer;
      width: 100%;
    }

    button:hover {
      background-color: #d93758;
    }

    .formula {
      background-color: #2d2d2d;
      padding: 15px;
      border-radius: 10px;
      font-size: 16px;
      margin-bottom: 20px;
      color: #ccc;
    }
  </style>
</head>
  </style>
</head>
<body>

  <h1>Calculadora de Atributos</h1>

  <div id="formulario">
    <!-- Atributos -->
    <div class="atributo" id="atributos"></div>

    <button onclick="calcular()">Calcular Efeitos</button>
  </div>

  <h2>Resultados:</h2>
  <div class="resultados" id="resultados"></div>

  <script>
    const atributosBase = [
      "Força", "Resistência", "Inteligência", 
      "Agilidade", "Destreza", "Velocidade"
    ];

    const atributosDiv = document.getElementById('atributos');

    atributosBase.forEach(attr => {
      atributosDiv.innerHTML += `
        <div>
          <strong>${attr}</strong><br>
          Base: <input type="number" id="${attr}_base" value="0"> 
          Buff: <input type="number" id="${attr}_buff" value="0"> 
          Debuff: <input type="number" id="${attr}_debuff" value="0">
        </div><br>
      `;
    });

    function calcular() {
      const res = {};
      atributosBase.forEach(attr => {
        const base = parseInt(document.getElementById(`${attr}_base`).value) || 0;
        const buff = parseInt(document.getElementById(`${attr}_buff`).value) || 0;
        const debuff = parseInt(document.getElementById(`${attr}_debuff`).value) || 0;
        res[attr] = base + buff - debuff;
      });

      let html = "";
      html += `<strong>Força (${res["Força"]})</strong><br>`;
      html += `Carga: ${res["Força"] * 10} kg<br>`;
      html += `Dano Físico: ${Math.floor(res["Força"]/2)*10}<br>`;
      html += `Arremesso: ${Math.floor(res["Força"]/2)*2} km<br><br>`;

      html += `<strong>Resistência (${res["Resistência"]})</strong><br>`;
      html += `Redução de Dano Físico: ${Math.floor(res["Resistência"]/2)*3}%<br>`;
      html += `Ações Extras: ${Math.floor(res["Resistência"]/10)}<br>`;
      html += `Resistência Mágica: ${Math.floor(res["Resistência"]/2)*10} kg<br><br>`;

      html += `<strong>Inteligência (${res["Inteligência"]})</strong><br>`;
      html += `Ações Mágicas: ${Math.floor(res["Inteligência"]/3)}<br>`;
      html += `Resistência Mental: ${Math.floor(res["Inteligência"]/2)*2}%<br>`;
      html += `Resistência Mágica: ${res["Inteligência"] * 2}<br>`;
      html += `Regen de Mana: ${Math.floor(res["Inteligência"]/10)}<br>`;
      html += `Dano Mágico: ${res["Inteligência"]}<br>`;
      html += `Velocidade de Feitiço: ${Math.floor(res["Inteligência"]/2)} km/h<br><br>`;

      html += `<strong>Agilidade (${res["Agilidade"]})</strong><br>`;
      html += `Alcance de Visão: ${(Math.floor((Math.floor(res["Inteligência"]/2))/2)) * 10} m<br>`;
      html += `Chance de Detecção: ${res["Agilidade"] * 3}%<br><br>`;

      html += `<strong>Destreza (${res["Destreza"]})</strong><br>`;
      html += `Acerto com armas leves/projéteis: ${res["Destreza"] * 3}%<br>`;
      html += `Reflexos: ${res["Destreza"]} km/h<br><br>`;

      html += `<strong>Velocidade (${res["Velocidade"]})</strong><br>`;
      html += `Deslocamento: ${res["Velocidade"]} m/s<br>`;
      html += `Iniciativa: ${Math.floor(res["Velocidade"]/5)}<br><br>`;

      document.getElementById("resultados").innerHTML = html;
    }
    
  </script>

</body>
</html>
