# 🍔🔥 ALITA RICA – SABOR DE BARRIO AL CARBÓN

Sistema de menú digital interactivo con cálculo automático de total y generación automática de pedidos vía WhatsApp.

Diseñado para ofrecer una experiencia rápida, clara y funcional desde cualquier dispositivo móvil.

---

# 📋 DESCRIPCIÓN DEL MENÚ (MOSTRADO EXACTAMENTE EN EL SISTEMA)

*ALITA RICA SABOR DE BARRIO AL CARBÓN*

Burger clásica c/ papas $109  
Doble bacón c/ papas $129  
Champiburger c/ papas  $145  
Hawaianburger c/papas $145  
Cachitoburger c/ papas $165  

Promo smashsencilla 3pzas s/ papas  $99  

Wings 10 pzas $139  
Wings 18 pzas $229  
Wings 28 pzas $329  
Sabores: Lemon peper, bbq, skwinkles, pulparindo, valentina, blacksauce, doritos incognita, mango habanero, chetos bolita, ruffles queso, Buffalo, takis blu.  

Combo fan $99  
Combo mix $139  

Boneless 10 pzas $139  
Boneless  10 pzas $239  
Boneless 28 pzas $339  
Sabores: Lemon peper, bbq, skwinkles, pulparindo, valentina, blacksauce, doritos incognita, mango habanero, chetos bolita, ruffles queso, Buffalo, takis blu.  

Jocho clásico $35  
Jocho hawaiano $45  
Jocho champi $45  
Cachitojocho $60  

PromoJocho sencillo 2 $60  

Refresco 355ml  
Fanta  $15  
Manzanita $15  
7up $15  
Squirt $15  
Pepsi $15  
Cocacola $16  

BOING  245 ml  
uva $20  
Fresa $20  
Mango $20  
Guayaba $20  

Refresco 600 ml  
Coca-cola  $27  
Pepsi $27  
Manzanita $27  
Fanta $27  
7up $27  
Squirt $27  

---

# 🚀 FUNCIONALIDADES DEL SISTEMA

## 🔹 Datos del Cliente
- Campo obligatorio: Nombre
- Selección de tipo de entrega:
  - Pickup
  - Delivery
- Si selecciona Delivery, la dirección exacta es obligatoria.

---

## 🔹 Selección de Cantidades
El cliente puede seleccionar número de piezas para:

- Burgers
- Promo Smash
- Jochos
- Promo Jochos

---

## 🔹 Wings
- Selección de presentación (10, 18 o 28 piezas)
- Selección libre de sabores disponibles

---

## 🔹 Boneless
- Selección de presentación (10, 18 o 28 piezas)
- Selección libre de sabores disponibles

---

## 🔹 Método de Pago
- Efectivo
- Transferencia

---

# 🧮 CÁLCULO AUTOMÁTICO

El sistema:

- Calcula automáticamente el total en tiempo real.
- Suma productos según cantidad seleccionada.
- Suma Wings y Boneless según presentación elegida.
- Muestra el total en pantalla.
- Inserta el total dentro del mensaje final de WhatsApp.

---

# 📲 GENERACIÓN AUTOMÁTICA DE PEDIDO

Al presionar **"Enviar Pedido por WhatsApp"**, el sistema:

1. Valida campos obligatorios.
2. Genera mensaje formateado con:
   - Nombre
   - Tipo de entrega
   - Dirección (si aplica)
   - Total
   - Método de pago
3. Abre WhatsApp con el pedido listo para enviar.

---

# ⚙️ CONFIGURACIÓN

Dentro del archivo `index.html` debes configurar el número:

```javascript
const telefono = "5219903667103";
