# registro-covers
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Registro de Celular</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to right, #00c6ff, #0072ff);
      padding: 40px;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .form-container {
      background: white;
      padding: 30px;
      max-width: 400px;
      border-radius: 15px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
      transition: transform 0.3s;
    }

    .form-container:hover {
      transform: scale(1.02);
    }

    h2 {
      text-align: center;
      color: #0072ff;
      margin-bottom: 20px;
    }

    label {
      font-weight: bold;
      margin-top: 10px;
      display: block;
    }

    input[type="text"] {
      width: 100%;
      padding: 12px;
      margin-top: 8px;
      border-radius: 8px;
      border: 1px solid #ccc;
      transition: border-color 0.3s;
    }

    input[type="text"]:focus {
      border-color: #0072ff;
      outline: none;
    }

    button {
      width: 100%;
      padding: 12px;
      margin-top: 15px;
      border-radius: 8px;
      border: none;
      background-color: #25D366;
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #1ebe5d;
    }

    .footer {
      text-align: center;
      margin-top: 20px;
      font-size: 0.9em;
      color: #555;
    }
  </style>
</head>
<body>

  <div class="form-container">
    <h2><i class="fas fa-mobile-alt"></i> Registro de Dispositivo</h2>
    <form id="formularioWhatsapp">
      <label for="nombre">Nombre:</label>
      <input type="text" id="nombre" name="nombre" required>

      <label for="modelo">Modelo del celular:</label>
      <input type="text" id="modelo" name="modelo" required>

      <button type="submit">Enviar por WhatsApp</button>
    </form>
    <div class="footer">© 2025 Custom Covers</div>
  </div>

  <script>
    document.getElementById("formularioWhatsapp").addEventListener("submit", function(e){
      e.preventDefault();

      const nombre = document.getElementById("nombre").value;
      const modelo = document.getElementById("modelo").value;

      const numeroDestino = "8295135915"; // Asegúrate de que este número sea correcto
      const mensaje = `Hola, me llamo ${nombre} y tengo un celular modelo ${modelo}.`;
      const enlaceWhatsapp = `https://wa.me/${numeroDestino}?text=${encodeURIComponent(mensaje)}`;

      window.open(enlaceWhatsapp, "_blank");
    });
  </script>

</body>
</html>
