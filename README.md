# -ALITA-RICA-menupedidos
Menu-pedidos Alita rica

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ALITA RICA - Menú Premium</title>
  <!-- Enlace al manifiesto PWA -->
  <link rel="manifest" href="manifest.json">
  <!-- Icono de la app -->
  <link rel="icon" href="logo.png">
  <!-- Color de la barra en la app instalada -->
  <meta name="theme-color" content="#ff6600">
  <style>
    body{
      font-family: Arial, sans-serif;
      background:#111;
      color:white;
      margin:0; padding:0;
    }
    header{
      background:#ff6600;
      padding:15px;
      text-align:center;
    }
    header img{
      max-height: 60px;
      vertical-align: middle;
    }
    .container{
      padding:15px;
    }
    .card{
      background:#1c1c1c;
      padding:15px;
      margin-bottom:15px;
      border-radius:12px;
      box-shadow:0 0 10px rgba(0,0,0,0.5);
    }
    /* Botón flotante de WhatsApp (fijo en esquina) */
    #whatsapp-button {
      position: fixed;
      bottom: 20px;
      right: 20px;
      z-index: 9999;
    }
    #whatsapp-button img {
      width: 60px;
      height: auto;
    }
    button{
      background:#ff6600;
      color:white;
      border:none;
      padding:8px;
      border-radius:8px;
      cursor:pointer;
      margin-top:5px;
      width:100%;
    }
    button:hover{
      background:#ff3300;
    }
    input, select, textarea{
      width:100%;
      padding:8px;
      margin-top:5px;
      border-radius:6px;
      border:none;
    }
    .total{
      font-size:20px;
      font-weight:bold;
      text-align:center;
      margin-top:10px;
      color:#00ff88;
    }
    /* Panel admin oculto (se muestra con Alt+A) */
    #adminPanel{
      background:#282828;
      padding:10px;
      margin-top:15px;
      border:2px dashed #555;
      display:none;
    }
  </style>
</head>
<body>

<header>
  <!-- Logotipo en la cabecera -->
  <img src="logo.png" alt="Logo Alita Rica">
</header>

<div class="container">

  <!-- Datos del Cliente -->
  <div class="card">
    <h3>👤 Tus datos</h3>
    Nombre:<br>
    <input type="text" id="nombre" placeholder="Tu nombre aquí">
    <br>
    Servicio:<br>
    <select id="servicio" onchange="mostrarDireccion()">
      <option value="Pickup">Pickup</option>
      <option value="Delivery">Delivery</option>
    </select>
    <br>
    <!-- Mostrar dirección sólo para Delivery -->
    <div id="direccionBox" style="display:none;">
      Dirección:<br>
      <input type="text" id="direccion" placeholder="Tu dirección">
    </div>
  </div>

  <!-- Selección de Sabor (para Wings/Boneless) -->
  <div class="card">
    <h3>🍗 Sabor (Wings/Boneless)</h3>
    <select id="sabor">
      <option value="">-- Seleccionar sabor --</option>
      <option>Takis Blu</option>
      <option>BBQ</option>
      <option>Chetos Bolita</option>
      <option>Ruffles Queso</option>
      <option>Chetos Flamin</option>
      <option>Mango Habanero</option>
      <option>Skwinkles</option>
      <option>Sauce Blanck Tajin</option>
      <option>Doritos Incógnita</option>
      <option>Lemon Pepper</option>
      <option>Búffalo</option>
      <option>Pulparindo</option>
    </select>
  </div>

  <!-- Menú: Burgers -->
  <div class="card">
    <h3>🍔 Burgers</h3>
    <button onclick="agregar('Burger clásica c/ papas',109)">Clásica $109</button>
    <button onclick="agregar('Doble bacón c/ papas',129)">Doble Bacón $129</button>
    <button onclick="agregar('Champiburger c/ papas',145)">Champiburger $145</button>
    <button onclick="agregar('Hawaianburger c/ papas',145)">Hawaian $145</button>
    <button onclick="agregar('Cachitoburger c/ papas',165)">Cachitoburger $165</button>
    <button onclick="agregar('Promo Smash 3 pzas c/ papas',99)">Promo Smash $99</button>
  </div>

  <!-- Menú: Wings -->
  <div class="card">
    <h3>🍗 Wings</h3>
    <button onclick="agregarConSabor('Wings 10 pzas',139)">10 pzas $139</button>
    <button onclick="agregarConSabor('Wings 18 pzas',229)">18 pzas $229</button>
    <button onclick="agregarConSabor('Wings 28 pzas',329)">28 pzas $329</button>
  </div>

  <!-- Menú: Boneless -->
  <div class="card">
    <h3>🍗 Boneless</h3>
    <button onclick="agregarConSabor('Boneless 10 pzas',139)">10 pzas $139</button>
    <button onclick="agregarConSabor('Boneless 18 pzas',239)">18 pzas $239</button>
    <button onclick="agregarConSabor('Boneless 28 pzas',339)">28 pzas $339</button>
  </div>

  <!-- Menú: Jochos -->
  <div class="card">
    <h3>🌭 Jochos</h3>
    <button onclick="agregar('Jocho clásico',35)">Clásico $35</button>
    <button onclick="agregar('Jocho hawaiano',45)">Hawaiano $45</button>
    <button onclick="agregar('Jocho champi',45)">Champi $45</button>
    <button onclick="agregar('Cachitojocho',60)">Cachitojocho $60</button>
    <button onclick="agregar('PromoJocho 2x',60)">Promo 2x $60</button>
  </div>

  <!-- Sección de pedido -->
  <div class="card">
    <h3>📝 Tu pedido</h3>
    <textarea id="pedido" rows="5" readonly></textarea>
    <div class="total">Total: $<span id="total">0</span></div>
    <button onclick="enviarPedido()">📲 Enviar Pedido</button>
  </div>

  <!-- Panel Admin (oculto por defecto) -->
  <div id="adminPanel">
    <h3>🔧 Panel Admin (cambiar precios)</h3>
    <p>Aquí podrías editar cada producto y su precio.</p>
    <button onclick="guardarPrecios()">Guardar cambios</button>
  </div>

