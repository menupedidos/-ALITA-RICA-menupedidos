# 🍔🔥 ALITA RICA – SABOR DE BARRIO AL CARBÓN

Sistema de menú digital interactivo con cálculo automático de total y generación directa de pedidos vía WhatsApp.

Diseñado para optimizar la toma de pedidos, reducir errores y agilizar el proceso de venta desde cualquier dispositivo móvil.

---

## 🚀 Características del Sistema

- Campo obligatorio para nombre del cliente
- Selección de tipo de entrega: Pickup o Delivery
- Dirección obligatoria si se selecciona Delivery
- Ingreso manual de cantidades para:
  - Hamburguesas
  - Promo Smash
  - Jochos
  - Promo Jochos
- Selección de presentación para Wings
- Selección de hasta 3 sabores para Wings
- Selección de presentación para Boneless
- Selección de hasta 3 sabores para Boneless
- Método de pago (Efectivo o Transferencia)
- Cálculo automático del total en tiempo real
- Total agregado automáticamente al mensaje final
- Generación automática del pedido listo para enviar por WhatsApp
- Diseño limpio, moderno y 100% adaptable a celular

---

## 📋 Menú Oficial

### 🍔 Hamburguesas (Incluyen papas)

- Burger clásica — $109  
- Doble bacón — $129  
- Champiburger — $145  
- Hawaianburger — $145  
- Cachitoburger — $165  

🔥 Promo Smash sencilla (3 piezas sin papas) — $99  

---

### 🍗 Wings

- 10 piezas — $139  
- 18 piezas — $229  
- 28 piezas — $329  

*Permite seleccionar hasta 3 sabores.*

---

### 🍗 Boneless

- 10 piezas — $139  
- 18 piezas — $239  
- 28 piezas — $339  

*Permite seleccionar hasta 3 sabores.*

---

### 🌭 Jochos

- Jocho clásico — $35  
- Jocho hawaiano — $45  
- Jocho champi — $45  
- Cachitojocho — $60  

🔥 PromoJocho sencillo (2 piezas) — $60  

---

## 🧮 Sistema de Cálculo

El sistema:

- Multiplica automáticamente cada producto por su precio unitario.
- Suma Wings y Boneless según la presentación seleccionada.
- Actualiza el total en tiempo real.
- Inserta el total automáticamente dentro del mensaje de WhatsApp.

---

## 📲 Flujo del Pedido

1. El cliente completa los campos obligatorios.
2. Selecciona productos y cantidades.
3. El sistema calcula el total automáticamente.
4. Al presionar “Enviar Pedido”, se abre WhatsApp con:
   - Nombre del cliente
   - Tipo de entrega
   - Dirección (si aplica)
   - Resumen del pedido
   - Total final
   - Método de pago

El mensaje queda listo para enviarse.

---

## ⚙️ Configuración del Número de WhatsApp

Dentro del archivo `index.html`, ubica la siguiente línea:

```javascript
const telefono = "5219903667103";
