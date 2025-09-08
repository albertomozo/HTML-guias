# EJERCICIO 01 - MONTES
https://github.com/albertomozo/web-01-intro/tree/main/01-web-intro

# EJERCICIO 02 - CIUDADES

https://drive.google.com/drive/folders/1hbANpfscSdNLfJc_VC__HlmzxFRJSSZ2?usp=sharing	



# EJERCICIO 03 <IFRAMES>
EJERCICIO
Investigar en tus plataformas habituales como puedes insertar tu contenido en tu página.
Siempre puedes probar poniendo un mapa de google maps !!!
https://docs.google.com/presentation/d/1KfPKrD9dmRxfIlOQ9hdRaeayiibZQ7jZJXq_qWlHOTA/edit?slide=id.g2ae202b06d4_0_8#slide=id.g2ae202b06d4_0_8

# EJERCICO 04 BARRA DE REDES SOCIALES
Usando iconos, crearos vuestra propia barra de navegación a vuestra redes sociales.

Os paso como ejemplo est abara maquetada con <table>.
https://github.com/albertomozo/HTML-IMAGENES/blob/main/06-barra.html
El ejercicio consiste en personalizarla con vuestras redes y maquetarla como una barra de navegación 
```html
<ul>
  <li><a><svg>        </li>
  ....
</ul>
```

Como siempre en Internet hay multitud de código hechos. Haced una busqueda y intentar copiar un diseño que os guste.

# EJERCICIO 05  UNSPLASH
Crear una página web, en la que vais a colocar una imagen descargada de https://unsplash.com/es  con las siguientes caracteriscas:
Hay que reducir el tamaño de la foto a 500px de ancho
Colocar la imagen como background 
Con un borde redondeado
La atribución de unsplash colocarla en letra que resalte encima de la imagen

# EJERCICIO 06 FAVICON

siguiendo las instrucciones adjuntas https://docs.google.com/presentation/d/1izevuJu99f5T8hneO6xV5EIcwXwNsuUbQCBZVzJWPgg/edit?slide=id.g2aaa4f5af2a_0_8#slide=id.g2aaa4f5af2a_0_8

crear un favicon para tu web



# EJERCICIO  07  FONTS
Aplicar fuentes de google fonts y fuentes en ficheros de font
https://docs.google.com/presentation/d/1OFtKHyxyZJVulR0SMkdugUt3MbB-4dktjLCDAdkJ1P0/edit?slide=id.g2b20c8042fb_0_0#slide=id.g2b20c8042fb_0_0

# EJERCICIO 08 POSITION
Tomando como base este código HTML
https://github.com/albertomozo/web-01-intro/blob/main/99-ejemplos/position_css.html
Crear un barra inferior de similar a la de acepar cookies.

# EJERCICIO 09 esqueleto CV en  HTML
Os paso un fichero html, para que os sirva de base en la confección de vuestro curriculum

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="cv.css">
    <title>Cv</title>
