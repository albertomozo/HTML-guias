<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

### Objetos en JavaScript

En JavaScript, un **objeto** es una estructura que permite almacenar y organizar datos mediante pares clave-valor (propiedades y métodos). Piensa en un objeto como una "caja" que agrupa datos relacionados y, opcionalmente, comportamientos asociados (funciones).

- **Ejemplo básico:**

```js
const persona = {
  nombre: "Ana",
  edad: 30,
  saludar: function() {
    console.log("¡Hola, soy Ana!");
  }
};
persona.saludar(); // Imprime: ¡Hola, soy Ana!
```

- Los objetos te permiten agrupar información y facilitar el acceso, la modificación y la reutilización de datos[^1][^2][^3].


### ¿Qué es un Prototipo en JavaScript?

Un **prototipo** es también un objeto, pero su función es actuar como "plantilla" o base sobre la que otros objetos pueden heredar propiedades y métodos. Todos los objetos en JavaScript están vinculados a un prototipo, y es clave para la herencia.

- Cuando accedes a una propiedad o método en un objeto y no se encuentra, JavaScript lo busca en su prototipo, y así sucesivamente, formando la "cadena de prototipos"[^4][^5][^6].
- **Ejemplo:**

```js
function Persona(nombre) {
  this.nombre = nombre;
}
Persona.prototype.saludar = function () {
  console.log("Hola, soy " + this.nombre);
};
const juan = new Persona("Juan");
juan.saludar(); // Usa el método del prototipo
```


### Diferencias entre Objetos y Prototipos

|  | **Objeto** | **Prototipo** |
| :--: | :-- | :-- |
| Definición | Es una instancia con propiedades y métodos propios. | Es un objeto del cual otros objetos pueden heredar. |
| Uso | Encapsula datos y funcionalidades concretas. | Sirve de plantilla para compartir funcionalidades. |
| Herencia | No necesariamente comparte nada con otros objetos. | Permite que múltiples objetos compartan propiedades/métodos. |
| Memoria | Métodos definidos directamente en cada objeto consumen más memoria. | Los métodos definidos en el prototipo se comparten y optimizan el uso de memoria. |

- Los **objetos** se usan para representar entidades concretas (por ejemplo, un usuario o un coche).
- Los **prototipos** permiten compartir funcionalidades comunes entre objetos, evitando duplicación y mejorando el rendimiento[^4][^7][^5].


### ¿Cuándo usar cada uno?

- Usa **objetos** cuando necesitas estructurar datos o crear entidades únicas.
- Usa **prototipos** para métodos compartidos entre muchas instancias, como funciones en las clases o constructores personalizados.


### Ejemplo Ilustrativo

- Si defines un método directamente dentro de cada objeto, cada instancia tiene su propia copia:

```js
function Animal(nombre) {
  this.nombre = nombre;
  this.sonido = function () {
    console.log("Sonido!");
  }
}
```

- Si defines el método en el prototipo, se comparte entre todas las instancias:

```js
function Animal(nombre) {
  this.nombre = nombre;
}
Animal.prototype.sonido = function () {
  console.log("Sonido!");
}
```


En resumen, **los prototipos son la base de la herencia de JavaScript**, y todos los objetos pueden acceder a los métodos y propiedades definidos en su cadena de prototipos, mientras que los objetos representan datos concretos y pueden tener propiedades únicas a cada instancia[^4][^7][^6].

<div style="text-align: center">⁂</div>

[^1]: https://lenguajejs.com/javascript/objetos/que-son/

[^2]: https://developer.mozilla.org/es/docs/Learn_web_development/Core/Scripting/Object_basics

[^3]: https://es.javascript.info/object

[^4]: https://keepcoding.io/blog/prototipo-en-javascript-y-como-funciona/

[^5]: https://developer.mozilla.org/es/docs/Learn_web_development/Extensions/Advanced_JavaScript_objects/Object_prototypes

[^6]: https://codigofacilito.com/articulos/js-conceptos-de-prototipos

[^7]: https://blog.eamexicano.com/javascript/diferencias-entre-objetos-y-prototipos/

[^8]: https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Working_with_objects

[^9]: https://www.freecodecamp.org/espanol/news/objetos-en-javascript-una-guia-para-principiantes/

[^10]: https://www.freecodecamp.org/espanol/news/javascript-crear-objecto-como-definir-objetos-en-js/

[^11]: https://arielfuggini.com/javascript-prototypes/

[^12]: https://elrincondelfront.substack.com/p/prototipos-en-javascript

[^13]: https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Object

[^14]: https://es.stackoverflow.com/questions/236929/qué-diferencia-hay-entre-prototipos-y-clases-en-javascript

[^15]: https://www.youtube.com/watch?v=5DaZXXbHI_U

[^16]: https://www.youtube.com/watch?v=KB3kWoTbmWk

[^17]: https://www.deustoformacion.com/blog/programacion-tic/5-formas-crear-objetos-javascript

[^18]: https://es.stackoverflow.com/questions/2012/qué-son-los-prototipos-en-javascript-y-para-qué-sirven

[^19]: https://www.reddit.com/r/learnjavascript/comments/x80v4l/eli5_what_is_the_difference_between_proto_and/?tl=es-es

[^20]: https://www.digitalocean.com/community/tutorials/como-usar-metodos-de-objetos-en-javascript-es

