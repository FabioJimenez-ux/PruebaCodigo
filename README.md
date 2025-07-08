<!DOCTYPE html>
<html>
<head>
  <title>Perfil de usuario</title>
</head>
<body>
  <h1>Bienvenido</h1>

  <!-- Supongamos que este valor viene de la URL o de un formulario sin validación -->
  <p>Tu nombre es: <span id="nombre"></span></p>

  <script>
    // Simula que el nombre viene de la URL: ?nombre=<script>alert('XSS')</script>
    const params = new URLSearchParams(window.location.search);
    const nombre = params.get("nombre");

    // ❌ Inseguro: inserta directamente el valor en el DOM sin sanitizar