</head>
<body>
    <header>
        <h1>Curriculum Nombre Apellido</h1>
    </header>
    <nav>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#experiencia">Experiencia</a></li>
            <li><a href="#formacion">Formación</a></li>
            <li><a href="#idiomas">Idiomas</a></li>
            <li><a href="#habilidades">Habilidades</a></li>
            <li><a href="#contacto">Contacto</a></li>
        </ul>
    </nav>
    <section id="incio">
        <h2>Datos Personales</h2>
        <ul>
            <li>Nombre : xxxxx</li>
            <li>mail: xxxxx</li>
            <li>......: xxxxx</li>
        </ul>
    </section>
    <section id="experiencia">
        <h2>Experiencia</h2>
        <article class="exp" id="exp02">
            <h3>Trabajo (2020 - Actualidad)</h3>
            <ul>
                <li>Descripcion</li>
                <li>Funciones</li>
                    <ul>
                        <li>Función 1</li>
                        <li>Función 1</li>
                        <li>Función 1</li>
                    </ul>
            </ul>
        </article>
        <article class="exp" id="exp02">
            <h3>Trabajo (2020 - Actualidad)</h3>
            <ul>
                <li>Descripcion</li>
                <li>Funciones</li>
                    <ul>
                        <li>Función 1</li>
                        <li>Función 1</li>
                        <li>Función 1</li>
                    </ul>
            </ul>
        </article>
    </section>
    <section id="formacion">
        <h2>Formación</h2>
        <article class="form" id="for02">
            <h3>Titulo  (999H)</h3>
            <p>Institucion</p>
            <p>Temario</p>
        </article>
        <article class="form" id="for01">
            <h3>Titulo  (999H)</h3>
            <p>Institucion</p>
            <p>Temario</p>
        </article>
        
    </section>
        <section id="idiomas">
        <h2>Idiomas</h2>
        <table>
            <tr>
                <th>Idioma</th><th>lectura</th><th>escritura</th><th>Comprension</th><th>Nivel</th>
            </tr>
             <tr>
                <th>Español</th><th>10</th><th>10</th><th>10</th><th>C1</th>
            </tr>
              <tr>
                <th>Euskera</th><th>4</th><th>4</th><th>2</th><th>A1</th>
            </tr>
               <tr>
                <th>Ingles</th><th>7</th><th>6</th><th>5</th><th>A2</th>
            </tr>
        </table>
    </section>
    <section id="habilidades">
        <h2>Habilidades</h2>
        <article class="habilidades">
            <h3>HTML</h3>
            <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>HTML5</title><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.564-2.438L1.5 0zm7.031 9.75l-.232-2.718 10.059.003.23-2.622L5.412 4.41l.698 8.01h9.126l-.326 3.426-2.91.804-2.955-.81-.188-2.11H6.248l.33 4.171L12 19.351l5.379-1.443.744-8.157H8.531z"/></svg>
            <p>Nivel : 9</p>
        </article>
        <article class="habilidades">
            <h3>CSS3</h3>
            <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>CSS</title><path d="M0 0v20.16A3.84 3.84 0 0 0 3.84 24h16.32A3.84 3.84 0 0 0 24 20.16V3.84A3.84 3.84 0 0 0 20.16 0Zm14.256 13.08c1.56 0 2.28 1.08 2.304 2.64h-1.608c.024-.288-.048-.6-.144-.84-.096-.192-.288-.264-.552-.264-.456 0-.696.264-.696.84-.024.576.288.888.768 1.08.72.288 1.608.744 1.92 1.296q.432.648.432 1.656c0 1.608-.912 2.592-2.496 2.592-1.656 0-2.4-1.032-2.424-2.688h1.68c0 .792.264 1.176.792 1.176.264 0 .456-.072.552-.24.192-.312.24-1.176-.048-1.512-.312-.408-.912-.6-1.32-.816q-.828-.396-1.224-.936c-.24-.36-.36-.888-.36-1.536 0-1.44.936-2.472 2.424-2.448m5.4 0c1.584 0 2.304 1.08 2.328 2.64h-1.608c0-.288-.048-.6-.168-.84-.096-.192-.264-.264-.528-.264-.48 0-.72.264-.72.84s.288.888.792 1.08c.696.288 1.608.744 1.92 1.296.264.432.408.984.408 1.656.024 1.608-.888 2.592-2.472 2.592-1.68 0-2.424-1.056-2.448-2.688h1.68c0 .744.264 1.176.792 1.176.264 0 .456-.072.552-.24.216-.312.264-1.176-.048-1.512-.288-.408-.888-.6-1.32-.816-.552-.264-.96-.576-1.2-.936s-.36-.888-.36-1.536c-.024-1.44.912-2.472 2.4-2.448m-11.031.018c.711-.006 1.419.198 1.839.63.432.432.672 1.128.648 1.992H9.336c.024-.456-.096-.792-.432-.96-.312-.144-.768-.048-.888.24-.12.264-.192.576-.168.864v3.504c0 .744.264 1.128.768 1.128a.65.65 0 0 0 .552-.264c.168-.24.192-.552.168-.84h1.776c.096 1.632-.984 2.712-2.568 2.688-1.536 0-2.496-.864-2.472-2.472v-4.032c0-.816.24-1.44.696-1.848.432-.408 1.146-.624 1.857-.63"/></svg>
            <p>Nivel : 9</p>
        </article>
    </section>
    <section id="contacto">
        <h3>Contacto</h3>
        <p>Formulario de contacto</p>
    </section>
    <footer>
        &copy; 2025 Alberto Mozo
    </footer>
    
