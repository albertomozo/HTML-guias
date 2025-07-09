<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Guía rápida del objeto `Math` en JavaScript

El objeto `Math` en JavaScript proporciona funciones y constantes matemáticas. No es un constructor, por lo que no se puede instanciar, y todas sus propiedades y métodos son estáticos.

## Propiedades principales

- **Math.PI**: Valor de π (aprox. 3.14159)
- **Math.E**: Base de los logaritmos naturales (aprox. 2.718)
- **Math.LN2**: Logaritmo natural de 2

```js
console.log(Math.PI); // 3.141592653589793
console.log(Math.E);  // 2.718281828459045
```


## Métodos comunes

### Redondeo

- **Math.round(x)**: Redondea al entero más cercano.
- **Math.ceil(x)**: Redondea hacia arriba.
- **Math.floor(x)**: Redondea hacia abajo.
- **Math.trunc(x)**: Elimina la parte decimal.

```js
console.log(Math.round(4.7)); // 5
console.log(Math.ceil(4.1));  // 5
console.log(Math.floor(4.9)); // 4
console.log(Math.trunc(4.9)); // 4
```


### Operaciones básicas

- **Math.abs(x)**: Valor absoluto.
- **Math.max(a, b, ...)**: Máximo de varios valores.
- **Math.min(a, b, ...)**: Mínimo de varios valores.

```js
console.log(Math.abs(-10));         // 10
console.log(Math.max(1, 5, 3));     // 5
console.log(Math.min(1, 5, 3));     // 1
```


### Potencias y raíces

- **Math.pow(base, exp)**: Potencia.
- **Math.sqrt(x)**: Raíz cuadrada.
- **Math.cbrt(x)**: Raíz cúbica.

```js
console.log(Math.pow(2, 3));  // 8
console.log(Math.sqrt(16));   // 4
console.log(Math.cbrt(27));   // 3
```


### Trigonometría

- **Math.sin(x)**, **Math.cos(x)**, **Math.tan(x)**: Seno, coseno y tangente (en radianes).

```js
console.log(Math.sin(Math.PI / 2)); // 1
console.log(Math.cos(0));           // 1
console.log(Math.tan(0));           // 0
```


### Logaritmos

- **Math.log(x)**: Logaritmo natural.
- **Math.log10(x)**: Logaritmo base 10.
- **Math.log2(x)**: Logaritmo base 2.

```js
console.log(Math.log(Math.E));    // 1
console.log(Math.log10(100));     // 2
console.log(Math.log2(8));        // 3
```


### Aleatorio

- **Math.random()**: Número pseudoaleatorio entre 0 (incluido) y 1 (excluido).

```js
console.log(Math.random()); // Ejemplo: 0.5367
```


## Ejemplo práctico: Número aleatorio entre dos valores

```js
function aleatorioEntre(min, max) {
  return Math.random() * (max - min) + min;
}
console.log(aleatorioEntre(5, 10)); // Ejemplo: 7.345
```

Esta guía cubre los métodos y propiedades más usados del objeto `Math` en JavaScript, útiles para la mayoría de las tareas matemáticas básicas y avanzadas en desarrollo web.

