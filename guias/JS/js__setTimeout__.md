# Guía de setTimeout y setInterval en JavaScript

## setTimeout - Ejecutar una vez después de un tiempo

### Sintaxis básica
```javascript
setTimeout(función, tiempo, parámetros...)
```

### 1. Uso básico de setTimeout
```javascript
// Ejecutar después de 2 segundos
setTimeout(function() {
    console.log("¡Hola después de 2 segundos!");
}, 2000);

// Con función nombrada
function saludo() {
    console.log("¡Hola mundo!");
}
setTimeout(saludo, 1000);
```

### 2. Pasar parámetros con setTimeout
```javascript
function saludar(nombre, edad) {
    console.log("Hola " + nombre + ", tienes " + edad + " años");
}

// Los parámetros se pasan después del tiempo
setTimeout(saludar, 1500, "Ana", 25);
```

### 3. Cancelar setTimeout
```javascript
// Guardar el ID del timeout
var timeoutId = setTimeout(function() {
    console.log("Esto no se ejecutará");
}, 3000);

// Cancelar antes de que se ejecute
clearTimeout(timeoutId);
```

## setInterval - Ejecutar repetidamente cada cierto tiempo

### Sintaxis básica
```javascript
setInterval(función, tiempo, parámetros...)
```

### 4. Uso básico de setInterval
```javascript
// Ejecutar cada 2 segundos
setInterval(function() {
    console.log("Mensaje cada 2 segundos");
}, 2000);

// Con función nombrada
function contar() {
    console.log("Contando: " + new Date().getSeconds());
}
setInterval(contar, 1000);
```

### 5. Pasar parámetros con setInterval
```javascript
function mostrarMensaje(mensaje, numero) {
    console.log(mensaje + " - Número: " + numero);
}

// Se ejecuta cada 3 segundos
setInterval(mostrarMensaje, 3000, "Hola", 42);
```

### 6. Cancelar setInterval
```javascript
// Guardar el ID del interval
var intervalId = setInterval(function() {
    console.log("Esto se repetirá solo por un tiempo");
}, 1000);

// Cancelar después de 5 segundos
setTimeout(function() {
    clearInterval(intervalId);
    console.log("Interval cancelado");
}, 5000);
```

## Ejemplos prácticos combinados

### 7. Contador con inicio y parada
```javascript
var contador = 0;
var intervalId;

function iniciarContador() {
    intervalId = setInterval(function() {
        contador++;
        console.log("Contador: " + contador);
    }, 1000);
}

function detenerContador() {
    clearInterval(intervalId);
    console.log("Contador detenido en: " + contador);
}

// Iniciar contador
iniciarContador();

// Detener después de 10 segundos
setTimeout(detenerContador, 10000);
```

### 8. Reloj digital
```javascript
function mostrarHora() {
    var ahora = new Date();
    var horas = ahora.getHours();
    var minutos = ahora.getMinutes();
    var segundos = ahora.getSeconds();
    
    var tiempo = horas + ":" + minutos + ":" + segundos;
    console.log("Hora actual: " + tiempo);
}

// Mostrar la hora cada segundo
setInterval(mostrarHora, 1000);
```

### 9. Semáforo simple
```javascript
var estado = 0; // 0=rojo, 1=amarillo, 2=verde
var colores = ["ROJO", "AMARILLO", "VERDE"];

function cambiarSemaforo() {
    console.log("Semáforo: " + colores[estado]);
    estado = (estado + 1) % 3;
}

// Cambiar cada 2 segundos
setInterval(cambiarSemaforo, 2000);
```

### 10. Manipular elementos del DOM
```javascript
// Cambiar color de un elemento cada 3 segundos
function cambiarColor() {
    var elemento = document.getElementById("miDiv");
    var colores = ["red", "blue", "green", "orange"];
    var colorAleatorio = colores[Math.floor(Math.random() * colores.length)];
    elemento.style.color = colorAleatorio;
}

setInterval(cambiarColor, 3000);

// Mostrar mensaje después de 5 segundos
setTimeout(function() {
    document.getElementById("mensaje").innerHTML = "¡Aparecí después de 5 segundos!";
}, 5000);
```

### 11. Temporizador con cuenta regresiva
```javascript
var tiempoRestante = 10;

function cuentaRegresiva() {
    console.log("Tiempo restante: " + tiempoRestante + " segundos");
    tiempoRestante--;
    
    if (tiempoRestante < 0) {
        clearInterval(temporizador);
        console.log("¡Tiempo agotado!");
    }
}

var temporizador = setInterval(cuentaRegresiva, 1000);
```

### 12. Animación simple con timeouts
```javascript
function moverElemento() {
    var elemento = document.getElementById("cuadrado");
    var posicion = 0;
    
    function animar() {
        posicion += 10;
        elemento.style.left = posicion + "px";
        
        if (posicion < 200) {
            setTimeout(animar, 100);
        }
    }
    
    animar();
}

// Iniciar animación después de 2 segundos
setTimeout(moverElemento, 2000);
```

## Diferencias clave

| setTimeout | setInterval |
|------------|-------------|
| Se ejecuta **una sola vez** | Se ejecuta **repetidamente** |
| Se usa para retrasos | Se usa para repeticiones |
| Se cancela con `clearTimeout()` | Se cancela con `clearInterval()` |

## Ejemplo comparativo
```javascript
// setTimeout - Una sola vez
setTimeout(function() {
    console.log("Esto se ejecuta solo una vez");
}, 2000);

// setInterval - Repetidamente
var intervalo = setInterval(function() {
    console.log("Esto se repite cada 2 segundos");
}, 2000);

// Cancelar el interval después de 10 segundos
setTimeout(function() {
    clearInterval(intervalo);
    console.log("Interval cancelado");
}, 10000);
```

## Notas importantes:
- El tiempo está en milisegundos (1000ms = 1 segundo)
- Ambos devuelven un ID numérico para poder cancelarlos
- `setTimeout` se ejecuta una sola vez, `setInterval` se repite
- Siempre guarda el ID si planeas cancelar la ejecución
- Son funciones asíncronas: no bloquean el resto del código
- Es buena práctica cancelar los intervals cuando ya no los necesites