</body>
</html>
```

# EJERCICIO 09  display:flex

Sobre el html https://github.com/albertomozo/HTML-COLUMNAS/blob/main/05-zapatillas-flex.html realizar modificacioens en el css para
- poner bordes   a los ```<article>``` ( zapatillas)
- centrar titulo de zapatillas
- poner secciones nuevas para zapatillas a 2 columna y a 5 columnas
- Probar las alineaciones de ```justify-content```

# EJERCICIO 10 - COMPARTIDO EN GITHUB
https://github.com/albertomozo/PROYECTO_202505_IFCD0110

# EJERCICIO 11 - MOBILE FIRST
Convertir este ejercicio "Desktop first"  en "Mobile first"
https://github.com/albertomozo/HTML_RESPONSIVE/blob/main/03-ejemplo-tintin2.html

# EJERCICIO 12 - Ideas fescas
El ejercicio de hoy consiste en realizar una web idéntica al modelo proporcionado.
https://drive.google.com/drive/folders/1fHxPlcz_HyjqnNXLLXT-0rYCfVU_fTOm?usp=sharing

# EJERCICIO 13  FORMULARIO CONTACTO EN CURRICULUM
Vamos a registrarnos en la página https://jotform.com  y vamos a crear un formulario para incrustar en nuestra página de curriculum. Vamos a solicitar nombre, correo y texto de observaciones.

https://getbootstrap.com/docs/5.2/getting-started/introduction/

Una vez enlazado los css, y los script. Buscar en la seccion componentes colocar en la pagina los siguientes elmentos:
- acordeón
- galería

# EJERCICIO 15
Realizar el siguiente sistema de layouts en Bootstrap

3 imagenes

Móvil
![Layaout movil](/imagenes/imagemobile.webp)

Tablet
![Layaout tablet](/imagenes/imagetablet.webp)

Desktop
![Layaout Desktop](/imagenes/imageDesktop.webp)

# EJERCICIO 16 - FORMULARIOS


---

## :pencil: **Ejercicio: Formulario de Registro de Usuario**

### :dart: **Objetivo**

Crear un formulario HTML que permita registrar un nuevo usuario, aplicando correctamente etiquetas como `<form>`, `<input>`, `<select>`, `<textarea>`, `<label>`, entre otras, y organizando visualmente el formulario.

---

### :page_facing_up: **Enunciado del ejercicio**

Crea una página web llamada `registro.html` que contenga un **formulario de registro** con los siguientes campos:

#### :bust_in_silhouette: Datos personales:

* **Nombre completo** (campo de texto)
* **Correo electrónico** (campo `type="email"`)
* **Contraseña** (campo `type="password"`)
* **Fecha de nacimiento** (campo `type="date"`)
* **Sexo** (opciones tipo `radio`: Hombre / Mujer / Otro)
* **País de residencia** (menú desplegable con 5 países a elegir)

#### :mailbox_with_mail: Información adicional:

* **Habilidades** (varios checkbox: HTML, CSS, JavaScript, Python, Otros)
* **Comentario** (campo `<textarea>` para comentarios opcionales)
* **Subir imagen de perfil** (campo `type="file"`)

#### :white_check_mark: Botones:

* **Enviar** (type `submit`)
* **Limpiar formulario** (type `reset`)

---

### :art: **Requisitos de diseño (opcionales)**

* Agrupar los datos en bloques visuales usando `<fieldset>` y `<legend>`.
* Asociar correctamente las etiquetas `<label>` con los campos usando `for` y `id`.
* Añadir al menos 3 campos con el atributo `required`.
* Añadir `placeholder` en algunos inputs.

---

### :bulb: **Pistas para ampliación (para alumnos más avanzados)**

* Validar que el correo tiene un formato correcto.
* Previsualizar la imagen de perfil seleccionada (con JS).
* Usar CSS o Bootstrap para mejorar la apariencia del formulario.

# EJERCICIO 18 - JS - getElementById
Crear 2 contenedores y diferentes botones para cambia r los estilos de los  botones
```html<body>
    <button type="button"  onclick="rojo('id1')" >rojo 1</button>
     <button type="button"  onclick="rojo('id2')" >rojo 2</button>
     <button type="button"  onclick="rojo('id3')" >rojo 3</button>
    <button type="button"  onclick="verde()" >verde</button>
    <button type="button"  onclick="circulo()" >circulo</button>
    <button type="button" onclick="cuadrado()">cuadrado</button>
    <button type="button" onclick="anchura100por100()">Anchura 100%</button>
     <button type="button" onclick="anchurainicial()">Anchura initial-scale</button>
    <div class="micontenedor" id="id1">

    </div>
    <div class="micontenedor" id="id2">

    </div>
    <input type="text" id="id3" placeholder="Introduce texto aquí">
