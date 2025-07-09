# Guía Rápida: Tipos de Datos en JavaScript

## Tipos Primitivos

### 1. **Number**
Representa números enteros y decimales.

```javascript
let edad = 25;
let precio = 19.99;
let negativo = -42;
let infinito = Infinity;
let noEsNumero = NaN;

console.log(typeof edad); // "number"
```

### 2. **String**
Cadenas de texto.

```javascript
let nombre = "Juan";
let apellido = 'Pérez';
let mensaje = `Hola ${nombre}!`; // Template literal
let multilinea = `Primera línea
Segunda línea`;

console.log(typeof nombre); // "string"
```

### 3. **Boolean**
Valores verdadero o falso.

```javascript
let esVerdadero = true;
let esFalso = false;
let resultado = 5 > 3; // true

console.log(typeof esVerdadero); // "boolean"
```

### 4. **Undefined**
Variable declarada pero sin valor asignado.

```javascript
let sinValor;
console.log(sinValor); // undefined
console.log(typeof sinValor); // "undefined"
```

### 5. **Null**
Representa ausencia intencional de valor.

```javascript
let vacio = null;
console.log(vacio); // null
console.log(typeof vacio); // "object" (peculiaridad de JS)
```

### 6. **Symbol**
Identificador único (ES6+).

```javascript
let sym1 = Symbol('descripcion');
let sym2 = Symbol('descripcion');
console.log(sym1 === sym2); // false (cada Symbol es único)
console.log(typeof sym1); // "symbol"
```

### 7. **BigInt**
Para números enteros muy grandes (ES2020+).

```javascript
let numeroGrande = 123456789012345678901234567890n;
let otraForma = BigInt("123456789012345678901234567890");
console.log(typeof numeroGrande); // "bigint"
```

## Tipos No Primitivos (Object)

### 8. **Object**
Colección de propiedades clave-valor.

```javascript
let persona = {
    nombre: "Ana",
    edad: 30,
    activo: true
};

console.log(persona.nombre); // "Ana"
console.log(typeof persona); // "object"
```

### 9. **Array**
Lista ordenada de elementos.

```javascript
let numeros = [1, 2, 3, 4, 5];
let mixto = ["texto", 42, true, null];
let vacio = [];

console.log(numeros[0]); // 1
console.log(typeof numeros); // "object"
console.log(Array.isArray(numeros)); // true
```

### 10. **Function**
Bloque de código reutilizable.

```javascript
function saludar(nombre) {
    return `Hola, ${nombre}!`;
}

let despedir = function(nombre) {
    return `Adiós, ${nombre}!`;
};

let flecha = (nombre) => `Hey, ${nombre}!`;

console.log(typeof saludar); // "function"
```

### 11. **Date**
Para trabajar con fechas.

```javascript
let ahora = new Date();
let fecha = new Date('2023-12-25');
let timestamp = new Date(1640995200000);

console.log(typeof ahora); // "object"
console.log(ahora instanceof Date); // true
```

### 12. **RegExp**
Expresiones regulares.

```javascript
let patron = /[a-z]+/g;
let otroPatron = new RegExp('[0-9]+', 'i');

console.log(typeof patron); // "object"
console.log(patron instanceof RegExp); // true
```

## Verificación de Tipos

### typeof
```javascript
console.log(typeof 42);           // "number"
console.log(typeof "hola");       // "string"
console.log(typeof true);         // "boolean"
console.log(typeof undefined);    // "undefined"
console.log(typeof null);         // "object" (¡cuidado!)
console.log(typeof {});           // "object"
console.log(typeof []);           // "object"
console.log(typeof function(){}); // "function"
```

### instanceof
```javascript
let arr = [1, 2, 3];
let obj = {};
let fecha = new Date();

console.log(arr instanceof Array);  // true
console.log(obj instanceof Object); // true
console.log(fecha instanceof Date); // true
```

### Métodos útiles
```javascript
Array.isArray([1, 2, 3]);        // true
Number.isNaN(NaN);               // true
Number.isFinite(42);             // true
Object.prototype.toString.call([]); // "[object Array]"
```

## Conversión de Tipos

### Conversión a String
```javascript
let num = 42;
console.log(String(num));    // "42"
console.log(num.toString()); // "42"
console.log(num + "");       // "42"
```

### Conversión a Number
```javascript
let str = "42";
console.log(Number(str));    // 42
console.log(parseInt(str));  // 42
console.log(parseFloat(str)); // 42
console.log(+str);           // 42
```

### Conversión a Boolean
```javascript
console.log(Boolean(1));      // true
console.log(Boolean(0));      // false
console.log(Boolean(""));     // false
console.log(Boolean("hola")); // true
console.log(!!"hola");        // true
```

## Valores Falsy en JavaScript
```javascript
// Estos valores se evalúan como false:
false
0
-0
0n
""
null
undefined
NaN
```

## Valores Truthy
```javascript
// Todo lo que no sea falsy es truthy:
true
1
"0"
"false"
[]
{}
function(){}
```