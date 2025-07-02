# Guía Rápida: Variables en JavaScript

## 1. Los 3 Tipos de Variables

JavaScript tiene **3 formas** de declarar variables:

| Palabra clave | Scope | Reasignación | Redeclaración | ¿Cuándo usar? |
|---------------|-------|--------------|---------------|---------------|
| `var` | Función | ✅ Sí | ✅ Sí | ❌ **No usar** (obsoleto) |
| `let` | Bloque | ✅ Sí | ❌ No | ✅ **Variables que cambian** |
| `const` | Bloque | ❌ No | ❌ No | ✅ **Variables constantes** |

## 2. `let` - Variables que Cambian

### Uso básico
```javascript
let nombre = 'Juan';
let edad = 25;
let activo = true;

// Puedes reasignar el valor
nombre = 'María';
edad = 30;
activo = false;
```

### Scope de bloque
```javascript
function ejemplo() {
    let x = 1;
    
    if (true) {
        let x = 2; // Variable diferente
        console.log(x); // 2
    }
    
    console.log(x); // 1
}
```

## 3. `const` - Variables Constantes

### Uso básico
```javascript
const PI = 3.14159;
const NOMBRE_EMPRESA = 'Mi Empresa';
const URL_API = 'https://api.ejemplo.com';

// ❌ Esto da error
// PI = 3.14; // TypeError: Assignment to constant variable
```

### ⚠️ IMPORTANTE: `const` con objetos y arrays
```javascript
// El objeto/array puede modificarse, pero no reasignarse
const usuario = {
    nombre: 'Ana',
    edad: 28
};

// ✅ Esto SÍ se puede hacer
usuario.nombre = 'Carmen';
usuario.email = 'carmen@email.com';

// ❌ Esto NO se puede hacer
// usuario = {}; // TypeError
```

```javascript
const colores = ['rojo', 'azul'];

// ✅ Esto SÍ se puede hacer
colores.push('verde');
colores[0] = 'amarillo';

// ❌ Esto NO se puede hacer
// colores = []; // TypeError
```

## 4. Reglas de Nomenclatura

### ✅ Nombres válidos
```javascript
let nombre;
let _privado;
let $elemento;
let camelCase;
let numero1;
let CONSTANTE;
```

### ❌ Nombres inválidos
```javascript
// let 123numero;  // No puede empezar con número
// let mi-variable; // No puede tener guiones
// let class;       // No puede ser palabra reservada
// let mi variable; // No puede tener espacios
```

### 🎯 Buenas prácticas
```javascript
// ✅ Descriptivos y claros
let nombreUsuario = 'Pedro';
let edadEnAños = 25;
let estaActivo = true;

// ❌ Nombres confusos
let n = 'Pedro';
let x = 25;
let flag = true;
```

## 5. Tipos de Datos

### Primitivos
```javascript
let texto = 'Hola mundo';           // string
let numero = 42;                    // number
let decimal = 3.14;                 // number
let verdadero = true;               // boolean
let falso = false;                  // boolean
let indefinido = undefined;         // undefined
let nulo = null;                    // null
```

### Objetos
```javascript
let persona = {                     // object
    nombre: 'Juan',
    edad: 30
};

let numeros = [1, 2, 3, 4, 5];     // array (tipo object)

let fecha = new Date();             // object
```

## 6. Hoisting (Elevación)

### Con `var` (problemático)
```javascript
console.log(x); // undefined (no error, pero confuso)
var x = 5;

// JavaScript lo interpreta como:
// var x;
// console.log(x);
// x = 5;
```

### Con `let` y `const` (más seguro)
```javascript
// console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;

// console.log(z); // ReferenceError: Cannot access 'z' before initialization  
const z = 20;
```

## 7. Scope (Alcance)

### Scope global
```javascript
let variableGlobal = 'Accesible desde cualquier lugar';

function miFuncion() {
    console.log(variableGlobal); // ✅ Funciona
}
```