```
# EJERCICO 19 - JS  - BOMIBILLA
Partiendo de este ejercicio https://github.com/albertomozo/JS-01-introduccion/blob/main/19_onclick-bombilla_00.html
Generar un único botón de encendido y apagado. 
Cambiar el boton por 2 imagenes de interruptor apagado / interuptor encendido

# EJERCICIO 20 - BOTONES FOTOS
Modificar este código https://github.com/albertomozo/JS-01-introduccion/blob/main/20_onclick-fotos.html .
- Crear una función con parámetro
- Poner un titulo a las fotos
- Modificar estilo del boton activo

# EJERCICO 21 ADIVINAR UN NUMERO
El ejercicio consiste en solicitar un numero del 1 al 100 y adivinarlo.  Hay que devolver como resultado el intento en el que se ha adivinado el numero.
Intentar crear el pseudocodigo usando mientras en lugar de for, no sabemos el numero de iteraciones o repeticiones.
```
// Juego simple que pide al usuario que adivine un numero en 10 intentos

Algoritmo Adivina_Numero

    Definir intentos,num_secreto,num_ingresado Como Entero;
    intentos<-10;
    num_secreto <- azar(100)+1;
    
    Escribir "Adivine el numero (de 1 a 100):";
    Leer num_ingresado;
    Mientras num_secreto<>num_ingresado & intentos>1 Hacer
        Si num_secreto>num_ingresado Entonces
            Escribir "Muy bajo";
        SiNo 
            Escribir "Muy alto";
        FinSi
        intentos <- intentos-1;
        Escribir "Le quedan ",intentos," intentos:";
        Leer num_ingresado;
    FinMientras
    
    Si num_secreto=num_ingresado Entonces
        Escribir "Exacto! Usted adivino en ",11-intentos," intentos.";
    SiNo
        Escribir "El numero era: ",num_secreto;
    FinSi
    
