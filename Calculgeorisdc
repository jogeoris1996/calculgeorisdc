<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Calcul Cintrage Tube</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f3f4f6;
      display: flex;
      justify-content: center;
      padding: 40px;
    }
    .container {
      background: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
      width: 100%;
      max-width: 500px;
    }
    h2 {
      text-align: center;
      margin-bottom: 20px;
    }
    label {
      font-weight: bold;
      display: block;
      margin-top: 15px;
    }
    input {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }
    button {
      margin-top: 20px;
      width: 100%;
      padding: 12px;
      background-color: #1d4ed8;
      color: white;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    button:hover {
      background-color: #2563eb;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Calcul Cintrage Tube</h2>

    <label for="rayon">Rayon (mm)</label>
    <input type="number" id="rayon" step="0.01">

    <label for="angle">Angle (°)</label>
    <input type="number" id="angle" step="0.01">

    <label for="developpement">Développement (mm)</label>
    <input type="number" id="developpement" step="0.01">

    <label for="corde">Corde (mm)</label>
    <input type="number" id="corde" step="0.01">

    <label for="hauteur">Hauteur (mm)</label>
    <input type="number" id="hauteur" step="0.01">

    <button onclick="calculer()">Calculer</button>
  </div>

  <script>
    function toRadians(deg) {
      return deg * Math.PI / 180;
    }

    function toDegrees(rad) {
      return rad * 180 / Math.PI;
    }

    function calculer() {
      let R = parseFloat(document.getElementById("rayon").value);
      let A = parseFloat(document.getElementById("angle").value);
      let D = parseFloat(document.getElementById("developpement").value);
      let C = parseFloat(document.getElementById("corde").value);
      let H = parseFloat(document.getElementById("hauteur").value);

      // Développement = (π * R * A) / 180
      if (!isNaN(R) && !isNaN(A)) {
        D = (Math.PI * R * A) / 180;
        document.getElementById("developpement").value = D.toFixed(2);
      }

      // Angle = (D * 180) / (π * R)
      if (!isNaN(R) && !isNaN(D) && isNaN(A)) {
        A = (D * 180) / (Math.PI * R);
        document.getElementById("angle").value = A.toFixed(2);
      }

      // Corde = 2 * R * sin(A / 2)
      if (!isNaN(R) && !isNaN(A)) {
        let rad = toRadians(A / 2);
        C = 2 * R * Math.sin(rad);
        document.getElementById("corde").value = C.toFixed(2);
      }

      // Hauteur = R * (1 - cos(A / 2))
      if (!isNaN(R) && !isNaN(A)) {
        let rad = toRadians(A / 2);
        H = R * (1 - Math.cos(rad));
        document.getElementById("hauteur").value = H.toFixed(2);
      }

      // Rayon à partir de corde et hauteur
      if (!isNaN(C) && !isNaN(H) && isNaN(R)) {
        R = (H / 2) + (Math.pow(C, 2) / (8 * H));
        document.getElementById("rayon").value = R.toFixed(2);
      }

      // Angle à partir de corde et rayon
      if (!isNaN(C) && !isNaN(R) && isNaN(A)) {
        A = 2 * toDegrees(Math.asin(C / (2 * R)));
        document.getElementById("angle").value = A.toFixed(2);
      }
    }
  </script>
</body>
</html>
