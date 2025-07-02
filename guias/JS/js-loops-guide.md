# Guía Rápida: Bucles Básicos en JavaScript

## 1. Tipos de Bucles Básicos

| Bucle | Uso principal | Cuándo usarlo |
|-------|---------------|---------------|
| `for` | Número conocido de iteraciones | Contadores, rangos, arrays |
| `while` | Condición verdadera | No sabes cuántas veces |
| `do...while` | Al menos una ejecución | Validar entrada, menús |
| `for...in` | Propiedades de objetos | Iterar objetos |
| `for...of` | Elementos iterables | Arrays, strings, NodeLists |

## 2. Bucle `for` - El Más Común

### Sintaxis básica
```javascript
for (inicialización; condición; incremento) {
    // Código que se repite
}
```

### Ejemplo básico
```javascript
// Contar del 1 al 5
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
// Imprime: 1, 2, 3, 4, 5
```

### Ejemplos prácticos
```javascript
// Tabla de multiplicar
for (let i = 1; i <= 10; i++) {
    console.log(`5 x ${i} = ${5 * i}`);
}

// Recorrer un array
let frutas = ['manzana', 'banana', 'naranja'];
for (let i = 0; i < frutas.length; i++) {
    console.log(`${i}: ${frutas[i]}`);
}

// Contar hacia atrás
for (let i = 10; i >= 1; i--) {
    console.log(i);
}
console.log('¡Despegue!');
```

### Variaciones del incremento
```javascript
// De 2 en 2
for (let i = 0; i <= 10; i += 2) {
    console.log(i); // 0, 2, 4, 6, 8, 10
}

// De 3 en 3 hacia atrás
for (let i = 15; i >= 0; i -= 3) {
    console.log(i); // 15, 12, 9, 6, 3, 0
}

// Multiplicar por 2
for (let i = 1; i <= 16; i *= 2) {
    console.log(i); // 1, 2, 4, 8, 16
}
```

## 3. Bucle `while` - Mientras Sea Verdadero

### Sintaxis básica
```javascript
while (condición) {
    // Código que se repite
    // ¡No olvides modificar la condición!
}
```

### Ejemplos básicos
```javascript
// Contador básico
let i = 1;
while (i <= 5) {
    console.log(i);
    i++; // ¡IMPORTANTE! Sin esto es bucle infinito
}

// Buscar en un array
let nombres = ['Ana', 'Juan', 'Pedro', 'María'];
let index = 0;
while (index < nombres.length && nombres[index] !== 'Pedro') {
    index++;
}
console.log(index < nombres.length ? `Encontrado en posición ${index}` : 'No encontrado');
```

### Casos prácticos con `while`
```javascript
// Validar entrada del usuario (simulado)
let password = '';
while (password.length < 8) {
    password = prompt('Ingresa una contraseña (mín. 8 caracteres):');
    if (password.length < 8) {
        alert('Contraseña muy corta');
    }
}

// Juego de adivinanza
let numeroSecreto = 7;
let intento = 0;
while (intento !== numeroSecreto) {
    intento = parseInt(prompt('Adivina el número (1-10):'));
    if (intento < numeroSecreto) {
        alert('Muy bajo');
    } else if (intento > numeroSecreto) {
        alert('Muy alto');
    }
}
alert('¡Correcto!');
```

## 4. Bucle `do...while` - Ejecuta Al Menos Una Vez

### Sintaxis básica
```javascript
do {
    // Código que se ejecuta al menos una vez
} while (condición);
```

### Ejemplos
```javascript
// Menú que se muestra al menos una vez
let opcion;
do {
    opcion = prompt(`
    Selecciona una opción:
    1. Ver perfil
    2. Configuración
    3. Salir
    `);
    
    switch (opcion) {
        case '1':
            alert('Mostrando perfil...');
            break;
        case '2':
            alert('Abriendo configuración...');
            break;
        case '3':
            alert('¡Hasta luego!');
            break;
        default:
            alert('Opción no válida');
    }
} while (opcion !== '3');

// Validar entrada (siempre pregunta al menos una vez)
let numero;
do {
    numero = parseInt(prompt('Ingresa un número entre 1 y 10:'));
} while (numero < 1 || numero > 10 || isNaN(numero));
```

## 5. Bucle `for...in` - Para Objetos

### Sintaxis básica
```javascript
for (let propiedad in objeto) {
    // Código para cada propiedad
}
```

