## Guía Rápida: Pseudoselectores y Pseudoelementos CSS

Más allá de los selectores básicos que eligen elementos completos, CSS nos permite seleccionar partes *específicas* de un elemento o elementos en un *estado particular*. Aquí es donde entran los **pseudoselectores** (también conocidos como pseudoclases) y **pseudoelementos**.

Imagina que quieres que un botón cambie de color cuando el ratón pasa por encima, o que el primer párrafo de cada sección tenga un estilo diferente, o incluso añadir texto o un icono antes de un elemento sin modificar el HTML. ¡Para eso sirven!

---

### Pseudoselectores (Pseudoclases) - `:` (Un solo dos puntos)

Los pseudoselectores (`:`) seleccionan un elemento basándose en su **estado**, su **posición** dentro de su "familia" de elementos, o alguna otra característica que no se puede expresar con un selector normal.

1.  **Pseudoselectores de Estado (Interacción del Usuario):**
    * **`:hover`**: Selecciona un elemento cuando el **ratón está sobre él**.
    * **`:active`**: Selecciona un elemento cuando está siendo **activado** (haciendo clic en un botón, por ejemplo).
    * **`:focus`**: Selecciona un elemento cuando está **enfocado** (por ejemplo, al hacer clic en un campo de texto o al navegar con el teclado).
    * **`:visited`**: Selecciona un enlace (`<a>`) que el usuario ya **ha visitado**.
    * **`:link`**: Selecciona un enlace (`<a>`) que el usuario **aún no ha visitado** (estado por defecto).

2.  **Pseudoselectores Estructurales (Posición o Tipo):**
    * **`:first-child`**: Selecciona el elemento que es el **primer hijo** de su elemento padre.
    * **`:last-child`**: Selecciona el elemento que es el **último hijo** de su elemento padre.
    * **`:nth-child(n)`**: Selecciona el **hijo número `n`** de su elemento padre. `n` puede ser un número (`2`), una palabra clave (`even` para pares, `odd` para impares) o una fórmula (`2n` para cada segundo elemento, `3n+1` para cada tercer elemento a partir del primero).
    * **`:first-of-type`**: Selecciona el primer elemento de un **tipo específico** dentro de su padre (ej., el primer `p` dentro de un `div`).
    * **`:last-of-type`**: Selecciona el último elemento de un **tipo específico** dentro de su padre.
    * **`:nth-of-type(n)`**: Selecciona el enésimo elemento de un **tipo específico** dentro de su padre.
    * **`:not(selector)`**: Selecciona todos los elementos que **NO** coinciden con el selector especificado entre paréntesis.

---

### Pseudoelementos - `::` (Dos dos puntos)

Los pseudoelementos (`::`) permiten estilizar **partes específicas de un elemento** o **insertar contenido** antes o después de un elemento sin añadir HTML real.

1.  **`::before`**: Inserta **contenido virtual antes** del contenido de un elemento. Se usa casi siempre junto con la propiedad `content`.
2.  **`::after`**: Inserta **contenido virtual después** del contenido de un elemento. También requiere la propiedad `content`.
3.  **`::first-line`**: Estiliza la **primera línea de un bloque de texto**.
4.  **`::first-letter`**: Estiliza la **primera letra de un bloque de texto**.
5.  **`::selection`**: Estiliza el texto que el usuario ha **seleccionado/resaltado** con el ratón.

---

## Ejemplo Genérico: Pseudoselectores y Pseudoelementos en Acción

