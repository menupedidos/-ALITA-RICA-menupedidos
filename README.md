# -ALITA-RICA-menupedidos
Menupedidos Alita rica
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ALITA RICA - Menú Digital</title>

<style>
body{
font-family: Arial, sans-serif;
background:#0f0f0f;
color:white;
margin:0;
padding:0;
}

header{
background:#ff6600;
padding:20px;
text-align:center;
font-size:22px;
font-weight:bold;
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
</style>
</head>

<body>

<header>
🔥 ALITA RICA 🔥<br>
Sabor de Barrio al Carbón
</header>

<div class="container">

<div class="card">
<h3>👤 Datos del Cliente</h3>
Nombre:
<input type="text" id="nombre">

Servicio:
<select id="servicio" onchange="mostrarDireccion()">
<option value="Pickup">Pickup</option>
<option value="Delivery">Delivery</option>
</select>

<div id="direccionBox" style="display:none;">
Dirección:
<input type="text" id="direccion">
</div>
</div>

<div class="card">
<h3>🍗 Selecciona Sabor (para Wings/Boneless)</h3>
<select id="sabor">
<option value="">-- Selecciona Sabor --</option>
<option>Takis Blu</option>
<option>BBQ</option>
<option>Chetos Bolita</option>
<option>Ruffles Queso</option>
<option>Chetos Flamin</option>
<option>Mango Habanero</option>
<option>Skwinkles</option>
<option>Sauce Blanck Tajin Valentina</option>
<option>Doritos Incógnita</option>
<option>Lemon Pepper</option>
<option>Búffalo</option>
<option>Pulparindo</option>
</select>
</div>

<div class="card">
<h3>🍔 Burgers</h3>
<button onclick="agregar('Burger clásica',109)">Burger clásica $109</button>
<button onclick="agregar('Doble bacón',129)">Doble bacón $129</button>
<button onclick="agregar('Champiburger',145)">Champiburger $145</button>
<button onclick="agregar('Hawaianburger',145)">Hawaianburger $145</button>
<button onclick="agregar('Cachitoburger',165)">Cachitoburger $165</button>
<button onclick="agregar('Promo Smash 3 pzas',99)">Promo Smash $99</button>
</div>

<div class="card">
<h3>🍗 Wings</h3>
<button onclick="agregarConSabor('Wings 10 pzas',139)">10 pzas $139</button>
<button onclick="agregarConSabor('Wings 18 pzas',229)">18 pzas $229</button>
<button onclick="agregarConSabor('Wings 28 pzas',329)">28 pzas $329</button>
</div>

<div class="card">
<h3>🍗 Boneless</h3>
<button onclick="agregarConSabor('Boneless 10 pzas',139)">10 pzas $139</button>
<button onclick="agregarConSabor('Boneless 18 pzas',239)">18 pzas $239</button>
<button onclick="agregarConSabor('Boneless 28 pzas',339)">28 pzas $339</button>
</div>

<div class="card">
<h3>🌭 Jochos</h3>
<button onclick="agregar('Jocho clásico',35)">Clásico $35</button>
<button onclick="agregar('Jocho hawaiano',45)">Hawaiano $45</button>
<button onclick="agregar('Jocho champi',45)">Champi $45</button>
<button onclick="agregar('Cachitojocho',60)">Cachitojocho $60</button>
<button onclick="agregar('PromoJocho 2x',60)">Promo 2x $60</button>
</div>

<div class="card">
<h3>📝 Pedido</h3>
<textarea id="pedido" rows="5" readonly></textarea>
<div class="total">Total: $<span id="total">0</span></div>
<button onclick="enviarPedido()">📲 Enviar Pedido</button>
</div>

</div>

<script>

let total = 0;

function mostrarDireccion(){
let servicio = document.getElementById("servicio").value;
document.getElementById("direccionBox").style.display =
(servicio === "Delivery") ? "block" : "none";
}

function agregar(nombre,precio){
total += precio;
document.getElementById("pedido").value += nombre + " - $" + precio + "\n";
document.getElementById("total").innerText = total;
}

function agregarConSabor(nombre,precio){
let sabor = document.getElementById("sabor").value;
if(sabor === ""){
alert("Selecciona un sabor primero.");
return;
}
total += precio;
document.getElementById("pedido").value += nombre + 
" ("+ sabor +") - $" + precio + "\n";
document.getElementById("total").innerText = total;
}

function enviarPedido(){
let nombre = document.getElementById("nombre").value;
let servicio = document.getElementById("servicio").value;
let direccion = document.getElementById("direccion").value;
let pedido = document.getElementById("pedido").value;

if(nombre === "" || pedido === ""){
alert("Completa tu nombre y selecciona productos.");
return;
}

if(servicio === "Delivery" && direccion === ""){
alert("Ingresa tu dirección para Delivery.");
return;
}

let mensaje = "🔥 ALITA RICA 🔥\n" +
"Cliente: " + nombre + "\n" +
"Servicio: " + servicio + "\n" +
(servicio === "Delivery" ? "Dirección: " + direccion + "\n" : "") +
"\nPedido:\n" + pedido +
"\nTotal: $" + total;

let telefono = "529903667103";
let url = "https://wa.me/" + telefono + "?text=" + encodeURIComponent(mensaje);

window.open(url);
}

</script>

</body>
</html>
