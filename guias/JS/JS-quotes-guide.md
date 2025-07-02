# Guía Completa: Comillas en JavaScript

## 1. Tipos de Comillas en JavaScript

JavaScript tiene **tres tipos** de comillas para trabajar con strings:

- **Comillas simples** (`'`)
- **Comillas dobles** (`"`)
- **Template literals** (`` ` ``)

## 2. Comillas Simples (`'`)

### Uso básico
```javascript
let nombre = 'Juan';
let mensaje = 'Hola mundo';
console.log('Este es un texto con comillas simples');
```

### ¿Cuándo usarlas?
- Para strings simples sin variables
- Cuando el texto contiene comillas dobles
- Por preferencia de estilo de código

### Ejemplo con comillas dobles dentro
```javascript
let frase = 'Él dijo: "Buenos días" y se fue';
console.log(frase); // Él dijo: "Buenos días" y se fue
```

## 3. Comillas Dobles (`"`)

### Uso básico
```javascript
let apellido = "García";
let saludo = "¡Hola!";
console.log("Este es un texto con comillas dobles");
```

### ¿Cuándo usarlas?
- Funcionalmente igual que las simples
- Cuando el texto contiene comillas simples
- En JSON (obligatorio)

### Ejemplo con comillas simples dentro
```javascript
let frase = "No pudo decir 'adiós' porque se emocionó";
console.log(frase); // No pudo decir 'adiós' porque se emocionó
```

## 4. Template Literals (`` ` ``)

### ¿Qué son?
Las **template literals** usan backticks (`` ` ``) y tienen superpoderes:
- Interpolación de variables
- Strings multilínea
- Expresiones JavaScript embebidas

### Interpolación de variables
```javascript
let nombre = 'Ana';
let edad = 25;

// ❌ Forma antigua (concatenación)
let presentacion1 = 'Hola, soy ' + nombre + ' y tengo ' + edad + ' años';

// ✅ Forma moderna (template literal)
let presentacion2 = `Hola, soy ${nombre} y tengo ${edad} años`;

console.log(presentacion2); // Hola, soy Ana y tengo 25 años
```

### Strings multilínea
```javascript
// ❌ Con comillas normales (necesitas \n)
let poema1 = 'Roses are red\nViolets are blue\nJavaScript is awesome\nAnd so are you';

// ✅ Con template literals (saltos de línea naturales)
let poema2 = `Roses are red
Violets are blue
JavaScript is awesome
And so are you`;

console.log(poema2);
```

### Expresiones dentro de template literals
```javascript
let a = 10;
let b = 5;

let resultado = `La suma de ${a} + ${b} es ${a + b}`;
console.log(resultado); // La suma de 10 + 5 es 15

// Puedes usar cualquier expresión JavaScript
let usuario = { nombre: 'Pedro', edad: 30 };
let info = `Usuario: ${usuario.nombre.toUpperCase()}, Edad: ${usuario.edad}`;
console.log(info); // Usuario: PEDRO, Edad: 30
```

## 5. Escape de Caracteres

### ¿Qué pasa si necesitas usar el mismo tipo de comilla dentro del string?

#### Opción 1: Usar el carácter de escape (`\`)
```javascript
// Comillas simples escapadas
let frase1 = 'Él dijo: \'Hasta luego\'';

// Comillas dobles escapadas  
let frase2 = "Ella respondió: \"De acuerdo\"";

// Backticks escapados
let codigo = `El comando es: \`npm install\``;
```

#### Opción 2: Alternar tipos de comillas
```javascript
// Más fácil de leer
let frase1 = "Él dijo: 'Hasta luego'";
let frase2 = 'Ella respondió: "De acuerdo"';
```

## 6. Casos Prácticos y Ejemplos

### Caso 1: Creando HTML dinámicamente
```javascript
let titulo = 'Mi Página Web';
let contenido = 'Bienvenido a mi sitio';

// Con template literals es mucho más claro
let html = `
<div class="container">
    <h1>${titulo}</h1>
    <p>${contenido}</p>
    <button onclick="alert('¡Hola!')">Saludar</button>
</div>
`;
```

### Caso 2: URLs dinámicas
```javascript
let usuario = 'juan123';
let pagina = 2;

let url = `https://api.ejemplo.com/usuarios/${usuario}/posts?page=${pagina}`;
console.log(url); // https://api.ejemplo.com/usuarios/juan123/posts?page=2
```

### Caso 3: Mensajes condicionales
```javascript
let nombre = 'María';
let hora = 14;

let saludo = `${hora < 12 ? 'Buenos días' : 'Buenas tardes'}, ${nombre}!`;
console.log(saludo); // Buenas tardes, María!
```

## 7. Errores Comunes y Cómo Evitarlos

### ❌ Error 1: Mezclar tipos de comillas sin escape
```javascript
// Esto da error
let mal = 'Él dijo: 'Hola''; // SyntaxError
```

### ✅ Solución
```javascript
let bien1 = 'Él dijo: "Hola"';
let bien2 = "Él dijo: 'Hola'";
let bien3 = 'Él dijo: \'Hola\'';
```

### ❌ Error 2: No usar template literals para concatenación compleja
```javascript
// Difícil de leer y mantener
let mensaje = 'Hola ' + nombre + ', tienes ' + emails.length + ' emails nuevos. ' + 
              'Tu último login fue el ' + ultimoLogin + '.';
```

### ✅ Solución
```javascript
let mensaje = `Hola ${nombre}, tienes ${emails.length} emails nuevos. 
               Tu último login fue el ${ultimoLogin}.`;
```

## 8. Mejores Prácticas

### 🎯 Cuándo usar cada tipo:

1. **Comillas simples (`'`)**: Para strings simples y estáticos
2. **Comillas dobles (`"`)**: Para JSON o cuando prefieras este estilo
3. **Template literals (`` ` ``)**: Para strings con variables, expresiones o multilínea

### 🎯 Recomendaciones:
- Sé consistente en tu proyecto (elige un estilo y manténlo)
- Usa template literals cuando necesites interpolar variables
- Para HTML dinámico, siempre usa template literals
- En equipos, establece reglas con ESLint

## 9. Ejercicios Prácticos

### Ejercicio 1: Convertir concatenación a template literal
```javascript
// Convierte esto:
let usuario = 'Ana';
let puntos = 150;
let mensaje = 'Felicidades ' + usuario + ', has ganado ' + puntos + ' puntos!';

// A esto:
let mensajeMejorado = `Felicidades ${usuario}, has ganado ${puntos} puntos!`;
```

### Ejercicio 2: Crear una función que genere HTML
```javascript
function crearTarjetaUsuario(nombre, email, edad) {
    return `
    <div class="tarjeta-usuario">
        <h3>${nombre}</h3>
        <p>Email: ${email}</p>
        <p>Edad: ${edad} años</p>
        <p>Estado: ${edad >= 18 ? 'Adulto' : 'Menor'}</p>
    </div>
    `;
}

console.log(crearTarjetaUsuario('Carlos', 'carlos@email.com', 25));
```

## 10. Resumen

| Tipo | Símbolo | Mejor uso | Superpoderes |
|------|---------|-----------|--------------|
| Simples | `'` | Strings simples | Ninguno especial |
| Dobles | `"` | Strings simples, JSON | Ninguno especial |
| Template | `` ` `` | Variables, multilínea | ${interpolación}, saltos de línea |

**Regla de oro**: Si tu string tiene variables o necesita saltos de línea, usa template literals. Para todo lo demás, usa comillas simples o dobles según tu preferencia.