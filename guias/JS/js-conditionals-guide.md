# Guía Rápida: Sentencias de Decisión en JavaScript

## 1. Tipos de Sentencias de Decisión

| Sentencia | Uso | Cuándo usarla |
|-----------|-----|---------------|
| `if` | Condición simple | Una sola condición |
| `if...else` | Dos opciones | Verdadero o falso |
| `if...else if...else` | Múltiples condiciones | Varias opciones |
| `switch` | Comparar un valor | Muchas opciones específicas |
| Operador ternario `?:` | Condición inline | Asignaciones simples |
| Operadores lógicos | Evaluación corta | Validaciones rápidas |

## 2. `if` - Condición Simple

### Sintaxis básica
```javascript
if (condicion) {
    // Código si es verdadero
}
```

### Ejemplos
```javascript
let edad = 18;

if (edad >= 18) {
    console.log('Eres mayor de edad');
}

// Con múltiples líneas
if (usuario.activo) {
    mostrarDashboard();
    registrarAcceso();
    actualizarUltimoLogin();
}
```

## 3. `if...else` - Dos Opciones

### Sintaxis básica
```javascript
if (condicion) {
    // Si es verdadero
} else {
    // Si es falso
}
```

### Ejemplos
```javascript
let hora = 14;

if (hora < 12) {
    console.log('Buenos días');
} else {
    console.log('Buenas tardes');
}

// Con funciones
if (validarFormulario()) {
    enviarDatos();
} else {
    mostrarErrores();
}
```

## 4. `if...else if...else` - Múltiples Condiciones

### Sintaxis básica
```javascript
if (condicion1) {
    // Opción 1
} else if (condicion2) {
    // Opción 2
} else if (condicion3) {
    // Opción 3
} else {
    // Opción por defecto
}
```

### Ejemplos
```javascript
let nota = 85;

if (nota >= 90) {
    console.log('Excelente');
} else if (nota >= 80) {
    console.log('Muy bien');
} else if (nota >= 70) {
    console.log('Bien');
} else if (nota >= 60) {
    console.log('Suficiente');
} else {
    console.log('Insuficiente');
}
```

## 5. `switch` - Múltiples Opciones Específicas

### Sintaxis básica
```javascript
switch (expresion) {
    case valor1:
        // Código para valor1
        break;
    case valor2:
        // Código para valor2
        break;
    default:
        // Código por defecto
}
```

### Ejemplos básicos
```javascript
let diaSemana = 'lunes';

switch (diaSemana) {
    case 'lunes':
        console.log('Inicio de semana');
        break;
    case 'martes':
    case 'miércoles':
    case 'jueves':
        console.log('Mitad de semana');
        break;
    case 'viernes':
        console.log('¡Por fin viernes!');
        break;
    case 'sábado':
    case 'domingo':
        console.log('Fin de semana');
        break;
    default:
        console.log('Día no válido');
}
```

### ⚠️ IMPORTANTE: El `break`
```javascript
// ❌ Sin break - "fall through"
let numero = 2;

switch (numero) {
    case 1:
        console.log('Uno');
    case 2:
        console.log('Dos');
    case 3:
        console.log('Tres');
}
// Imprime: "Dos" y "Tres"

// ✅ Con break correcto
switch (numero) {
    case 1:
        console.log('Uno');
        break;
    case 2:
        console.log('Dos');
        break;
    case 3:
        console.log('Tres');
        break;
}
// Imprime solo: "Dos"
```

## 6. Operador Ternario `?:` - Condición Inline

### Sintaxis básica
```javascript
condicion ? valorSiVerdadero : valorSiFalso
```

### Ejemplos simples
```javascript
let edad = 20;
let mensaje = edad >= 18 ? 'Adulto' : 'Menor';
console.log(mensaje); // 'Adulto'

// En funciones
function obtenerSaludo(hora) {
    return hora < 12 ? 'Buenos días' : 'Buenas tardes';
}

// En JSX (React)
<div className={activo ? 'activo' : 'inactivo'}>
    {usuario ? `Hola ${usuario.nombre}` : 'Iniciar sesión'}
</div>
```