Este documento HTML demuestra el uso de los pseudoselectores y pseudoelementos más comunes. Anime a sus alumnos a interactuar con los elementos (pasar el ratón, hacer clic, seleccionar texto) para ver los efectos.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demostración de Pseudoselectores y Pseudoelementos</title>
    <style>
        body {
            font-family: 'Open Sans', Arial, sans-serif;
            background-color: #f8f9fa;
            color: #343a40;
            padding: 20px;
            margin: 0;
            line-height: 1.6;
        }

        h1, h2 {
            color: #0056b3;
            margin-bottom: 15px;
            border-bottom: 1px solid #dee2e6;
            padding-bottom: 5px;
        }

        section {
            background-color: white;
            padding: 20px;
            margin-bottom: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        /* --- Pseudoselectores de Estado (Interacción) --- */

        .interactividad button {
            background-color: #007bff;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease; /* Transición suave para el hover */
            margin-right: 10px;
        }

        .interactividad button:hover { /* Cuando el ratón está sobre el botón */
            background-color: #0056b3;
            transform: scale(1.02); /* Ligeramente más grande */
        }

        .interactividad button:active { /* Cuando se hace clic en el botón */
            background-color: #004085;
            transform: scale(0.98);
        }

        .interactividad input[type="text"] {
            padding: 8px;
            border: 2px solid #ccc;
            border-radius: 4px;
            outline: none; /* Elimina el contorno azul por defecto del navegador */
            transition: border-color 0.3s ease;
        }

        .interactividad input[type="text"]:focus { /* Cuando el campo de texto está enfocado */
            border-color: #28a745; /* Borde verde */
            box-shadow: 0 0 5px rgba(40, 167, 69, 0.5);
        }

        .interactividad a {
            color: #17a2b8; /* Azul claro para enlaces no visitados */
            text-decoration: none;
            margin-right: 15px;
        }

        .interactividad a:visited { /* Cuando el enlace ya ha sido visitado */
            color: #6610f2; /* Púrpura */
        }

        .interactividad a:hover {
            text-decoration: underline;
        }

        /* --- Pseudoselectores Estructurales --- */

        .lista-estructural ul {
            list-style: none; /* Quitamos viñetas por defecto */
            padding: 0;
        }

        .lista-estructural li {
            background-color: #e9ecef;
            margin-bottom: 5px;
            padding: 8px 12px;
            border-radius: 4px;
        }

        .lista-estructural li:first-child { /* El primer elemento de la lista */
            font-weight: bold;
            background-color: #ffe0b2; /* Naranja claro */
        }

        .lista-estructural li:last-child { /* El último elemento de la lista */
            font-style: italic;
            background-color: #c8e6c9; /* Verde claro */
        }

        .lista-estructural li:nth-child(even) { /* Elementos pares (2º, 4º, etc.) */
            background-color: #d4edda; /* Verde pastel */
        }

        .lista-estructural li:nth-child(odd) { /* Elementos impares (1º, 3º, etc.) */
            background-color: #f8d7da; /* Rojo pastel */
        }

        .lista-estructural p:first-of-type { /* El primer párrafo dentro de su padre (.lista-estructural) */
            text-decoration: underline;
            color: #dc3545; /* Rojo */
        }

        .lista-estructural div:not(.excluir) { /* Divs que NO tienen la clase 'excluir' */
            border: 2px dashed #6f42c1; /* Púrpura oscuro */
            padding: 10px;
            margin-top: 15px;
        }

        /* --- Pseudoelementos --- */

        .texto-pseudoelementos p::first-line { /* La primera línea de este párrafo */
            font-weight: bold;
            color: #007bff;
        }

        .texto-pseudoelementos p::first-letter { /* La primera letra de este párrafo */
            font-size: 2em; /* Doble tamaño */
            color: #fd7e14; /* Naranja */
            margin-right: 5px;
            float: left; /* Para que la letra inicial quede flotando */
            line-height: 1;
        }

        .texto-pseudoelementos .icono::before { /* Inserta un icono antes del elemento con clase 'icono' */
            content: "💡 "; /* El contenido a insertar */
            color: #ffc107; /* Amarillo */
        }

        .texto-pseudoelementos .cita::after { /* Inserta comillas al final de la cita */
            content: "”";
            font-size: 1.5em;
            color: #6c757d;
            margin-left: 5px;
        }
        .texto-pseudoelementos .cita::before { /* Inserta comillas al inicio de la cita */
            content: "“";
            font-size: 1.5em;
            color: #6c757d;
            margin-right: 5px;
        }

        /* Estilo para el texto seleccionado */
        ::selection {
            background-color: #28a745; /* Verde para el fondo */
            color: white;             /* Blanco para el texto */
        }
    </style>
</head>
<body>
    <h1>Pseudoselectores y Pseudoelementos CSS</h1>

    <section class="interactividad">
        <h2>1. Pseudoselectores de Estado (Interacción)</h2>
        <p>Pasa el ratón, haz clic y enfoca los elementos de abajo para ver los cambios de estilo.</p>
        <button>Botón Interactivo</button>
        <input type="text" placeholder="Haz clic aquí para enfocar">
        <br><br>
        <a href="https://example.com/pagina-no-visitada">Enlace no visitado</a>
        <a href="https://google.com">Enlace a Google (visitado probablemente)</a>
    </section>

    <section class="lista-estructural">
        <h2>2. Pseudoselectores Estructurales</h2>
        <p>Este es el primer párrafo de esta sección. Es un ejemplo de `:first-of-type`.</p>
        <p>Este es el segundo párrafo.</p>
        <div>
            Este es un `div` que NO tiene la clase `excluir`.
            <p>Otro párrafo dentro del div.</p>
        </div>
        <div class="excluir">
            Este es un `div` con la clase `excluir`. El selector `:not(.excluir)` NO lo afectará.
        </div>
        <h3>Elementos de Lista:</h3>
        <ul>
            <li>Primer elemento (<code>:first-child</code> / <code>:nth-child(odd)</code>)</li>
            <li>Segundo elemento (<code>:nth-child(even)</code>)</li>
            <li>Tercer elemento (<code>:nth-child(odd)</code>)</li>
            <li>Cuarto elemento (<code>:nth-child(even)</code>)
                <ul>
                    <li>Sub-elemento de lista (NO afectado por `ul > li`)</li>
                    <li>Otro sub-elemento</li>
                </ul>
            </li>
            <li>Último elemento (<code>:last-child</code> / <code>:nth-child(odd)</code>)</li>
        </ul>
    </section>

    <section class="texto-pseudoelementos">
        <h2>3. Pseudoelementos</h2>
        <p>
            Este es un párrafo de texto largo para demostrar <code>::first-line</code> y <code>::first-letter</code>. La primera línea y la primera letra deberían tener un estilo diferente. Experimenta cambiando el tamaño de la ventana para ver cómo la "primera línea" cambia dinámicamente.
        </p>
        <p class="icono">Este texto tiene un icono de bombilla antes de él usando `::before`.</p>
        <p class="cita">La creatividad es la inteligencia divirtiéndose.</p>
        <p>
            Intenta **seleccionar este texto con el ratón**. El color del resaltado debería ser diferente gracias a <code>::selection</code>.
        </p>
    </section>

    <p style="text-align: center; margin-top: 30px; font-size: 0.9em; color: #6c757d;">
        Los pseudoselectores y pseudoelementos son herramientas muy poderosas para añadir dinamismo y estilo a tus páginas sin modificar la estructura HTML.
    </p>
</body>
</html>
```