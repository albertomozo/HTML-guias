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

Estos son los métodos y usos más comunes del objeto **Date** en JavaScript, esenciales para manipular y mostrar fechas y horas en cualquier aplicación web




# Trabajar con Timestamps y Fechas en JavaScript

## ¿Qué es un Timestamp Unix?

Un **timestamp Unix** es un número entero que representa los segundos transcurridos desde el 1 de enero de 1970 a las 00:00:00 UTC (el "Unix epoch"). Este valor es muy útil en informática porque permite operar con fechas como si fueran simples números, facilitando cálculos y comparaciones.

En JavaScript, los timestamps suelen manejarse en **milisegundos**, así que para trabajar con segundos (el estándar Unix), normalmente se divide o multiplica por 1000.

## Cómo Obtener el Timestamp Actual

```js
// En milisegundos
const timestampMs = Date.now();

// En segundos (Unix timestamp)
const timestamp = Math.floor(Date.now() / 1000);
console.log(timestamp);
```


## Convertir una Fecha a Timestamp

```js
// Fecha específica a timestamp en milisegundos
const fecha = new Date('2025-07-14T13:29:00Z');
const timestampMs = fecha.getTime();

// En segundos (Unix timestamp)
const timestamp = Math.floor(fecha.getTime() / 1000);
console.log(timestamp);
```


## Convertir un Timestamp a Fecha

```js
// Timestamp en segundos a objeto Date
const timestamp = 1752480540;
const fecha = new Date(timestamp * 1000);
console.log(fecha.toISOString()); // Formato legible y estandarizado
```


## Operar con Fechas como Números

Como los timestamps son números, puedes sumar o restar segundos fácilmente:

```js
// Sumar 1 hora (3600 segundos) a un timestamp
const timestamp = Math.floor(Date.now() / 1000);
const timestampMasUnaHora = timestamp + 3600;

// Diferencia entre dos fechas en segundos
const fecha1 = new Date('2025-07-14T12:00:00Z');
const fecha2 = new Date('2025-07-14T15:30:00Z');
const diffSegundos = Math.floor((fecha2 - fecha1) / 1000);
console.log(diffSegundos); // 12600 segundos (3 horas y media)
```


## Ejemplo Práctico: Funciones Útiles

```js
// Obtener el timestamp actual en segundos
function getCurrentTimestamp() {
  return Math.floor(Date.now() / 1000);
}

// Convertir fecha a timestamp
function dateToTimestamp(dateString) {
  return Math.floor(new Date(dateString).getTime() / 1000);
}

// Convertir timestamp a fecha legible
function timestampToDate(ts) {
  return new Date(ts * 1000).toISOString();
}

// Sumar segundos a un timestamp
function addSecondsToTimestamp(ts, seconds) {
  return ts + seconds;
}

// Diferencia en segundos entre dos fechas
function diffInSeconds(date1, date2) {
  return Math.abs(Math.floor((new Date(date1) - new Date(date2)) / 1000));
}
```


## Resumen de Operaciones Comunes

| Operación                  | Ejemplo JS                                    |
|----------------------------|-----------------------------------------------|
| Timestamp actual (segundos)| `Math.floor(Date.now() / 1000)`              |
| Fecha a timestamp          | `Math.floor(new Date(fecha).getTime() / 1000)`|
| Timestamp a fecha          | `new Date(timestamp * 1000)`                  |
| Sumar segundos             | `timestamp + segundos`                        |
| Diferencia entre fechas    | `(new Date(fecha2) - new Date(fecha1)) / 1000`|

## Notas

- **JavaScript** usa milisegundos por defecto en sus objetos `Date`; el timestamp Unix estándar está en segundos, por eso se multiplica o divide por 1000 según la conversión[5][7].
- Las operaciones con timestamps evitan problemas de formato y zonas horarias, aunque la visualización de la fecha puede ajustarse a la zona local o UTC según el método usado[7].
- Para manipulación avanzada de fechas y zonas horarias, puedes usar bibliotecas como [moment.js](https://momentjs.com/) o [date-fns](https://date-fns.org/)[7].