### Ejemplos
```javascript
let persona = {
    nombre: 'Juan',
    edad: 30,
    ciudad: 'Madrid',
    profesion: 'Programador'
};

// Recorrer propiedades del objeto
for (let clave in persona) {
    console.log(`${clave}: ${persona[clave]}`);
}
// Imprime:
// nombre: Juan
// edad: 30
// ciudad: Madrid
// profesion: Programador

// Contar propiedades
let contador = 0;
for (let prop in persona) {
    contador++;
}
console.log(`El objeto tiene ${contador} propiedades`);
```

## 6. Bucle `for...of` - Para Elementos

### Sintaxis básica
```javascript
for (let elemento of iterable) {
    // Código para cada elemento
}
```

### Ejemplos
```javascript
// Recorrer array
let colores = ['rojo', 'verde', 'azul'];
for (let color of colores) {
    console.log(color);
}

// Recorrer string
let palabra = 'Hola';
for (let letra of palabra) {
    console.log(letra); // H, o, l, a
}

// Con índice usando entries()
for (let [indice, valor] of colores.entries()) {
    console.log(`${indice}: ${valor}`);
}
```

## 7. Control de Bucles: `break` y `continue`

### `break` - Salir del bucle
```javascript
// Buscar el primer número par
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log(`Primer número par: ${i}`);
        break; // Sale del bucle
    }
}

// En while
let contador = 0;
while (true) { // Bucle infinito controlado
    contador++;
    if (contador === 5) {
        break; // Sale cuando contador sea 5
    }
    console.log(contador);
}
```

### `continue` - Saltar iteración
```javascript
// Imprimir solo números impares
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        continue; // Salta al siguiente número
    }
    console.log(i); // Solo imprime impares: 1, 3, 5, 7, 9
}

// Filtrar elementos
let palabras = ['hola', '', 'mundo', '', 'JavaScript'];
for (let palabra of palabras) {
    if (palabra === '') {
        continue; // Salta strings vacíos
    }
    console.log(palabra.toUpperCase());
}
```

## 8. Bucles Anidados

### Ejemplo básico
```javascript
// Tabla de multiplicar completa
for (let i = 1; i <= 3; i++) {
    console.log(`Tabla del ${i}:`);
    for (let j = 1; j <= 5; j++) {
        console.log(`${i} x ${j} = ${i * j}`);
    }
    console.log('---');
}
```

### Ejemplos prácticos
```javascript
// Crear una matriz
let matriz = [];
for (let fila = 0; fila < 3; fila++) {
    matriz[fila] = [];
    for (let columna = 0; columna < 3; columna++) {
        matriz[fila][columna] = fila * 3 + columna + 1;
    }
}
console.log(matriz); // [[1,2,3], [4,5,6], [7,8,9]]

// Buscar en matriz
let encontrado = false;
let buscar = 5;

for (let i = 0; i < matriz.length && !encontrado; i++) {
    for (let j = 0; j < matriz[i].length && !encontrado; j++) {
        if (matriz[i][j] === buscar) {
            console.log(`Encontrado ${buscar} en posición [${i}][${j}]`);
            encontrado = true;
        }
    }
}
```

## 9. Errores Comunes

### ❌ Error 1: Bucle infinito en `while`
```javascript
// ❌ Bucle infinito - nunca cambia la condición
let i = 0;
while (i < 5) {
    console.log(i);
    // ¡Falta i++!
}

// ✅ Versión correcta
let i = 0;
while (i < 5) {
    console.log(i);
    i++; // Modifica la condición
}
```

### ❌ Error 2: Confundir `=` con `===` en condiciones
```javascript
// ❌ Asignación en lugar de comparación
for (let i = 0; i = 5; i++) { // Asigna 5 a i
    console.log(i);
}

// ✅ Comparación correcta
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

### ❌ Error 3: Modificar array mientras lo recorres
```javascript
let numeros = [1, 2, 3, 4, 5];

// ❌ Problemático - modifica el array durante iteración
for (let i = 0; i < numeros.length; i++) {
    if (numeros[i] % 2 === 0) {
        numeros.splice(i, 1); // Elimina elemento
        // Esto cambia los índices
    }
}

// ✅ Recorrer hacia atrás para eliminar
for (let i = numeros.length - 1; i >= 0; i--) {
    if (numeros[i] % 2 === 0) {
        numeros.splice(i, 1);
    }
}
```

### ❌ Error 4: Scope de variables en bucles
```javascript
// ❌ Problema con var
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Imprime: 3, 3, 3
}

// ✅ Solución con let
for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // Imprime: 0, 1, 2
}
```

## 10. Casos Prácticos

### Validación de formulario
```javascript
function validarFormulario(campos) {
    let errores = [];
    
    for (let campo in campos) {
        if (!campos[campo] || campos[campo].trim() === '') {
            errores.push(`El campo ${campo} es requerido`);
        }
    }
    
    return errores.length === 0;
}