</div>

<!-- Botón flotante de WhatsApp (esquina inferior derecha) -->
<div id="whatsapp-button">
  <a href="https://wa.me/529903667103" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/WhatsApp_icon.png" alt="WhatsApp">
  </a>
</div>

<script>
let total = 0;
function mostrarDireccion(){
  var servicio = document.getElementById("servicio").value;
  document.getElementById("direccionBox").style.display =
    (servicio === "Delivery") ? "block" : "none";
}
function agregar(nombre, precio){
  total += precio;
  let pedido = document.getElementById("pedido");
  pedido.value += nombre + " - $" + precio + "\\n";
  document.getElementById("total").innerText = total;
}
function agregarConSabor(nombre, precio){
  let sabor = document.getElementById("sabor").value;
  if(!sabor){
    alert("Selecciona un sabor primero.");
    return;
  }
  total += precio;
  let pedido = document.getElementById("pedido");
  pedido.value += nombre + " ("+sabor+") - $" + precio + "\\n";
  document.getElementById("total").innerText = total;
}
function enviarPedido(){
  let nombre = document.getElementById("nombre").value;
  let servicio = document.getElementById("servicio").value;
  let direccion = document.getElementById("direccion").value;
  let pedidoTxt = document.getElementById("pedido").value;
  if(!nombre || !pedidoTxt){
    alert("Completa tu nombre y selecciona algún producto.");
    return;
  }
  if(servicio==="Delivery" && !direccion){
    alert("Ingresa tu dirección para delivery.");
    return;
  }
  let mensaje = "🔥 ALITA RICA 🔥\\n"
              + "Cliente: " + nombre + "\\n"
              + "Servicio: " + servicio + "\\n"
              + (servicio==="Delivery" ? "Dirección: " + direccion + "\\n" : "")
              + "\\nPedido:\\n" + pedidoTxt
              + "Total: $" + total;
  let telefono = "529903667103";
  let url = "https://wa.me/" + telefono + "?text=" + encodeURIComponent(mensaje);
  window.open(url);
}
// Toggle del panel admin con Alt+A
document.addEventListener('keydown', function(e){
  if(e.key === 'A' && e.altKey){
    let panel = document.getElementById("adminPanel");
    panel.style.display = (panel.style.display==="none"?"block":"none");
  }
});
// Ejemplo básico: guardar precios en localStorage
function guardarPrecios(){
  // Por ejemplo: localStorage.setItem('precios', JSON.stringify(objPrecios));
  alert("Cambios guardados en localStorage (ejemplo).");
}
</script>

</body>
</html>