### Ternarios anidados (úsalos con cuidado)
```javascript
let temperatura = 25;

let clima = temperatura > 30 ? 'Calor' : 
            temperatura > 20 ? 'Templado' : 
            temperatura > 10 ? 'Fresco' : 'Frío';

// Mejor como if...else if para mayor claridad
```

## 7. Operadores Lógicos para Decisiones

### AND (`&&`) - Evaluación corta
```javascript
// Si usuario existe, mostrar nombre
usuario && console.log(usuario.nombre);

// Ejecutar función solo si condición es verdadera
estaLogueado && mostrarDashboard();

// En React
{productos.length > 0 && <ListaProductos productos={productos} />}
```

### OR (`||`) - Valores por defecto
```javascript
// Valor por defecto
let nombre = usuario.nombre || 'Anónimo';

// Llamar función si existe
callback && callback();

// Múltiples opciones
let color = usuario.colorPreferido || configuracion.colorDefecto || 'azul';
```

### Nullish Coalescing (`??`) - Solo para null/undefined
```javascript
let valor = datos?.campo ?? 'Sin datos';

// Diferencia con ||
let numero = 0;
console.log(numero || 10);  // 10 (porque 0 es falsy)
console.log(numero ?? 10);  // 0 (porque 0 no es null/undefined)
```

## 8. Valores Truthy y Falsy

### Valores Falsy (se evalúan como falso)
```javascript
// Estos valores son falsy:
if (false) { }      // false
if (0) { }          // 0
if (-0) { }         // -0
if (0n) { }         // BigInt 0
if ("") { }         // string vacío
if (null) { }       // null
if (undefined) { }  // undefined
if (NaN) { }        // NaN

// Ninguno ejecutará el código
```

### Valores Truthy (todo lo demás)
```javascript
// Estos valores son truthy:
if (true) { }       // true
if (1) { }          // números diferentes de 0
if ("hola") { }     // strings no vacíos
if ([]) { }         // arrays (incluso vacíos)
if ({}) { }         // objetos (incluso vacíos)
if (function(){}) { } // funciones
```

## 9. Comparadores y Operadores

### Comparadores de igualdad
```javascript
// ❌ Evitar == (comparación débil)
console.log(5 == "5");    // true (convierte tipos)
console.log(0 == false);  // true
console.log("" == 0);     // true

// ✅ Usar === (comparación estricta)
console.log(5 === "5");   // false
console.log(0 === false); // false
console.log("" === 0);    // false
```

### Comparadores relacionales
```javascript
let a = 10, b = 20;

if (a > b) { }      // Mayor que
if (a < b) { }      // Menor que
if (a >= b) { }     // Mayor o igual
if (a <= b) { }     // Menor o igual
if (a !== b) { }    // Diferente (estricto)
```

## 10. Errores Comunes

### ❌ Error 1: Asignación en lugar de comparación
```javascript
let x = 5;

// ❌ Asignación (siempre true)
if (x = 10) {
    console.log('Esto siempre se ejecuta');
}

// ✅ Comparación
if (x === 10) {
    console.log('Esto solo si x es 10');
}
```

### ❌ Error 2: Comparar con == en lugar de ===
```javascript
// ❌ Problemático
if (edad == "18") { } // true si edad es 18 o "18"

// ✅ Correcto  
if (edad === 18) { }  // solo true si edad es número 18
```

### ❌ Error 3: Olvidar break en switch
```javascript
// ❌ Fall through no deseado
switch (opcion) {
    case 'A':
        console.log('Opción A');
    case 'B':
        console.log('Opción B'); // Se ejecuta también si opcion es 'A'
        break;
}

// ✅ Con break correcto
switch (opcion) {
    case 'A':
        console.log('Opción A');
        break;
    case 'B':
        console.log('Opción B');
        break;
}
```