### Scope de función
```javascript
function ejemplo() {
    let variableLocal = 'Solo dentro de la función';
    console.log(variableLocal); // ✅ Funciona
}

// console.log(variableLocal); // ❌ ReferenceError
```

### Scope de bloque
```javascript
if (true) {
    let variableBloque = 'Solo dentro del bloque';
    const CONSTANTE_BLOQUE = 'También solo aquí';
}

// console.log(variableBloque); // ❌ ReferenceError
// console.log(CONSTANTE_BLOQUE); // ❌ ReferenceError
```

## 8. Errores Comunes

### ❌ Error 1: Usar `var`
```javascript
// Problemático
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Imprime: 3, 3, 3
}
```

### ✅ Solución: Usar `let`
```javascript
// Correcto
for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Imprime: 0, 1, 2
}
```

### ❌ Error 2: No declarar variables
```javascript
function malo() {
    miVariable = 'Esto crea una variable global'; // ❌ Malo
}
```

### ✅ Solución: Siempre declarar
```javascript
function bueno() {
    let miVariable = 'Variable local correcta'; // ✅ Bueno
}
```

### ❌ Error 3: Confundir `const` con inmutabilidad
```javascript
const objeto = { nombre: 'Juan' };
objeto.nombre = 'Pedro'; // ✅ Esto SÍ funciona
console.log(objeto.nombre); // 'Pedro'
```

## 9. Ejemplos Prácticos

### Contador con `let`
```javascript
let contador = 0;

function incrementar() {
    contador++;
    console.log(`Contador: ${contador}`);
}

incrementar(); // Contador: 1
incrementar(); // Contador: 2
```

### Configuración con `const`
```javascript
const CONFIG = {
    API_URL: 'https://api.ejemplo.com',
    TIMEOUT: 5000,
    MAX_INTENTOS: 3
};

// Usar en tu código
fetch(CONFIG.API_URL)
    .then(response => response.json())
    .catch(error => console.error(error));
```

### Formulario dinámico
```javascript
const formulario = document.getElementById('miFormulario');
let datosUsuario = {};

formulario.addEventListener('submit', (e) => {
    e.preventDefault();
    
    // let para datos que cambian
    let nombre = formulario.nombre.value;
    let email = formulario.email.value;
    
    // Actualizar objeto
    datosUsuario = { nombre, email };
    console.log(datosUsuario);
});
```

## 10. Reglas de Oro

### 🎯 Qué usar y cuándo:

1. **`const` por defecto** - Para todo lo que no va a cambiar
2. **`let` cuando necesites reasignar** - Contadores, acumuladores, etc.
3. **`var` NUNCA** - Está obsoleto y causa problemas

### 🎯 Checklist de buenas prácticas:

- ✅ Usa nombres descriptivos
- ✅ Declara variables al principio del scope
- ✅ Una variable por línea
- ✅ Inicializa variables cuando sea posible
- ✅ Usa `const` para objetos/arrays que no reasignas
- ✅ Agrupa declaraciones relacionadas

## 11. Cheat Sheet

```javascript
// Declaraciones básicas
const CONSTANTE = 'No cambia';
let variable = 'Puede cambiar';

// Múltiples variables
let nombre = 'Juan', edad = 30, activo = true;

// Desestructuración
const { nombre, edad } = persona;
const [primero, segundo] = array;

// Valores por defecto
let mensaje = usuario.mensaje || 'Mensaje por defecto';

// Operador nullish coalescing
let valor = datos?.campo ?? 'Sin datos';
```

## Resumen Ultra-Rápido

- **`const`**: Para constantes y objetos/arrays que no reasignas
- **`let`**: Para variables que cambian de valor  
- **`var`**: ❌ No usar nunca
- **Nombres**: Descriptivos, camelCase, sin números al inicio
- **Scope**: `let` y `const` tienen scope de bloque
- **Buena práctica**: Declara siempre, usa `const` por defecto