// Uso
let datosFormulario = {
    nombre: 'Juan',
    email: '',
    telefono: '123456789'
};

if (!validarFormulario(datosFormulario)) {
    console.log('Formulario inválido');
}
```

### Generador de contraseñas
```javascript
function generarPassword(longitud) {
    let caracteres = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
    let password = '';
    
    for (let i = 0; i < longitud; i++) {
        let indiceAleatorio = Math.floor(Math.random() * caracteres.length);
        password += caracteres[indiceAleatorio];
    }
    
    return password;
}

console.log(generarPassword(8)); // Ej: "aB3xY9mN"
```

### Calculadora de estadísticas
```javascript
function calcularEstadisticas(numeros) {
    let suma = 0;
    let max = numeros[0];
    let min = numeros[0];
    
    for (let i = 0; i < numeros.length; i++) {
        suma += numeros[i];
        
        if (numeros[i] > max) {
            max = numeros[i];
        }
        
        if (numeros[i] < min) {
            min = numeros[i];
        }
    }
    
    return {
        suma: suma,
        promedio: suma / numeros.length,
        maximo: max,
        minimo: min
    };
}

let notas = [85, 92, 78, 96, 87];
console.log(calcularEstadisticas(notas));
```

## 11. Rendimiento y Optimización

### Optimizar bucles `for`
```javascript
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// ❌ Menos eficiente - calcula length en cada iteración
for (let i = 0; i < array.length; i++) {
    console.log(array[i]);
}

// ✅ Más eficiente - calcula length una vez
for (let i = 0, len = array.length; i < len; i++) {
    console.log(array[i]);
}
```

### Evitar trabajo innecesario
```javascript
// ❌ Búsqueda ineficiente
let nombres = ['Ana', 'Juan', 'Pedro', 'María'];
let encontrado = false;

for (let i = 0; i < nombres.length; i++) {
    if (nombres[i] === 'Pedro') {
        encontrado = true;
        // Sigue buscando innecesariamente
    }
}

// ✅ Búsqueda eficiente con break
for (let i = 0; i < nombres.length; i++) {
    if (nombres[i] === 'Pedro') {
        encontrado = true;
        break; // Sale inmediatamente
    }
}
```

## 12. Buenas Prácticas

### 🎯 Cuándo usar cada bucle:

- **`for`**: Cuando sabes exactamente cuántas veces iterar
- **`while`**: Cuando la condición puede cambiar durante la ejecución
- **`do...while`**: Cuando necesitas ejecutar al menos una vez
- **`for...in`**: Para recorrer propiedades de objetos
- **`for...of`**: Para recorrer elementos de arrays/strings

### 🎯 Consejos generales:

```javascript
// ✅ Variables descriptivas
for (let indiceUsuario = 0; indiceUsuario < usuarios.length; indiceUsuario++) {
    // Código
}

// ✅ Evitar bucles anidados profundos
// Si necesitas más de 3 niveles, considera refactorizar

// ✅ Usar break y continue apropiadamente
for (let producto of productos) {
    if (!producto.activo) continue;
    if (producto.precio > presupuesto) break;
    
    procesarProducto(producto);
}

// ✅ Inicializar variables fuera del bucle cuando sea posible
let total = 0;
for (let precio of precios) {
    total += precio;
}
```

## 13. Cheat Sheet

```javascript
// For básico
for (let i = 0; i < 10; i++) { }

// While básico
while (condicion) { 
    // modificar condicion
}

// Do-while
do { } while (condicion);

// For-in (objetos)
for (let prop in objeto) { }

// For-of (arrays/iterables)
for (let elemento of array) { }

// Control
break;    // Sale del bucle
continue; // Salta a siguiente iteración

// Patrones comunes
for (let i = array.length - 1; i >= 0; i--) { } // Hacia atrás
for (let i = 0; i < array.length; i += 2) { }   // De 2 en 2
```

## Resumen Ultra-Rápido

- **`for`**: Ideal para contadores y arrays (conoces las iteraciones)
- **`while`**: Perfecto cuando no sabes cuántas veces (condición dinámica)
- **`do...while`**: Garantiza al menos una ejecución
- **`for...in`**: Para objetos (propiedades)
- **`for...of`**: Para arrays y strings (elementos)
- **Siempre modifica la condición** en `while` para evitar bucles infinitos
- **Usa `break`** para salir temprano
- **Usa `continue`** para saltar iteraciones
- **Cuidado con el scope** - usa `let` en lugar de `var`