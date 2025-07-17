
### 1. **Inclusión del CDN**
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
```

### 2. **Estructura básica de una animación**
```javascript
anime({
    targets: '.mi-elemento',    // Selector del elemento
    translateX: 250,            // Propiedad a animar
    duration: 2000,             // Duración en milisegundos
    easing: 'easeInOutQuad'     // Tipo de easing
});
```

### 3. **Ejemplos incluidos:**

- **Animación básica**: Movimiento y rotación
- **Escalado y color**: Cambio de tamaño y color de fondo
- **Animación de texto**: Fade in con movimiento
- **Stagger**: Animación escalonada de múltiples elementos
- **Timeline**: Secuencia de animaciones encadenadas

### 4. **Propiedades principales:**
- `targets`: Elemento(s) a animar
- `duration`: Duración de la animación
- `easing`: Curva de animación
- `delay`: Retraso antes de iniciar
- `loop`: Número de repeticiones
- `direction`: Dirección (normal, reverse, alternate)

### 5. **Funciones útiles:**
- `anime.stagger()`: Para retrasos escalonados
- `anime.timeline()`: Para secuencias complejas
- Callbacks como `complete`, `update`, `begin`

Ejemplo en [anime](../../ejemplos/js/anime_js_example.html)