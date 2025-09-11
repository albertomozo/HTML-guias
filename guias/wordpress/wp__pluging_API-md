## 🔹 Plugins para mostrar datos de API/JSON en WordPress

### 1. **WPGetAPI**

* Permite conectar tu WordPress con **cualquier API REST**.
* Configuras la URL, parámetros y cabeceras en el panel de WP.
* Puedes mostrar los datos con **shortcodes** o bloques.
  👉 Muy útil si quieres leer un JSON desde una API externa.

🔗 [WPGetAPI](https://wordpress.org/plugins/wpgetapi/)

---

### 2. **WP All Import** (y su complemento JSON/XML)

* Está pensado para **importar datos** en WordPress desde ficheros JSON o XML.
* Puedes traer productos, posts, usuarios, etc. desde un archivo.
* Ideal si quieres **importar un JSON a entradas/páginas** y luego gestionarlo como contenido normal.

🔗 [WP All Import](https://www.wpallimport.com/)

---

### 3. **WP REST API Controller**

* Si lo que quieres es **exponer tu JSON** (hacer que tu web sirva datos como API).
* Permite activar y desactivar endpoints sin programar.

🔗 [WP REST API Controller](https://wordpress.org/plugins/wp-rest-api-controller/)

---

### 4. **Advanced Custom Fields (ACF) + ACF to REST API**

* Con **ACF** puedes crear campos personalizados.
* Con el add-on **ACF to REST API** puedes consumirlos o exportarlos en JSON sin tocar código.

---

### 5. **Visualizer** o **WPDataTables**

* Si tu JSON tiene estructura tabular (ej. listas de usuarios, precios, estadísticas), estos plugins convierten el JSON en **tablas y gráficos**.
* Muy prácticos para mostrar datos directamente sin programar.

---

✅ En resumen:

* **Mostrar datos dinámicos desde APIs externas → WPGetAPI.**
* **Importar JSON a contenido (entradas, productos) → WP All Import.**
* **Mostrar en tablas/gráficos → Visualizer o WPDataTables.**

---

# ejemplo  **WPGetAPI** 

## 🔹 Paso 1: Instalar WPGetAPI

1. Entra en tu WordPress → **Plugins → Añadir nuevo**.
2. Busca **WPGetAPI**.
3. Instálalo y actívalo.

---

## 🔹 Paso 2: Configurar la API

1. Ve al menú lateral **WPGetAPI → Endpoints**.
2. Crea una nueva **API** (ejemplo: `UsuariosAPI`).
3. Configura:

   * **Base URL:** `https://jsonplaceholder.typicode.com/`
   * **Endpoint:** `users`
   * **Método:** `GET`
   * El resto lo puedes dejar por defecto.

👉 Esto hará que WordPress sepa que debe pedir la lista de usuarios.

---

## 🔹 Paso 3: Mostrar los datos en una página

Ahora puedes usar un **shortcode** en cualquier entrada o página:

```php
[wpgetapi_endpoint api_id="UsuariosAPI" endpoint_id="users"]
```

Esto mostrará directamente el JSON crudo.

---

## 🔹 Paso 4: Formatear los datos (ejemplo de nombres y emails)

Si quieres algo más bonito, WPGetAPI Pro (de pago) trae opciones para **mapeo y plantillas**.
Pero con la versión gratuita puedes combinarlo con un poco de **JavaScript en el editor de bloques HTML**:

```html
<div id="usuarios"></div>

<script>
fetch("https://jsonplaceholder.typicode.com/users")
  .then(res => res.json())
  .then(data => {
    let salida = "<ul>";
    data.forEach(u => {
      salida += `<li><strong>${u.name}</strong> - ${u.email}</li>`;
    });
    salida += "</ul>";
    document.getElementById("usuarios").innerHTML = salida;
  });
</script>
```

---

✅ Con esto tienes dos formas:

* **Solo plugin (más rápido):** shortcode `[wpgetapi_endpoint ...]` → muestra el JSON en crudo.
* **Plugin + HTML/JS:** haces una lista más amigable para el visitante.

---

👉 ¿Quieres que te prepare un ejemplo con WPGetAPI mostrando **una tabla ordenada de usuarios** (con nombre, email y ciudad) en vez de solo el JSON plano?

