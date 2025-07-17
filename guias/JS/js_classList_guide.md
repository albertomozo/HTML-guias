# Guía Rápida: classList en JavaScript

## ¿Qué es classList?

`classList` es una propiedad de los elementos DOM que devuelve una colección de las clases CSS del elemento. Es una interfaz más moderna y conveniente que manipular directamente la propiedad `className`.

## Métodos principales

### 1. `add()` - Agregar clases

```javascript
const elemento = document.getElementById('miElemento');

// Agregar una sola clase
elemento.classList.add('nueva-clase');

// Agregar múltiples clases
elemento.classList.add('clase1', 'clase2', 'clase3');
```

### 2. `remove()` - Eliminar clases

```javascript
// Eliminar una sola clase
elemento.classList.remove('clase-a-eliminar');

// Eliminar múltiples clases
elemento.classList.remove('clase1', 'clase2');
```

### 3. `toggle()` - Alternar clases

```javascript
// Si la clase existe, la elimina; si no existe, la agrega
elemento.classList.toggle('activo');

// Con segundo parámetro (fuerza el comportamiento)
elemento.classList.toggle('visible', true);  // Siempre agrega
elemento.classList.toggle('visible', false); // Siempre elimina
```

### 4. `contains()` - Verificar si tiene una clase

```javascript
if (elemento.classList.contains('activo')) {
    console.log('El elemento tiene la clase activo');
}

// Ejemplo práctico
const boton = document.querySelector('.btn');
if (boton.classList.contains('deshabilitado')) {
    return; // No hacer nada si está deshabilitado
}
```

### 5. `replace()` - Reemplazar una clase

```javascript
// Reemplaza 'clase-vieja' con 'clase-nueva'
elemento.classList.replace('clase-vieja', 'clase-nueva');

// Retorna true si se hizo el reemplazo, false si no
const reemplazado = elemento.classList.replace('inexistente', 'nueva');
```

## Propiedades útiles

### `length` - Número de clases

```javascript
console.log(elemento.classList.length); // Número de clases que tiene
```

### `value` - String con todas las clases

```javascript
console.log(elemento.classList.value); // "clase1 clase2 clase3"
```

## Ejemplos prácticos

### Ejemplo 1: Sistema de tabs

```javascript
const tabs = document.querySelectorAll('.tab');
const contenidos = document.querySelectorAll('.contenido');

tabs.forEach((tab, index) => {
    tab.addEventListener('click', () => {
        // Remover clase activa de todos los tabs
        tabs.forEach(t => t.classList.remove('activo'));
        contenidos.forEach(c => c.classList.remove('mostrar'));
        
        // Agregar clase activa al tab clickeado
        tab.classList.add('activo');
        contenidos[index].classList.add('mostrar');
    });
});
```

### Ejemplo 2: Modal

```javascript
const modal = document.getElementById('modal');
const abrirBtn = document.getElementById('abrir-modal');
const cerrarBtn = document.getElementById('cerrar-modal');

abrirBtn.addEventListener('click', () => {
    modal.classList.add('mostrar');
    document.body.classList.add('modal-abierto');
});

cerrarBtn.addEventListener('click', () => {
    modal.classList.remove('mostrar');
    document.body.classList.remove('modal-abierto');
});
```

### Ejemplo 3: Toggle de tema oscuro

```javascript
const toggleTema = document.getElementById('toggle-tema');
const body = document.body;

toggleTema.addEventListener('click', () => {
    const esOscuro = body.classList.toggle('tema-oscuro');
    
    // Cambiar texto del botón según el estado
    toggleTema.textContent = esOscuro ? 'Modo Claro' : 'Modo Oscuro';
});
```

### Ejemplo 4: Validación de formulario

```javascript
const input = document.getElementById('email');
const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

input.addEventListener('input', () => {
    const valor = input.value;
    
    if (emailRegex.test(valor)) {
        input.classList.remove('error');
        input.classList.add('valido');
    } else {
        input.classList.remove('valido');
        input.classList.add('error');
    }
});
```

## Ventajas sobre className

```javascript
// ❌ Forma antigua con className
elemento.className += ' nueva-clase'; // Puede duplicar clases
elemento.className = elemento.className.replace('vieja-clase', '');

// ✅ Forma moderna con classList
elemento.classList.add('nueva-clase');
elemento.classList.remove('vieja-clase');
```

## Iteración sobre classList

```javascript
// Recorrer todas las clases
elemento.classList.forEach(clase => {
    console.log(clase);
});

// Convertir a array
const clasesArray = Array.from(elemento.classList);
console.log(clasesArray); // ['clase1', 'clase2', 'clase3']
```

## Consejos importantes

- `classList` no duplica clases automáticamente
- Los métodos `add()` y `remove()` no lanzan errores si la clase no existe
- `toggle()` retorna `true` si agrega la clase, `false` si la elimina
- Es compatible con todos los navegadores modernos
- Es más seguro y legible que manipular `className` directamente