### ❌ Error 4: Ternarios demasiado complejos
```javascript
// ❌ Difícil de leer
let resultado = condicion1 ? (condicion2 ? valor1 : (condicion3 ? valor2 : valor3)) : valor4;

// ✅ Mejor con if...else
let resultado;
if (condicion1) {
    if (condicion2) {
        resultado = valor1;
    } else if (condicion3) {
        resultado = valor2;
    } else {
        resultado = valor3;
    }
} else {
    resultado = valor4;
}
```

## 11. Casos Prácticos

### Validación de formulario
```javascript
function validarFormulario(datos) {
    if (!datos.nombre) {
        return { valido: false, error: 'Nombre requerido' };
    }
    
    if (!datos.email || !datos.email.includes('@')) {
        return { valido: false, error: 'Email inválido' };
    }
    
    if (datos.edad < 18) {
        return { valido: false, error: 'Debe ser mayor de edad' };
    }
    
    return { valido: true };
}
```

### Sistema de permisos
```javascript
function puedeAcceder(usuario, recurso) {
    // Múltiples condiciones con operadores lógicos
    return usuario && 
           usuario.activo && 
           (usuario.rol === 'admin' || usuario.permisos.includes(recurso));
}

// Uso
if (puedeAcceder(usuario, 'panel-admin')) {
    mostrarPanelAdmin();
} else {
    mostrarError('Sin permisos');
}
```

### Manejo de estados
```javascript
function procesarPedido(pedido) {
    switch (pedido.estado) {
        case 'pendiente':
            enviarConfirmacion(pedido);
            pedido.estado = 'procesando';
            break;
            
        case 'procesando':
            if (pedido.pago === 'completado') {
                enviarProducto(pedido);
                pedido.estado = 'enviado';
            }
            break;
            
        case 'enviado':
            if (pedido.entregado) {
                pedido.estado = 'completado';
                enviarEncuesta(pedido);
            }
            break;
            
        default:
            console.log('Estado no reconocido');
    }
}
```

## 12. Buenas Prácticas

### 🎯 Cuándo usar cada sentencia:

- **`if` simple**: Una sola condición
- **`if...else`**: Dos opciones mutuamente excluyentes  
- **`if...else if`**: 3-5 condiciones complejas
- **`switch`**: Muchas opciones específicas de un mismo valor
- **Ternario `?:`**: Asignaciones simples o JSX
- **Operadores lógicos**: Validaciones rápidas

### 🎯 Consejos de legibilidad:

```javascript
// ✅ Condiciones claras y descriptivas
if (usuario.esAdmin() && recurso.requierePermisos()) {
    permitirAcceso();
}

// ✅ Funciones para condiciones complejas
function esHorarioLaboral(hora) {
    return hora >= 9 && hora <= 17;
}

if (esHorarioLaboral(horaActual)) {
    // código
}

// ✅ Early return para evitar anidamiento
function procesarUsuario(usuario) {
    if (!usuario) return;
    if (!usuario.activo) return;
    if (!usuario.email) return;
    
    // Lógica principal aquí
    enviarBienvenida(usuario);
}
```

## 13. Cheat Sheet

```javascript
// Básicos
if (condicion) { }
if (condicion) { } else { }
if (condicion1) { } else if (condicion2) { } else { }

// Switch
switch (valor) {
    case 'a': /* código */; break;
    default: /* código */;
}

// Ternario
let resultado = condicion ? valorTrue : valorFalse;

// Operadores lógicos
condicion && ejecutar();
valor = entrada || 'defecto';
valor = entrada ?? 'defecto';

// Comparaciones
=== !== > < >= <=

// Valores falsy
false, 0, "", null, undefined, NaN
```

## Resumen Ultra-Rápido

- **`if`**: Condiciones simples
- **`switch`**: Múltiples valores específicos (no olvides `break`)
- **Ternario**: Asignaciones simples
- **Operadores lógicos**: Evaluación corta y valores por defecto
- **Usa `===` siempre**, evita `==`
- **Early return** para evitar anidamiento excesivo
- **Funciones** para condiciones complejas