# 🧾 **Guía básica de Formularios en HTML**

## 📘 ¿Qué es un formulario en HTML?

Un **formulario** es una parte de una página web que permite al usuario **introducir datos** y **enviarlos** al servidor o procesarlos con JavaScript.
Se usa para recopilar información como nombres, correos, contraseñas, opiniones o archivos.

👉 En resumen: **un formulario conecta al usuario con la web.**

---

## 🧩 **Estructura básica**

Un formulario se define con la etiqueta `<form>` y dentro de ella se colocan los **campos** (inputs, select, textarea, etc.).

```html
<form action="procesar.php" method="post">
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre">

  <input type="submit" value="Enviar">
</form>
```

### 🔍 Atributos principales de `<form>`:

* **`action`** → URL donde se envían los datos.
* **`method`** → Cómo se envían los datos:

  * `get` → los datos van en la URL (visible).
  * `post` → los datos se envían ocultos (más seguro).
* **`enctype`** → tipo de codificación (por ejemplo, `multipart/form-data` para subir archivos).

---

## 🧱 **Etiquetas principales**

| Etiqueta     | Descripción                                               | Ejemplo                                          |
| ------------ | --------------------------------------------------------- | ------------------------------------------------ |
| `<input>`    | Campo de entrada (texto, número, email, contraseña, etc.) | `<input type="text" name="usuario">`             |
| `<label>`    | Texto asociado a un campo. Mejora la accesibilidad.       | `<label for="usuario">Usuario:</label>`          |
| `<textarea>` | Campo de texto largo (varias líneas).                     | `<textarea name="comentario"></textarea>`        |
| `<select>`   | Lista desplegable.                                        | `<select><option>Opción 1</option></select>`     |
| `<option>`   | Elemento dentro de un `<select>`.                         | `<option value="1">Uno</option>`                 |
| `<button>`   | Botón que puede enviar o ejecutar scripts.                | `<button type="submit">Enviar</button>`          |
| `<fieldset>` | Agrupa campos relacionados.                               | `<fieldset><legend>Datos</legend>...</fieldset>` |
| `<legend>`   | Título del grupo dentro del `<fieldset>`.                 | `<legend>Datos personales</legend>`              |

---

## ⚙️ **Tipos comunes de `<input>`**

| Tipo       | Uso                       | Ejemplo                                                   |
| ---------- | ------------------------- | --------------------------------------------------------- |
| `text`     | Texto corto               | `<input type="text" name="nombre">`                       |
| `password` | Contraseña oculta         | `<input type="password" name="clave">`                    |
| `email`    | Correo electrónico        | `<input type="email" name="correo">`                      |
| `number`   | Números                   | `<input type="number" name="edad">`                       |
| `date`     | Fecha                     | `<input type="date" name="nacimiento">`                   |
| `radio`    | Opción única entre varias | `<input type="radio" name="sexo" value="M">`              |
| `checkbox` | Opción múltiple           | `<input type="checkbox" name="intereses" value="musica">` |
| `file`     | Subir archivo             | `<input type="file" name="foto">`                         |
| `submit`   | Enviar formulario         | `<input type="submit" value="Enviar">`                    |
| `reset`    | Reiniciar los campos      | `<input type="reset" value="Borrar">`                     |

---

## 💡 **Ejemplo completo**

```html
<form action="/enviar" method="post">
  <fieldset>
    <legend>Datos personales</legend>

    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required><br><br>

    <label for="email">Correo:</label>
    <input type="email" id="email" name="email"><br><br>

    <label>Género:</label>
    <input type="radio" name="genero" value="M"> Hombre
    <input type="radio" name="genero" value="F"> Mujer<br><br>

    <label>Intereses:</label>
    <input type="checkbox" name="intereses" value="deporte"> Deporte
    <input type="checkbox" name="intereses" value="musica"> Música<br><br>

    <label for="comentarios">Comentarios:</label><br>
    <textarea id="comentarios" name="comentarios" rows="4" cols="40"></textarea><br><br>

    <input type="submit" value="Enviar">
  </fieldset>
</form>
```

---

## 🧠 **Resumen final**

| Concepto              | Descripción                                      |
| --------------------- | ------------------------------------------------ |
| **Formulario**        | Estructura para introducir y enviar datos.       |
| **Campos**            | Elementos donde el usuario escribe o selecciona. |
| **Método GET/POST**   | Forma en que se envían los datos.                |
| **Etiqueta `<form>`** | Contenedor principal del formulario.             |

---

