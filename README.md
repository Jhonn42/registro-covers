# registro-covers
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Registro de Celular</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 40px;
    }

    .form-container {
      background: white;
      padding: 20px 30px;
      max-width: 400px;
      margin: auto;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    input, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      background-color: #25D366;
      color: white;
      font-weight: bold;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background-color: #1ebe5d;
    }
  </style>
</head>
<body>

  <div class="form-container">
    <h2>Registro de Dispositivo</h2>
    <form id="formularioWhatsapp">
      <label for="nombre">Nombre:</label>
      <input type="text" id="nombre" name="nombre" required>

      <label for="modelo">Modelo del celular:</label>
      <input type="text" id="modelo" name="modelo" required>

      <button type="submit">Enviar por WhatsApp</button>
    </form>
  </div>

  <script>
    document.getElementById("formularioWhatsapp").addEventListener("submit", function(e){
      e.preventDefault();

      const nombre = document.getElementById("nombre").value.trim();
      const modelo = document.getElementById("modelo").value.trim();

      if (!nombre || !modelo) {
        alert("Por favor, completa todos los campos.");
        return;
      }

      const numeroDestino = "8295135915"; // Número con código de país sin "+" ni espacios
      const mensaje = `Hola, me llamo ${nombre} y tengo un celular modelo ${modelo}.`;

      let enlaceWhatsapp;
      if (/iPhone|iPad|iPod/.test(navigator.userAgent)) {
        // WhatsApp en iPhone
        enlaceWhatsapp = `whatsapp://send?phone=${numeroDestino}&text=${encodeURIComponent(mensaje)}`;
      } else {
        // WhatsApp Web en otros dispositivos
        enlaceWhatsapp = `https://api.whatsapp.com/send?phone=${numeroDestino}&text=${encodeURIComponent(mensaje)}`;
      }

      // Abrir el enlace de WhatsApp
      window.open(enlaceWhatsapp, "_blank");
    });
  </script>

</body>
</html>
