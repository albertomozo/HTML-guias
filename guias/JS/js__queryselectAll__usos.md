<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Ejemplos de funcionalidades típicas cojn elemntos seleccionados con queryselectall de JS

Al usar **querySelectorAll** en JavaScript, se obtienen *todas las coincidencias* con un selector CSS, permitiendo manipular múltiples elementos del DOM de manera eficiente y flexible. Aquí tienes ejemplos de funcionalidades típicas y patrones de uso:

### Ejemplos de funcionalidades típicas con `querySelectorAll`

- **Modificar estilos a varios elementos**
Cambiar el color de todos los elementos de una clase:

```js
document.querySelectorAll('.resaltar').forEach(el => el.style.backgroundColor = 'yellow');
```

Todos los elementos con la clase **resaltar** tendrán fondo amarillo[^4].
- **Cambiar el contenido de varios elementos**

```js
document.querySelectorAll('p.info').forEach(p => p.textContent = 'Texto actualizado');
```

Actualiza el texto en todos los `<p>` con clase **info**[^4].
- **Agregar o quitar clases**

```js
document.querySelectorAll('.boton').forEach(btn => btn.classList.add('activo'));
```

Añade la clase **activo** a todos los elementos con clase **boton**[^2][^4].
- **Asignar eventos a varios elementos**

```js
document.querySelectorAll('button.eliminar').forEach(btn => {
  btn.addEventListener('click', () => alert('¡Eliminado!'));
});
```

Todos los botones con clase **eliminar** mostrarán una alerta al hacer clic[^2][^4].
- **Contar elementos que cumplen un selector**

```js
const cantidad = document.querySelectorAll('.error').length;
console.log(cantidad); // Cuántos elementos con clase 'error'
```

Útil para validar formularios o mostrar estadísticas[^4].
- **Seleccionar varios tipos de elementos**

```js
const titulos = document.querySelectorAll('h1, h2, h3');
titulos.forEach(t => t.style.fontWeight = 'bold');
```

Aplica cambios a todos los títulos de varios niveles a la vez[^2][^5].
- **Usar selectores avanzados (atributos, pseudoclases, descendientes)**

```js
const inputsMarcados = document.querySelectorAll('input[type="checkbox"]:checked');
inputsMarcados.forEach(input => console.log(input.value));
```

Trabaja solo con los checkboxes seleccionados[^5].


### Cómo recorrer los elementos seleccionados

Generalmente se usa **forEach** para recorrer la NodeList retornada por `querySelectorAll`:

```js
const elementos = document.querySelectorAll('.miClase');
elementos.forEach(el => {
  // Acciones sobre cada elemento
});
```

La NodeList que devuelve **querySelectorAll** se comporta de manera parecida a un array en cuanto a iteración, aunque no tiene todos sus métodos[^1][^2][^4].

Estas funcionalidades permiten construir interfaces dinámicas y mejorar la experiencia de usuario sin depender de frameworks adicionales. Aprovecha la potencia de los selectores CSS combinados con el recorrido sencillo de los elementos para manipular el DOM de forma eficiente[^2][^4][^5].

<div style="text-align: center">⁂</div>

[^1]: https://developer.mozilla.org/es/docs/Web/API/Document/querySelectorAll

[^2]: https://www.aprenderaprogramar.com/index.php?option=com_content\&view=article\&id=814%3Aqueryselectorall-javascript-y-queryselector-acceder-a-elementos-por-selectores-css-ejemplos-cu01134e\&catid=78\&Itemid=206

[^3]: https://xitrus.es/blog/112/Seleccionar_elementos_con_querySelector_de_JavaScript

[^4]: https://keepcoding.io/blog/nodo-queryselectorall/

[^5]: https://certidevs.com/tutorial-javascript-seleccion-dom

[^6]: https://bootcamp.laboratoria.la/es/topics/browser/dom/dom-methods-selection

[^7]: https://www.chucksacademy.com/es/topic/javascript-dom/selecting-elements-in-dom

[^8]: https://es.stackoverflow.com/questions/178688/cómo-seleccionar-elementos-con-document-queryselectorall

[^9]: https://nachoiborraies.github.io/javascript/md/es/02a.html

[^10]: https://keepcoding.io/blog/devuelve-el-metodo-queryselectorall/

