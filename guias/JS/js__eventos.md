
# EVENTOS EN JS 

Existen **tres maneras principales** de definir eventos en HTML con JavaScript vanilla: usando atributos HTML (inline), asignando funciones a propiedades del DOM, y empleando el método `addEventListener`. Cada método tiene ventajas y desventajas, y se recomienda para distintos tipos de proyectos y necesidades.[^1][^5][^9]

## Usar atributos HTML (inline)

Define el evento directamente en el HTML mediante el atributo correspondiente (ejemplo: `onclick`). Es sencillo pero mezcla lógica y presentación, dificultando el mantenimiento del código.[^2][^3][^9]

```html
<button onclick="alert('Hola!')">Click aquí</button>
```

- Rápido para pruebas y ejemplos simples.[^3]
- No permite separar lógica y estructura de forma óptima.[^2]


## Propiedades del DOM

Consiste en asignar directamente una función al evento como propiedad JavaScript del elemento. Esto permite mejor separación de código, pero solo puede haber un manejador por evento con este método.[^5]

```js
const btn = document.getElementById('btn');
btn.onclick = function() {
  alert('Click detectado');
};
```

- Mejor para separar JS y HTML.
- Solo puede existir una función asignada por evento usando este método.[^5]


## addEventListener

El método más flexible y moderno. Permite asignar múltiples funciones al mismo evento y mayor control sobre su funcionamiento. Es la forma recomendada para producción.[^4][^9][^5]

```js
const btn = document.getElementById('btn');
btn.addEventListener('click', function() {
  alert('Usando addEventListener');
});
```

- Permite varios manejadores.
- Control avanzado (captura, burbuja, remover eventos).
- Permite usar objetos como manejadores de evento, no solo funciones.[^5]


## Tabla comparativa

| Método | Facilidad | Múltiples handlers | Separación HTML/JS | Recomendado producción |
| :-- | :-- | :-- | :-- | :-- |
| Atributo HTML | Alta | No | No | No [^2] |
| Propiedad DOM | Media | No | Sí | Parcial |
| addEventListener | Media | Sí | Sí | Sí [^5] |

## Resumen

- **Atributos HTML**: rápido, pero difícil de mantener.
- **Propiedades del DOM**: mejor organización, solo un handler.
- **addEventListener**: más flexible, profesional y recomendado para proyectos reales.[^9][^1][^5]
<span style="display:none">[^10][^6][^7][^8]</span>

### [ejemplo](js__eventos_ejemplo.html)


<div style="text-align: center">⁂</div>

[^1]: https://desarrolloweb.com/articulos/1235.php

[^2]: https://lenguajejs.com/eventos/introduccion/eventos-html/

[^3]: https://www.digitallearning.es/intro-programacion-js/eventos-javascript.html

[^4]: https://lenguajejs.com/eventos/introduccion/eventos-javascript/

[^5]: https://es.javascript.info/introduction-browser-events

[^6]: https://www.youtube.com/watch?v=kzOh8DQ7wrs

[^7]: http://nachoiborraies.github.io/javascript/md/es/02b.html

[^8]: https://www.paradigmadigital.com/dev/entendiendo-delegacion-eventos-javascript/

[^9]: https://lenguajehtml.com/html/interactivas/eventos-html/

[^10]: https://developer.mozilla.org/es/docs/Learn_web_development/Core/Scripting/Events

