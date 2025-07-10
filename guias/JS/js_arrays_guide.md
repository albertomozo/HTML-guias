# Guía Básica de Arrays en JavaScript

## ¿Qué es un Array?

Un array es una estructura de datos que permite almacenar múltiples valores en una sola variable. Es como una caja con compartimentos numerados donde puedes guardar diferentes elementos.

```javascript
// En lugar de hacer esto:
let fruta1 = 'manzana';
let fruta2 = 'banana';
let fruta3 = 'naranja';

// Hacemos esto:
let frutas = ['manzana', 'banana', 'naranja'];
```

## Crear un Array

### Forma más común (literal)
```javascript
let numeros = [1, 2, 3, 4, 5];
let frutas = ['manzana', 'banana', 'naranja'];
let mixto = ['texto', 42, true];
let vacio = [];
```

## Acceder a los Elementos

Los arrays usan **índices** que empiezan en **0**:

```javascript
let colores = ['rojo', 'verde', 'azul'];

console.log(colores[0]); // 'rojo' (primer elemento)
console.log(colores[1]); // 'verde' (segundo elemento)
console.log(colores[2]); // 'azul' (tercer elemento)
```

### Visualización del índice:
```
Índice:   0        1        2
Array:  ['rojo', 'verde', 'azul']
```

## Propiedad length

La propiedad `length` nos dice cuántos elementos tiene el array:

```javascript
let animales = ['perro', 'gato', 'pájaro'];
console.log(animales.length); // 3

let numeros = [10, 20, 30, 40, 50];
console.log(numeros.length); // 5

let vacio = [];
console.log(vacio.length); // 0
```

## Métodos Básicos

### push() - Agregar al final
Añade uno o más elementos al final del array:

```javascript
let frutas = ['manzana', 'banana'];
console.log(frutas); // ['manzana', 'banana']

frutas.push('naranja');
console.log(frutas); // ['manzana', 'banana', 'naranja']

// Agregar varios elementos
frutas.push('uva', 'pera');
console.log(frutas); // ['manzana', 'banana', 'naranja', 'uva', 'pera']
```

### pop() - Eliminar del final
Elimina el último elemento del array y lo devuelve:

```javascript
let numeros = [1, 2, 3, 4, 5];
console.log(numeros); // [1, 2, 3, 4, 5]

let ultimoNumero = numeros.pop();
console.log(ultimoNumero); // 5
console.log(numeros); // [1, 2, 3, 4]
```

### unshift() - Agregar al principio
Añade uno o más elementos al principio del array:

```javascript
let colores = ['verde', 'azul'];
console.log(colores); // ['verde', 'azul']

colores.unshift('rojo');
console.log(colores); // ['rojo', 'verde', 'azul']

// Agregar varios elementos
colores.unshift('amarillo', 'naranja');
console.log(colores); // ['amarillo', 'naranja', 'rojo', 'verde', 'azul']
```

### shift() - Eliminar del principio
Elimina el primer elemento del array y lo devuelve:

```javascript
let letras = ['a', 'b', 'c', 'd'];
console.log(letras); // ['a', 'b', 'c', 'd']

let primeraLetra = letras.shift();
console.log(primeraLetra); // 'a'
console.log(letras); // ['b', 'c', 'd']
```

## Recorrer Arrays con For Tradicional

El bucle `for` tradicional es la forma clásica de recorrer un array:

```javascript
let frutas = ['manzana', 'banana', 'naranja', 'uva'];

for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
}
```

### Desglose del bucle for:
- `let i = 0`: Empezamos en el índice 0
- `i < frutas.length`: Continuamos mientras el índice sea menor que la longitud
- `i++`: Incrementamos el índice en cada iteración

### Ejemplo con índices:
```javascript
let numeros = [10, 20, 30, 40];

for (let i = 0; i < numeros.length; i++) {
    console.log(`Índice ${i}: ${numeros[i]}`);
}

// Resultado:
// Índice 0: 10
// Índice 1: 20
// Índice 2: 30
// Índice 3: 40
```

## Ejemplos Prácticos

### Ejemplo 1: Lista de tareas
```javascript
let tareas = [];

// Agregar tareas
tareas.push('Hacer ejercicio');
tareas.push('Estudiar JavaScript');
tareas.push('Leer un libro');

console.log(`Tienes ${tareas.length} tareas por hacer:`);

// Mostrar todas las tareas
for (let i = 0; i < tareas.length; i++) {
    console.log(`${i + 1}. ${tareas[i]}`);
}
```

### Ejemplo 2: Procesar calificaciones
```javascript
let calificaciones = [85, 92, 78, 96, 88];

console.log('Calificaciones del estudiante:');

// Mostrar todas las calificaciones
for (let i = 0; i < calificaciones.length; i++) {
    console.log(`Examen ${i + 1}: ${calificaciones[i]}`);
}

// Calcular promedio
let suma = 0;
for (let i = 0; i < calificaciones.length; i++) {
    suma = suma + calificaciones[i];
}
let promedio = suma / calificaciones.length;
console.log(`Promedio: ${promedio}`);
```

### Ejemplo 3: Modificar elementos
```javascript
let precios = [10, 25, 30, 15, 40];

console.log('Precios originales:');
for (let i = 0; i < precios.length; i++) {
    console.log(`Producto ${i + 1}: $${precios[i]}`);
}

// Aplicar descuento del 10%
for (let i = 0; i < precios.length; i++) {
    precios[i] = precios[i] * 0.9;
}

console.log('Precios con descuento:');
for (let i = 0; i < precios.length; i++) {
    console.log(`Producto ${i + 1}: $${precios[i]}`);
}
```

## Puntos Importantes a Recordar

1. **Los índices empiezan en 0**: El primer elemento está en la posición 0
2. **length es muy útil**: Siempre úsalo para saber cuántos elementos tienes
3. **push/pop trabajan al final**: Para agregar/quitar del final del array
4. **unshift/shift trabajan al principio**: Para agregar/quitar del principio
5. **El bucle for es fundamental**: `for (let i = 0; i < array.length; i++)`

## Errores Comunes

```javascript
let numeros = [1, 2, 3];

// ❌ Error: índice fuera de rango
console.log(numeros[5]); // undefined

// ❌ Error: olvidar el índice
console.log(numeros.length); // 3 (correcto)
console.log(numeros.lenght); // undefined (mal escrito)

// ❌ Error: empezar el for en 1
for (let i = 1; i < numeros.length; i++) {
    // Se salta el primer elemento
}

// ✅ Correcto: empezar en 0
for (let i = 0; i < numeros.length; i++) {
    console.log(numeros[i]);
}
```

¡Con estos conceptos básicos ya puedes empezar a trabajar con arrays en JavaScript!