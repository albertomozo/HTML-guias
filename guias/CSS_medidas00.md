##  Medidas en HTML/CSS

Cuando construimos una página web, necesitamos decirle al navegador qué tamaño deben tener las cosas (imágenes, textos, cuadros, etc.) y dónde deben ir. Para eso usamos las "medidas". Imagina que estás construyendo con LEGOs: necesitas saber si una pieza es grande o pequeña, o si debe ir a la izquierda o a la derecha de otra. En HTML y CSS, las medidas nos ayudan a hacer lo mismo.

Hay dos grandes grupos de medidas:

1.  **Medidas Absolutas:** Son como usar una regla normal. Si dices que algo mide 10 centímetros, siempre medirá 10 centímetros, no importa dónde lo mires. Son muy precisas, pero a veces no se adaptan bien a diferentes pantallas (por ejemplo, un móvil o un ordenador grande).
2.  **Medidas Relativas:** Son como decir "la mitad de la mesa" o "el doble de la silla". Su valor depende de otra cosa. Son muy flexibles y se adaptan genial a diferentes tamaños de pantalla, lo que es crucial hoy en día.

Vamos a ver las más importantes:

### Medidas Absolutas

#### 1. `px` (Píxeles)

* **¿Qué es?** Un píxel es la unidad más pequeña de color en una pantalla. Es como un puntito.
* **¿Cuándo usarlo?** Cuando necesitas un control muy exacto y el tamaño no debe cambiar. Es muy común para bordes, sombras, o para asegurar que un elemento tenga un tamaño mínimo.
* **Ejemplo:** Si dices que un texto mide `16px`, siempre tendrá ese tamaño en cualquier pantalla, aunque el usuario esté en un móvil y el texto se vea muy grande comparado con el resto.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas en Píxeles (px)</title>
    <style>
        .caja-pixel {
            width: 200px; /* 200 píxeles de ancho */
            height: 100px; /* 100 píxeles de alto */
            background-color: lightblue;
            border: 2px solid darkblue;
            margin-bottom: 10px;
            padding: 10px;
            font-size: 18px; /* 18 píxeles de tamaño de fuente */
        }
        .texto-pixel {
            font-size: 14px; /* Otro texto con 14 píxeles */
        }
    </style>
</head>
<body>
    <h1>Ejemplo de Medidas en Píxeles (`px`)</h1>

    <div class="caja-pixel">
        <p>Esta caja tiene un ancho de 200px y un alto de 100px. Su texto tiene 18px.</p>
    </div>

    <p class="texto-pixel">Este es otro párrafo con un tamaño de fuente de 14px.</p>

    <p>Observa que, sin importar el tamaño de tu navegador, estas medidas se mantendrán fijas.</p>
</body>
</html>
```

### Medidas Relativas

#### 2. `%` (Porcentaje)

* **¿Qué es?** El porcentaje es una medida relativa al tamaño de su *elemento padre* (el elemento que lo contiene). Si un elemento está dentro de otro, su porcentaje se calcula en base al tamaño de ese "padre".
* **¿Cuándo usarlo?** ¡Muy útil para diseños "responsive" (que se adaptan a diferentes pantallas)! Si quieres que algo ocupe "la mitad" del espacio disponible, usa porcentajes.
* **Ejemplo:** Si un cuadro está dentro de otro que mide 500px y le dices que tenga un `width: 50%`, medirá 250px. Si el padre cambia a 1000px, automáticamente medirá 500px.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas en Porcentajes (%)</title>
    <style>
        .contenedor-padre {
            width: 80%; /* Ocupa el 80% del ancho de la ventana */
            background-color: #eee;
            padding: 20px;
            border: 2px dashed gray;
            margin: 20px auto; /* Centramos el contenedor */
            box-sizing: border-box; /* Incluye padding y borde en el ancho/alto */
        }

        .caja-hija-50 {
            width: 50%; /* Ocupa el 50% del ancho de su padre (.contenedor-padre) */
            height: 80px;
            background-color: lightgreen;
            border: 1px solid darkgreen;
            margin-bottom: 10px;
            padding: 5px;
        }

        .caja-hija-25 {
            width: 25%; /* Ocupa el 25% del ancho de su padre */
            height: 80px;
            background-color: lightcoral;
            border: 1px solid darkred;
            padding: 5px;
        }
    </style>
</head>
<body>
    <h1>Ejemplo de Medidas en Porcentajes (`%`)</h1>

    <div class="contenedor-padre">
        <p>Este es el contenedor padre. Su ancho es el 80% de la ventana del navegador. Intenta redimensionar la ventana para ver cómo se adapta.</p>
        <div class="caja-hija-50">
            <p>Soy una caja hija. Mi ancho es el 50% del ancho del contenedor padre.</p>
        </div>
        <div class="caja-hija-25">
            <p>Soy otra caja hija. Mi ancho es el 25% del ancho del contenedor padre.</p>
        </div>
    </div>

    <p>Observa cómo las cajas hijas se adaptan al redimensionar la ventana del navegador, porque dependen del tamaño de su padre.</p>
</body>
</html>
```

