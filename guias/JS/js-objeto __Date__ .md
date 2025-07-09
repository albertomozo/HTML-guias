<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Guía rápida del objeto **Date** en JavaScript con ejemplos

El objeto **Date** permite trabajar con fechas y horas en JavaScript. Es fundamental para manipular, mostrar y calcular fechas.

## Creación de objetos Date

- **Fecha y hora actual**

```js
const ahora = new Date();
console.log(ahora); // Ejemplo: Wed Jul 09 2025 19:58:00 GMT+0200 (CEST)
```

- **Fecha específica (año, mes, día, hora, minuto, segundo, milisegundo)**

```js
// Ojo: el mes empieza en 0 (enero = 0, diciembre = 11)
const fecha = new Date(2025, 6, 9, 19, 30, 0, 0);
console.log(fecha); // Wed Jul 09 2025 19:30:00 GMT+0200 (CEST)
```

- **Desde una cadena de texto**

```js
const desdeTexto = new Date("2025-07-09T19:30:00");
console.log(desdeTexto); // Wed Jul 09 2025 19:30:00 GMT+0200 (CEST)
```

- **Desde milisegundos desde 1970-01-01**

```js
const desdeMs = new Date(1720546200000);
console.log(desdeMs);
```


## Métodos principales para obtener información

| Método | Descripción | Ejemplo de uso |
| :-- | :-- | :-- |
| `getFullYear()` | Año (4 dígitos) | `fecha.getFullYear()` |
| `getMonth()` | Mes (0-11) | `fecha.getMonth()` |
| `getDate()` | Día del mes (1-31) | `fecha.getDate()` |
| `getDay()` | Día de la semana (0=Domingo) | `fecha.getDay()` |
| `getHours()` | Hora (0-23) | `fecha.getHours()` |
| `getMinutes()` | Minutos (0-59) | `fecha.getMinutes()` |
| `getSeconds()` | Segundos (0-59) | `fecha.getSeconds()` |
| `getMilliseconds()` | Milisegundos (0-999) | `fecha.getMilliseconds()` |
| `getTime()` | Milisegundos desde 1970-01-01 | `fecha.getTime()` |
| `getTimezoneOffset()` | Diferencia con UTC (en minutos) | `fecha.getTimezoneOffset()` |

```js
console.log(fecha.getFullYear());      // 2025
console.log(fecha.getMonth());         // 6 (julio)
console.log(fecha.getDate());          // 9
console.log(fecha.getDay());           // 3 (miércoles)
console.log(fecha.getHours());         // 19
console.log(fecha.getMinutes());       // 30
console.log(fecha.getTime());          // milisegundos desde 1970-01-01
```


---

## Métodos para modificar fechas

- **setFullYear(), setMonth(), setDate(), setHours(), setMinutes(), setSeconds(), setMilliseconds()**

```js
fecha.setFullYear(2030);
fecha.setMonth(0); // enero
fecha.setDate(1);
console.log(fecha); // Tue Jan 01 2030 ...
```


## Métodos para mostrar fechas como texto

- **toString()**: Representación completa
- **toDateString()**: Solo fecha
- **toTimeString()**: Solo hora
- **toISOString()**: Formato ISO (útil para APIs)
- **toLocaleDateString()**: Fecha según configuración regional
- **toLocaleTimeString()**: Hora según configuración regional

```js
console.log(fecha.toString());           // Tue Jan 01 2030 19:30:00 GMT+0100 (CET)
console.log(fecha.toDateString());       // Tue Jan 01 2030
console.log(fecha.toISOString());        // 2030-01-01T18:30:00.000Z
console.log(fecha.toLocaleDateString()); // 1/1/2030 (formato local)
console.log(fecha.toLocaleTimeString()); // 19:30:00
```


## Ejemplo práctico: sumar días a una fecha

```js
function sumarDias(fecha, dias) {
  const nueva = new Date(fecha);
  nueva.setDate(nueva.getDate() + dias);
  return nueva;
}
console.log(sumarDias(new Date(), 5)); // Fecha dentro de 5 días
```

Estos son los métodos y usos más comunes del objeto **Date** en JavaScript, esenciales para manipular y mostrar fechas y horas en cualquier aplicación web[^1][^2][^3][^4][^5].

<div style="text-align: center">⁂</div>

[^1]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date

[^2]: https://www.w3schools.com/js/js_dates.asp

[^3]: https://bugfender.com/blog/javascript-date-and-time/

[^4]: https://dev.to/akash32755/exploring-javascript-date-object-methods-a-comprehensive-guide-jpd

[^5]: https://www.tutorialspoint.com/javascript/javascript_date_object.htm

[^6]: https://talent500.com/blog/javascript-date-object-methods-time-zones/

[^7]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date

[^8]: https://www.w3schools.com/js/js_date_methods.asp

[^9]: https://www.geeksforgeeks.org/javascript/javascript-date-objects/

[^10]: https://www.geeksforgeeks.org/javascript/javascript-date/

[^11]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Representing_dates_times

[^12]: https://til.simonwillison.net/javascript/javascript-date-objects

[^13]: https://www.tecforfun.com/javascript/a-simple-guide-to-javascript-date-object/

[^14]: https://www.w3schools.com/jsref/jsref_obj_date.asp

