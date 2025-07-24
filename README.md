# Ozurdilerimazra
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Barışalım mı?</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      text-align: center;
      background-color: #fce4ec;
      padding: 40px;
    }

    h1 {
      color: #d81b60;
      font-size: 32px;
    }

    #buttons {
      margin-top: 30px;
    }

    button {
      font-size: 18px;
      padding: 15px 25px;
      margin: 10px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    #evet {
      background-color: #4caf50;
      color: white;
    }

    #hayir {
      background-color: #f44336;
      color: white;
    }

    #hayir-msg {
      margin-top: 20px;
      font-weight: bold;
      color: #c62828;
    }

    #final-msg {
      display: none;
      font-size: 20px;
      color: #2e7d32;
      margin-top: 30px;
    }
  </style>
</head>
<body>

  <h1>Webde ARKADAŞ OLALIM MI 😇 </h1>

  <div id="buttons">
    <button id="evet">Evet</button>
    <button id="hayir">Hayır</button>
  </div>

  <div id="hayir-msg"></div>
  <div id="final-msg">💚 Barıştık! Her şey güzel olacak 💚</div>

  <script>
    let hayirSayisi = 0;
    const hayirMesajlari = [
      "Emin misin? 🥺",
      "Son kararın mı? 😢",
      "Gerçekten mi? 😞"
    ];

    const evetBtn = document.getElementById("evet");
    const hayirBtn = document.getElementById("hayir");
    const msg = document.getElementById("hayir-msg");
    const finalMsg = document.getElementById("final-msg");

    hayirBtn.addEventListener("click", () => {
      if (hayirSayisi < hayirMesajlari.length) {
        msg.textContent = hayirMesajlari[hayirSayisi];
        hayirSayisi++;
        evetBtn.style.transform = `scale(${1 + hayirSayisi * 0.2})`;
      } else {
        msg.textContent = "Bu kadar ısrardan sonra hâlâ mı hayır? 😭";
        evetBtn.style.transform = "scale(2)";
      }
    });

    evetBtn.addEventListener("click", () => {
      msg.textContent = "";
      finalMsg.style.display = "block";
    });
  </script>

</body>
</html>
