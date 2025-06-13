¡Entendido! Aquí tienes un resumen conciso de los selectores CSS y un único documento HTML/CSS que los combina y demuestra en acción. Esto será muy práctico para tus alumnos.

---

## Guía Rápida: Los Selectores CSS Esenciales

Los **selectores CSS** son como las "direcciones" que le damos a CSS para decirle exactamente a qué elemento o grupo de elementos HTML debe aplicar un estilo. Sin ellos, CSS no sabría dónde actuar.

Aquí están los más importantes:

* **Selector Universal (`*`):** Selecciona **todos** los elementos HTML en la página. Útil para estilos muy generales.
* **Selector de Tipo (o Etiqueta):** Selecciona todos los elementos de un **tipo específico** (ej., `p` para todos los párrafos, `h1` para todos los títulos H1).
* **Selector de Clase (`.nombre-clase`):** Selecciona todos los elementos que tienen el atributo `class` con ese **nombre**. Es muy versátil, permite aplicar el mismo estilo a varios elementos, incluso de distinto tipo.
* **Selector de ID (`#nombre-id`):** Selecciona **un único elemento** con un `id` específico. El `id` debe ser único en toda la página.
* **Selectores de Atributo (`[atributo]`, `[atributo="valor"]`, etc.):** Seleccionan elementos basándose en la **presencia** de un atributo HTML o en el **valor** de ese atributo.
* **Combinación de Selectores:**
    * **Descendente (`padre descendiente`):** Selecciona un elemento que está **dentro** de otro (no importa cuán profundo). Por ejemplo, `div p` selecciona todos los párrafos dentro de un `div`.
    * **Hijo Directo (`padre > hijo`):** Selecciona un elemento que es **hijo directo** de otro. Por ejemplo, `ul > li` selecciona solo los `li` que son hijos directos de un `ul`.

---

## Ejemplo Completo: Todos los Selectores en Acción

Este documento HTML contiene un `style` con CSS que utiliza todos los selectores explicados. Invita a tus alumnos a inspeccionar el código y a ver cómo cada regla de estilo afecta a los elementos en la página.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demostración de Selectores CSS</title>
    <style>
        /* --- 1. Selector Universal (*) --- */
        * {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            box-sizing: border-box; /* Asegura que padding y border se incluyan en el ancho/alto */
            margin: 0;
            padding: 0;
        }

        body {
            padding: 20px;
            background-color: #f4f4f4;
            color: #333;
        }

        /* --- 2. Selector de Tipo (Etiqueta) --- */
        h1 {
            color: #2c3e50;
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 2px solid #ddd;
            padding-bottom: 10px;
        }

        p {
            font-size: 16px;
            line-height: 1.5;
            margin-bottom: 15px;
        }

        button {
            background-color: #3498db;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 15px;
            margin-right: 10px;
        }

        /* --- 3. Selector de Clase (.nombre-clase) --- */
        .contenedor {
            background-color: white;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .texto-rojo {
            color: red;
            font-weight: bold;
        }

        .destacado {
            background-color: #f1c40f; /* Amarillo */
            padding: 3px 6px;
            border-radius: 3px;
        }

        /* --- 4. Selector de ID (#nombre-id) --- */
        #seccion-principal {
            background-color: #e8f6f3; /* Verde agua muy claro */
            border: 2px solid #2ecc71; /* Verde esmeralda */
            padding: 30px;
            text-align: center;
            margin-bottom: 30px;
        }

        #pie-pagina {
            font-size: 14px;
            color: #7f8c8d;
            text-align: center;
            margin-top: 40px;
            border-top: 1px solid #eee;
            padding-top: 15px;
        }

        /* --- 5. Selectores de Atributo ([atributo], [atributo="valor"], etc.) --- */
        /* Elementos con el atributo 'data-info' */
        [data-info] {
            border: 1px dashed #9b59b6; /* Púrpura */
            padding: 5px;
            margin-top: 10px;
        }

        /* Enlaces que abren en una nueva pestaña */
        a[target="_blank"] {
            color: #e74c3c; /* Rojo */
            text-decoration: none;
            font-weight: bold;
        }

        /* Campos de texto (input type="text") */
        input[type="text"] {
            border: 1px solid #ccc;
            padding: 8px;
            border-radius: 4px;
            width: 200px;
        }

        /* --- 6. Combinación de Selectores --- */
        /* a. Selector Descendente (Espacio ' ') */
        .contenedor p { /* Selecciona todos los <p> que están DENTRO de un elemento con clase 'contenedor' */
            font-style: italic;
            color: #2c3e50;
        }

        /* b. Selector de Hijo Directo ('>') */
        ul > li { /* Selecciona solo los <li> que son HIJOS DIRECTOS de un <ul> */
            list-style-type: disc; /* Un disco como viñeta */
            color: #2980b9; /* Azul */
            margin-left: 20px;
        }

        ul li { /* Este afectaría a TODOS los li, incluso si están anidados más profundo */
            padding: 2px 0;
        }
    </style>
</head>
<body>
    <h1>Demostración de Selectores CSS</h1>

    <div id="seccion-principal">
        <p>Esta es la **sección principal** de la página. Está estilizada por su **ID** (`#seccion-principal`).</p>
        <p class="texto-rojo">Este párrafo es rojo por su **clase** (`.texto-rojo`).</p>
        <button>Botón Principal</button>
        <button data-info="más detalles">Otro Botón con Atributo</button>
    </div>

    <div class="contenedor">
        <h2>Contenedor General (clase `.contenedor`)</h2>
        <p>Este es un párrafo dentro del contenedor. Observa cómo su estilo (**descendente**: `.contenedor p`) es diferente.</p>
        <ul>
            <li>Elemento de lista 1 (hijo directo de `ul`)</li>
            <li>Elemento de lista 2 (hijo directo de `ul`)
                <ul>
                    <li>Sub-elemento de lista (NO es hijo directo del primer `ul`)</li>
                </ul>
            </li>
        </ul>
        <p>
            Aquí hay un texto <span class="destacado">destacado</span> por su **clase** (`.destacado`).
        </p>
        <p data-info="informacion adicional">
            Este párrafo tiene un **atributo `data-info`** (`[data-info]`) que le da un borde púrpura.
        </p>
    </div>

    <div class="contenedor">
        <h2>Otro Contenedor</h2>
        <p>Otro párrafo en un contenedor, con los mismos estilos descendentes.</p>
        <a href="https://www.w3schools.com" target="_blank">Visita W3Schools (abre en nueva pestaña)</a>
        <br><br>
        <a href="https://developer.mozilla.org/es/" >Visita MDN (enlace normal)</a>
        <br><br>
        <label for="campoTexto">Escribe aquí:</label>
        <input type="text" id="campoTexto" placeholder="Ejemplo de input">
    </div>

    <footer id="pie-pagina">
        <p>Este es el pie de página, estilizado por su **ID** (`#pie-pagina`).</p>
    </footer>

    <p>
        ¡Recuerda que el **selector universal** (`*`) aplicó un margen y padding a <em>todos</em> los elementos al inicio!
    </p>

</body>
</html>
```