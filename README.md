# 🛒 Tienda Estilo Mercado Libre - PHP + MySQL + Mercado Pago

Este proyecto es una tienda web responsive hecha con **PHP**, **HTML/CSS** y **MySQL**, que simula el estilo de **Mercado Libre Argentina**. Cuenta con:

- Carrito de compras funcional
- Visualización de productos desde base de datos
- Formulario de finalización de compra
- Integración con **Mercado Pago Checkout Pro** (modo test)

---

## 🔧 Tecnologías utilizadas

- PHP 7.x
- MySQL
- HTML5 + CSS3
- Mercado Pago SDK (integración sin Composer)

---

## 📁 Estructura del proyecto

/tienda_mercado_pago
├── index.php # Página principal con productos
├── carrito.php # Vista del carrito de compras
├── finalizar_compra.php # Genera el botón de pago con Mercado Pago
├── gracias.php # Página de confirmación post-pago
├── conexion.php # Conexión a la base de datos
├── /mercadopago-sdk/ # SDK de Mercado Pago (si no usás Composer)
└── README.md # Este archivo

sql
Copiar
Editar

---

## 📦 Instalación

1. Cloná este repositorio o descargá el ZIP del proyecto y extraelo en tu servidor local (`htdocs` si usás XAMPP).

2. Creá la base de datos MySQL:

sql
CREATE DATABASE tienda;
USE tienda;

CREATE TABLE productos (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nombre VARCHAR(255),
  precio DECIMAL(10,2)
);

INSERT INTO productos (nombre, precio) VALUES
('Notebook Lenovo i5', 450000),
('Zapatillas Nike Air', 95000),
('Auriculares Bluetooth', 19999),
('Samsung Galaxy A34', 230000);
Asegurate de que el archivo conexion.php tenga tu configuración correcta:

php
Copiar
Editar
$conexion = new mysqli("localhost", "root", "", "tienda");
Configurá tu token de prueba de Mercado Pago en finalizar_compra.php:

php
Copiar
Editar
MercadoPago\SDK::setAccessToken("TEST-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx");
Obtené el token desde: https://www.mercadopago.com.ar/developers/panel

Si no usás Composer, asegurate de tener la carpeta mercadopago-sdk/ incluida (descargada desde el repositorio oficial).

🧪 Modo de prueba
Podés usar los datos de tarjetas de prueba de Mercado Pago:
👉 https://www.mercadopago.com.ar/developers/es/docs/checkout-pro/test-cards

🚀 Características

🛒 Agregar productos al carrito

💵 Calcular el total

🧾 Formulario con datos del comprador

🔗 Redirección a Checkout Pro (sandbox)

✅ Página de éxito al finalizar el pago

✨ Funcionalidades futuras (sugeridas)
Registro e inicio de sesión de usuarios

Guardar pedidos en una tabla ventas

Envío automático de confirmación por correo

Soporte para cantidades por producto



🧑‍💻 Autores del Proyecto:

  Roman Quiroga, Joaquin Marek, Camila gonzalez

Si querés colaborar o hacer mejoras, ¡bienvenido!
