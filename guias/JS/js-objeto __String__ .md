<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Guía rápida del objeto **String** en JavaScript con ejemplos

El objeto **String** permite trabajar con cadenas de texto y ofrece numerosos métodos para manipularlas y consultarlas[^1][^5].

## Crear cadenas

```js
const texto1 = "Hola mundo";              // Cadena primitiva
const texto2 = 'Otra cadena';
const texto3 = `Plantilla con ${texto1}`; // Template literal
const texto4 = new String("Objeto String");
```

Las cadenas literales pueden usar comillas simples, dobles o backticks (para plantillas e interpolación)[^1].

## Propiedades

- **length**: Devuelve la longitud de la cadena.

```js
console.log(texto1.length); // 10
```


## Acceso a caracteres

```js
console.log(texto1.charAt(1)); // "o"
console.log(texto1[^1]);        // "o"
```

Ambos devuelven el carácter en la posición indicada[^1].

## Métodos útiles

### Búsqueda y comprobación

- **indexOf(subcadena)**: Primer índice de la subcadena (o -1 si no existe).
- **lastIndexOf(subcadena)**: Última aparición.
- **includes(subcadena)**: ¿Contiene la subcadena?
- **startsWith(subcadena)**: ¿Empieza con...?
- **endsWith(subcadena)**: ¿Termina con...?

```js
console.log(texto1.indexOf("mundo")); // 5
console.log(texto1.includes("Hola")); // true
console.log(texto1.startsWith("Ho")); // true
console.log(texto1.endsWith("do"));   // true
```


### Extracción

- **slice(inicio, fin?)**: Extrae parte de la cadena.
- **substring(inicio, fin?)**: Similar a slice.
- **substr(inicio, longitud?)**: (Obsoleto, pero aún usado)

```js
console.log(texto1.slice(0, 4));      // "Hola"
console.log(texto1.substring(5));     // "mundo"
console.log(texto1.substr(5, 3));     // "mun"
```


### Modificación

- **replace(buscar, reemplazo)**: Reemplaza la primera coincidencia.
- **replaceAll(buscar, reemplazo)**: Reemplaza todas.
- **toUpperCase()** / **toLowerCase()**: Mayúsculas/minúsculas.
- **trim()**: Elimina espacios al inicio y final.
- **padStart(longitud, relleno)** / **padEnd(longitud, relleno)**: Rellena la cadena.

```js
console.log(texto1.replace("Hola", "Adiós")); // "Adiós mundo"
console.log("   texto   ".trim());            // "texto"
console.log("abc".padStart(5, "0"));          // "00abc"
console.log("abc".padEnd(5, "."));            // "abc.."
```


### División y repetición

- **split(separador)**: Divide la cadena en un array.
- **repeat(n)**: Repite la cadena n veces.

```js
console.log("a,b,c".split(",")); // ["a", "b", "c"]
console.log("ja".repeat(3));     // "jajaja"
```


### Concatenación

- **concat()**: Une cadenas (también puedes usar `+`).

```js
console.log("Hola".concat(" ", "Mundo")); // "Hola Mundo"
console.log("Hola" + " " + "Mundo");      // "Hola Mundo"
```


### Ejemplo práctico

```js
let frase = "Sumergiendo en tecnología.";
console.log(frase.slice(0, 11));   // "Sumergiendo"
console.log(frase.includes("tec")); // true
console.log(frase.toUpperCase());   // "SUMERGIENDO EN TECNOLOGÍA."
console.log(frase.split(" "));      // ["Sumergiendo", "en", "tecnología."]
```

Estos son los métodos y usos más comunes del objeto **String** en JavaScript, esenciales para manipular y consultar texto en cualquier aplicación.

<div style="text-align: center">⁂</div>

[^1]: https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String

[^2]: https://codingpotions.com/javascript-strings/

[^3]: https://boluda.com/curso/javascript/5-objeto-string/

[^4]: https://www.youtube.com/watch?v=sFRUQbh7SqE

[^5]: https://www.aluracursos.com/blog/strings-con-javascript-que-son-y-como-manipularlas

[^6]: https://www.apinem.com/objetos-en-javascript/

[^7]: http://www.asuntosoftware.com/2023/01/javascript-guia-rapida-de-expresiones.html

[^8]: https://www.aulascript.com/evaluar/strings-basico.htm

[^9]: https://developer.mozilla.org/es/docs/Web/JavaScript/Guide

[^10]: https://labex.io/es/tutorials/html-explore-string-object-methods-in-javascript-451061