#### 3. `em`

* **¿Qué es?** La unidad `em` es relativa al tamaño de la fuente (letra) del *elemento padre*. Si no se especifica una fuente en el padre, toma la fuente por defecto del navegador.
* **¿Cuándo usarlo?** Ideal para tamaños de fuente y espaciados relacionados con el texto. Por ejemplo, si quieres que el interlineado sea 1.5 veces el tamaño de la letra.
* **Ejemplo:** Si el padre tiene un `font-size: 16px;`, entonces `1em` será `16px`. Si pones un texto con `font-size: 2em;`, medirá `32px`.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas em</title>
    <style>
        .contenedor-em {
            font-size: 16px; /* El tamaño de fuente base para este contenedor es 16px */
            background-color: lavender;
            padding: 20px;
            margin-bottom: 10px;
            border: 1px solid purple;
        }

        .texto-em-1 {
            font-size: 1em; /* 1em = 16px (tamaño de la fuente del padre) */
        }

        .texto-em-1-5 {
            font-size: 1.5em; /* 1.5em = 1.5 * 16px = 24px */
        }

        .texto-em-2 {
            font-size: 2em; /* 2em = 2 * 16px = 32px */
        }

        .caja-con-em {
            width: 10em; /* El ancho es 10 veces el tamaño de fuente del padre (10 * 16px = 160px) */
            height: 3em; /* La altura es 3 veces el tamaño de fuente del padre (3 * 16px = 48px) */
            background-color: lightgoldenrodyellow;
            border: 1px solid goldenrod;
            margin-top: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body>
    <h1>Ejemplo de Medidas `em`</h1>

    <div class="contenedor-em">
        <p>Este es el contenedor padre con un tamaño de fuente de 16px.</p>
        <p class="texto-em-1">Este texto tiene 1em (16px).</p>
        <p class="texto-em-1-5">Este texto tiene 1.5em (24px).</p>
        <p class="texto-em-2">Este texto tiene 2em (32px).</p>
        <div class="caja-con-em">
            <p>Caja con ancho y alto en em</p>
        </div>
    </div>

    <div style="font-size: 20px; background-color: #f0f8ff; padding: 15px; border: 1px solid lightblue; margin-top: 20px;">
        <p>Este es otro contenedor con un tamaño de fuente de 20px.</p>
        <p class="texto-em-1">Aquí, 1em ahora es 20px.</p>
    </div>

    <p>Observa cómo el valor de `em` cambia según el tamaño de fuente del elemento padre.</p>
</body>
</html>
```

#### 4. `rem` (Root em)

* **¿Qué es?** La unidad `rem` es muy parecida a `em`, pero siempre es relativa al tamaño de la fuente del *elemento raíz* (`<html>`) del documento. Esto significa que su valor es constante en toda la página, a menos que cambies el `font-size` del `html`.
* **¿Cuándo usarlo?** Ideal para mantener una escala consistente en tu diseño. Si cambias el `font-size` del `html`, todo tu diseño que use `rem` se adaptará automáticamente, lo cual es genial para accesibilidad (el usuario puede aumentar el tamaño de la fuente base del navegador).
* **Ejemplo:** Si el `font-size` por defecto del navegador (y del `html`) es 16px, entonces `1rem` siempre será `16px` en cualquier parte de tu página.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas rem</title>
    <style>
        /* Por defecto, 1rem suele ser 16px en la mayoría de navegadores.
           Podemos cambiarlo aquí si queremos una base diferente: */
        /* html { font-size: 18px; } */ /* Si descomentas esto, 1rem será 18px */

        .contenedor-rem {
            font-size: 20px; /* Este contenedor tiene su propia fuente, pero no afecta a rem */
            background-color: aliceblue;
            padding: 20px;
            margin-bottom: 10px;
            border: 1px solid lightblue;
        }

        .texto-rem-1 {
            font-size: 1rem; /* Siempre será el tamaño de fuente del html (por defecto 16px) */
        }

        .texto-rem-1-5 {
            font-size: 1.5rem; /* 1.5 veces el tamaño de fuente del html */
        }

        .caja-con-rem {
            width: 15rem; /* Ancho basado en la fuente del html */
            height: 5rem; /* Alto basado en la fuente del html */
            background-color: palegreen;
            border: 1px solid green;
            margin-top: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body>
    <h1>Ejemplo de Medidas `rem`</h1>

    <p>El tamaño de fuente base de este documento (del elemento `html`) suele ser 16px por defecto en los navegadores.</p>

    <div class="contenedor-rem">
        <p>Este contenedor tiene su propio tamaño de fuente (20px), pero no afecta a las medidas `rem`.</p>
        <p class="texto-rem-1">Este texto tiene 1rem. Su tamaño es el mismo que la fuente base del HTML.</p>
        <p class="texto-rem-1-5">Este texto tiene 1.5rem. Es 1.5 veces la fuente base del HTML.</p>
        <div class="caja-con-rem">
            <p>Caja con ancho y alto en rem</p>
        </div>
    </div>

    <p>Intenta cambiar el `font-size` en el `html` en la sección `<style>` y verás cómo todo lo que usa `rem` cambia de tamaño de forma uniforme.</p>
</body>
</html>
```

#### 5. `vw` (Viewport Width) y `vh` (Viewport Height)

* **¿Qué es?**
    * `vw` significa "viewport width" (ancho del área visible del navegador). `1vw` es el 1% del ancho total de la ventana del navegador.
    * `vh` significa "viewport height" (alto del área visible del navegador). `1vh` es el 1% del alto total de la ventana del navegador.
* **¿Cuándo usarlo?** ¡Perfecto para elementos que deben escalar con el tamaño de la ventana! Por ejemplo, si quieres un encabezado que siempre ocupe el 10% del alto de la pantalla, o un texto que se haga más grande/pequeño a medida que el usuario redimensiona la ventana.
* **Ejemplo:** Un elemento con `width: 50vw` siempre ocupará la mitad del ancho de la ventana, sin importar el tamaño del padre.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas vw y vh</title>
    <style>
        body {
            margin: 0; /* Quitamos márgenes por defecto del body */
            font-family: sans-serif;
            overflow-x: hidden; /* Evitar scroll horizontal si algo se desborda */
        }

        .seccion-vw-vh {
            width: 100vw; /* Ocupa el 100% del ancho de la ventana */
            height: 50vh; /* Ocupa el 50% del alto de la ventana */
            background-color: #e0ffff;
            border: 2px solid teal;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            margin-bottom: 20px;
        }

        .texto-vw {
            font-size: 5vw; /* El tamaño de la fuente es el 5% del ancho de la ventana */
            color: darkblue;
        }

        .texto-vh {
            font-size: 3vh; /* El tamaño de la fuente es el 3% del alto de la ventana */
            color: darkgreen;
            margin-top: 10px;
        }

        .caja-mix {
            width: 80vw; /* 80% del ancho de la ventana */
            height: 10vh; /* 10% del alto de la ventana */
            background-color: lightsalmon;
            border: 1px solid crimson;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Ejemplo de Medidas `vw` y `vh`</h1>

    <div class="seccion-vw-vh">
        <p class="texto-vw">¡Hola! Mi texto escala con el ANCHO de la ventana (`vw`).</p>
        <p class="texto-vh">Y este texto escala con el ALTO de la ventana (`vh`).</p>
        <p>Intenta redimensionar tu navegador (achicarlo y agrandarlo) para ver el efecto.</p>
    </div>

    <div class="caja-mix">
        <p>Esta caja tiene un ancho del 80vw y un alto del 10vh.</p>
    </div>

    <p style="text-align: center; margin-top: 30px;">
        Las unidades `vw` y `vh` son excelentes para hacer que elementos y textos se adapten fluidamente al tamaño de la pantalla.
    </p>
</body>
</html>
```

---

### Resumen Rápido y Consejos para tus Alumnos:

* **`px` (Píxeles):** Son fijos, como los puntos en una pantalla. Útiles para cosas que no deben cambiar de tamaño, como bordes finos.
* **`%` (Porcentaje):** Son flexibles, dependen del tamaño de su "padre". Genial para dividir un espacio.
* **`em`:** Relativo al tamaño de fuente del *padre*. Puede ser un poco confuso al principio porque "se hereda".
* **`rem`:** Relativo al tamaño de fuente del `html` (la base de toda la página). Más predecible y bueno para mantener una escala consistente.
* **`vw` y `vh`:** Relativo al tamaño de la *ventana del navegador*. ¡Excelente para diseños que deben escalar a la pantalla!

**Consejo clave para tus alumnos:** Al principio, `px` es el más fácil de entender. Pero a medida que avancen, verán que las medidas **relativas** (`%`, `rem`, `vw`, `vh`) son mucho más potentes para crear páginas web que se vean bien en cualquier dispositivo (móviles, tablets, ordenadores). ¡Es el secreto de los diseños "responsive"!

Anima a tus alumnos a jugar con estos códigos, cambiar los valores y redimensionar la ventana del navegador. La experimentación es la mejor manera de aprender. ¡Mucha suerte!