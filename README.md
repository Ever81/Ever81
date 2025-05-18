<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>WardrobeAI – Cambia tu ropa con IA</title>
  <style>
    body { font-family: Arial, sans-serif; margin:0; padding:0; color: #333; }
    header { background: #4A90E2; color: white; padding: 2rem 1rem; text-align: center; }
    section { padding: 2rem 1rem; max-width: 800px; margin: auto; }
    h1, h2 { margin-top: 0; }
    .features { display: flex; flex-wrap: wrap; gap: 1rem; }
    .feature { flex: 1 1 calc(50% - 1rem); background: #f0f0f0; padding: 1rem; border-radius: 4px; }
    .demo { text-align: center; }
    .demo img { max-width: 100%; height: auto; margin-top: 1rem; }
    footer { text-align: center; padding: 1rem; background: #222; color: #ccc; }
    button { background: #4A90E2; color: white; border: none; padding: 0.75rem 1.5rem; border-radius: 4px; cursor: pointer; }
    input, select { padding: 0.5rem; margin: 0.5rem 0; width: 100%; max-width: 300px; }
  </style>
</head>
<body>

  <header>
    <h1>WardrobeAI</h1>
    <p>Cambia tu ropa al instante con Inteligencia Artificial</p>
  </header>

  <section>
    <h2>¿Qué es WardrobeAI?</h2>
    <p>
      WardrobeAI es una aplicación basada en IA que te permite probar diferentes estilos de ropa
      sobre tu propia foto. Gracias a técnicas avanzadas de visión por computadora y segmentación
      de imágenes, la IA detecta tu figura y coloca la prenda seleccionada de forma realista.
    </p>
  </section>

  <section>
    <h2>Características</h2>
    <div class="features">
      <div class="feature">
        <h3>Subida de foto</h3>
        <p>Sólo sube tu imagen y la IA detectará automáticamente tu silueta.</p>
      </div>
      <div class="feature">
        <h3>Catálogo de prendas</h3>
        <p>Elige entre camisetas, chaquetas, vestidos y más, todo en alta calidad.</p>
      </div>
      <div class="feature">
        <h3>Ajuste realista</h3>
        <p>La IA adapta la prenda a la postura y ángulo de tu foto.</p>
      </div>
      <div class="feature">
        <h3>Compartir</h3>
        <p>Descarga o comparte tu nueva imagen en redes sociales al instante.</p>
      </div>
    </div>
  </section>

  <section class="demo">
    <h2>Prueba la demo</h2>
    <p>Sube tu foto y elige una prenda:</p>
    <input type="file" id="userImage" accept="image/*" />
    <br/>
    <select id="clothingSelect">
      <option value="">— Selecciona prenda —</option>
      <option value="camiseta">Camiseta casual</option>
      <option value="chaqueta">Chaqueta de cuero</option>
      <option value="vestido">Vestido elegante</option>
    </select>
    <br/>
    <button onclick="applyClothing()">Aplicar IA</button>
    <div id="resultArea">
      <!-- Aquí se mostrará el resultado -->
    </div>
  </section>

  <footer>
    <p>&copy; 2025 WardrobeAI · Hecho con ♥ por tu equipo de IA</p>
  </footer>

  <script>
    function applyClothing() {
      const fileInput = document.getElementById('userImage');
      const select = document.getElementById('clothingSelect');
      const resultArea = document.getElementById('resultArea');

      if (!fileInput.files[0] || !select.value) {
        alert('Por favor sube una foto y selecciona una prenda.');
        return;
      }

      const reader = new FileReader();
      reader.onload = function(e) {
        // Simulación: en vez de IA real, solo mostramos la misma foto con título
        resultArea.innerHTML = `
          <h3>Resultado simulado</h3>
          <p>Prenda aplicada: <strong>${select.options[select.selectedIndex].text}</strong></p>
          <img src="${e.target.result}" alt="Tu foto con IA" />
        `;
        // Aquí es donde llamarías a tu API de IA para procesar imagen y prenda
      }
      reader.readAsDataURL(fileInput.files[0]);
    }
  </script>

</body>
</html>
