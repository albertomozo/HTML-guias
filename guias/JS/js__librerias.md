## 📌 ¿Qué son las librerías externas de JavaScript?

Una **librería externa de JavaScript** es un conjunto de funciones y utilidades ya programadas que alguien ha creado y compartido para que otros desarrolladores las usen en sus proyectos.

En lugar de programar desde cero, puedes **reutilizar código probado y optimizado**.
👉 Ejemplo: en lugar de programar tu propio sistema de animaciones, puedes usar **GSAP** o **Anime.js**.

---

## 📌 ¿Por qué usarlas?

* **Ahorro de tiempo** → no reinventas la rueda.
* **Código optimizado** → suelen estar bien probadas.
* **Más funcionalidades** → puedes añadir efectos, gráficos, validaciones, etc.
* **Comunidad activa** → actualizaciones y soporte.

---

## 📌 ¿Cómo se instalan y funcionan habitualmente?

### 🔹 1. **Incluyendo un archivo `<script>` desde una CDN**

La forma más sencilla, ideal para principiantes.
Ejemplo con **Anime.js** desde un CDN:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Ejemplo con Anime.js</title>
</head>
<body>
  <h1 id="titulo">Hola Mundo</h1>

  <!-- Incluir la librería desde un CDN -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>

  <script>
    // Usar la librería
    anime({
      targets: '#titulo',
      translateX: 250,
      duration: 2000
    });
  </script>
</body>
</html>
```

👉 Solo necesitas copiar el `<script>` de la librería y luego ya puedes usar sus funciones.

---

### 🔹 2. **Descargando el archivo .js**

* Descargas el archivo `.js` de la librería.
* Lo guardas en una carpeta (ej. `js/`).
* Lo incluyes con `<script src="js/libreria.js"></script>`.

---

### 🔹 3. **Usando un gestor de paquetes (npm/yarn)**

Más usado en proyectos grandes.
Ejemplo con **Axios** (para llamadas HTTP):

```bash
npm install axios
```

Luego en tu archivo JS:

```js
import axios from 'axios';

axios.get('https://api.example.com/datos')
  .then(res => console.log(res.data));
```

---

## 📌 Resumen del funcionamiento

1. **Importar la librería** (CDN, descarga o npm).
2. **Consultar la documentación** para ver qué funciones ofrece.
3. **Usar sus métodos y clases** en tu propio código.

---

🔹 *“Las librerías JS son como cajas de herramientas que añadimos a nuestro proyecto. No tenemos que fabricar el martillo: simplemente lo usamos”*.