FinAlgoritmo
```



# EJERCICIO 22
#VARIOS EJERCICIOS

Ejercicios de JavaScript con Funciones y Formularios
Estos ejercicios están pensados para practicar la lectura de inputs, la ejecución de funciones y la visualización de resultados en el navegador.

---

:green_circle: Nivel 1 - Básico
Calculadora de Propina :receipt:
Pide al usuario el importe de una cuenta y el porcentaje de propina que quiere dejar. Muestra el total a pagar.

---

Conversor de Celsius a Fahrenheit :thermometer:
El usuario introduce una temperatura en grados Celsius y se muestra su equivalente en Fahrenheit.

---

Calculadora de Edad :date:
Introduce el año de nacimiento y calcula la edad actual.

---

:yellow_circle: Nivel 2 - Medio
Calculador de Gastos Mensuales :money_with_wings:
El usuario introduce sus gastos en comida, transporte y ocio. Se calcula el total mensual.

---

Detector de Mayor o Menor de Edad :child::man:
Introduce tu edad y muestra si eres menor o mayor de edad.

---

Calculadora de IMC (Índice de Masa Corporal) :scales:
El usuario introduce su peso (kg) y altura (m). Se calcula su IMC y se muestra una interpretación básica:
Bajo peso: < 18.5
Normal: 18.5–24.9
Sobrepeso: 25–29.9
Obesidad: 30 o más

(IMC = peso (kg) / estatura (m²))
---

:blue_circle: Nivel 3 - Avanzado
Calculadora de letra del DNI :id:
El usuario introduce su número de DNI sin letra (ej. 12345678) y el programa calcula y muestra la letra correcta usando el algoritmo oficial.

---

Calculadora de tarifa eléctrica :zap:
Según el consumo en kWh, se calcula el coste con una tarifa escalonada:
Hasta 100 kWh → 0.15 €/kWh
De 101 a 200 kWh → 0.20 €/kWh
Más de 200 kWh → 0.25 €/kWh

Se debe mostrar el total a pagar según el tram

# EJERCIO 23 - ARRAYS CON CON CONTENIDO "DINAMICO"

## Ejercicios arrays con "contenido dinámico"

Ejercicios prácticos que combinan arrays para alamacenar datos, para mostrar en html

### 1. Galería de imágenes dinámica

- **Enunciado:** Crea un array con rutas o nombres de imágenes (por ejemplo, `"foto1.jpg", "foto2.jpg", "foto3.jpg"`). Usa un bucle `for` para mostrar cada imagen en la página web con etiquetas `<img>`.
- **Variantes :**
    - Cambia el tamaño o el borde de las imágenes según el índice.
    - Agrega un texto alternativo personalizado para cada imagen.


### 2. Carrusel básico de fotos

- **Enunciado:** Usa un array de imágenes y muestra solo una a la vez. Añade botones "Siguiente" y "Anterior" para navegar entre ellas, cambiando el índice del array.


### 3. Lista visual de productos

- **Enunciado:** Crea dos arrays: uno con nombres de productos y otro con imágenes. Muestra una tabla donde cada fila tenga el nombre y la imagen correspondiente.
- **Extensión:** Agrega precios o descripciones en nuevas columnas para hacerlo más realista.


### 4. Álbum de tarjetas (cards) de animales

- **Enunciado:** Usa un array de objetos, donde cada objeto tenga el nombre de un animal y el archivo de su imagen. Muestra todas las tarjetas con nombre e imagen.



### 5. Visualización de notas o calificaciones

- **Enunciado:** Crea un array con las notas de varios estudiantes. Muestra los nombres y las notas en una tabla. Resalta visualmente la nota más alta y la más baja.
- **Extensión:** Agrega un promedio y usa colores para indicar el rendimiento.


### 6. Iconos o píxeles en matriz

- **Enunciado:** Crea una matriz (array bidimensional) que represente un icono en blanco y negro (por ejemplo, usando 0 para blanco y 1 para negro). Muestra el icono en pantalla usando caracteres o bloques de color.
- **Motivación:** Introduce arrays de dos dimensiones y creatividad visual.

# EJERCICIO 24 - OBJETOS

https://docs.google.com/document/d/1D8_pcvk3ODNcsSr9-z6Dmyfz0O5Jufn3CZb-DodTdQw/edit?tab=t.0

# EJERCICIO 25
# CASO REAL. CAMBIAR FORMULARIO.

La empresa te entrega este formulario de registro que lleva años en su web.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Registro de Usuario</title>
</head>
<body bgcolor="lightgray">
    <h1 align="center"><font color="blue">Formulario de Registro</font></h1>

    <form action="procesar.php" method="get" onSubmit="return validar()">
        <table border="1" align="center" cellpadding="10">
            <tr>
                <td>Nombre:</td>
                <td><input type="text" name="nombre"></td>
            </tr>
            <tr>
                <td>Email:</td>
                <td><input type="text" name="email"></td>
            </tr>
            <tr>
                <td>Contraseña:</td>
                <td><input type="text" name="password"></td>
            </tr>
            <tr>
                <td>Repetir contraseña:</td>
                <td><input type="text" name="password2"></td>
            </tr>
            <tr>
                <td colspan="2" align="center">
                    <input type="submit" value="Enviar">
                    <input type="reset" value="Borrar">
                </td>
            </tr>
        </table>
    </form>

    <script>
        function validar() {
            var nombre = document.forms[0].nombre.value;
            var email = document.forms[0].email.value;
            if(nombre == "" || email == "") {
                alert("Todos los campos son obligatorios");
                return false;
            }
            return true;
        }
    </script>
</body>
</html>
```

El cliente insiste en que "se ve bien" y que no lo cambiemos demasiado, pero te pide que lo modernices y lo hagas seguro.

Necesitan tenerlo actualizado hoy mismo para cumplir con normativa y evitar problemas de seguridad.

No te dicen cómo hacerlo: tu misión es detectar los fallos y arreglarlos rápidamente.

💡 Puedes usar cualquier recurso que consideres oportuno (documentación, buscadores, IA, librerías).

📌 Plazo máximo: unas pocas horas.

👉 Entregable: un nuevo código HTML+CSS+JS del formulario, que cumpla estándares actuales y sea seguro.