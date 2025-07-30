

# api https://api.euskadi.eus/culture/events de ejemplo

 Consumo de una API Open Data con ejemplos en JavaScript “vanila” utilizando fetch(), enfocada en el endpoint de eventos culturales de Euskadi.

## 1. Buscar datos de interés

- 📄 **Lee la documentación** y localiza la URL/base endpoint.
Para la API de eventos culturales:
`https://api.euskadi.eus/culture/events/v1.0/events`
- 🔍 **Ejemplo básico de petición GET para obtener todos los eventos** (máximo 20 por página por defecto):

```js
fetch('https://api.euskadi.eus/culture/events/v1.0/events')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error al obtener eventos:', error));
```

Esto muestra en consola todos los eventos de la primera página[^1][^2][^3].

## 2. Analizar datos

- Ajusta la URL añadiendo parámetros: Ejemplo, eventos por fecha y municipio (usando el ejemplo de la documentación para Vitoria-Gasteiz el 6/05/2021):

```js
fetch('https://api.euskadi.eus/culture/events/v1.0/events/byDate/2021/5/6/byMunicipality/1/59')
  .then(response => response.json())
  .then(data => {
    // Analiza los primeros eventos recibidos
    data.items.forEach(evento => {
      console.log('Título:', evento.title);
      console.log('Fecha:', evento.startDate);
      console.log('Descripción:', evento.description);
      console.log('---');
    });
    // Si quieres saber cuántas páginas hay:
    console.log('Total de páginas:', data.totalPages);
  })
  .catch(error => console.error('Error analizando eventos:', error));
```

*Así puedes filtrar, explorar y entender la estructura de los datos devueltos.*[^2][^3]

## 3. Probar que funciona

- Integra el código en tu proyecto HTML/JS y realiza peticiones con distintos parámetros para asegurarte de que el API responde correctamente:

```js
async function obtenerEventos(fecha, provincia, municipio) {
  const url = `https://api.euskadi.eus/culture/events/v1.0/events/byDate/${fecha.anio}/${fecha.mes}/${fecha.dia}/byMunicipality/${provincia}/${municipio}`;
  try {
    const response = await fetch(url);
    if (!response.ok) throw new Error('Respuesta no OK');
    const data = await response.json();
    console.log('Ejemplo de evento recibido:', data.items[^0]);
    return data;
  } catch (error) {
    console.error('Error en la petición:', error);
  }
}

// Uso de ejemplo:
obtenerEventos({ anio: 2021, mes: 5, dia: 6 }, 1, 59);
```

*Puedes iterar o depurar cambiando los valores para hacer distintas pruebas.*[^1][^2]

**Consejo:**
Si la respuesta tiene más de una página, utiliza el parámetro `_page`, por ejemplo:
`...?byMunicipality/1/59?_page=2` para navegar entre páginas de resultados[^3].

Estos fragmentos funcionan en cualquier navegador moderno y muestran cómo consumir la API Open Data de Euskadi de manera clara y efectiva usando JavaScript puro con fetch().

<div style="text-align: center">⁂</div>

[^1]: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch

[^2]: https://www.geeksforgeeks.org/javascript/javascript-fetch-method/

[^3]: https://www.euskadi.eus/gobierno-vasco/-/2021/apis-de-datos-abiertos-para-impulsar-la-reutilizacion/

[^4]: https://api.euskadi.eus/culture/events

[^5]: https://www.freecodecamp.org/espanol/news/tutorial-de-fetch-api-en-javascript-con-ejemplos-de-js-fetch-post-y-header/

[^6]: https://es.javascript.info/fetch

[^7]: https://www.w3schools.com/jsref/api_fetch.asp

[^8]: https://opendata.euskadi.eus/api-culture/

[^9]: https://www.digitalocean.com/community/tutorials/how-to-use-the-javascript-fetch-api-to-get-data

[^10]: https://www.freecodecamp.org/espanol/news/javascript-fetch-api-para-principiantes/

[^11]: https://opendata.euskadi.eus/apis/-/apis-open-data/

[^12]: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

[^13]: https://www.kulturklik.euskadi.eus/webkklik00-detalle/es/?r01kQry=tC%3Aeuskadi%3BtF%3Aopendata%3Bm%3AdocumentLanguage.EQ.es%2COpendataLabels.LIKE.conciertos%3B

[^14]: https://pablomonteserin.com/curso/javascript/ejemplos-api-fetch/

[^15]: https://opendata.euskadi.eus/apia-culture/

[^16]: https://opendata.euskadi.eus/api-administration/?api=administration_events

[^17]: https://data.europa.eu/data/datasets/https-opendata-euskadi-eus-catalogo-estadistica-empresas-y-establecimientos-industrias-culturales-empresas-culturales-por-territorio-historico-

[^18]: https://datos.gob.es/en/aplicaciones/openslot

[^19]: https://data.europa.eu/data/datasets/https-opendata-euskadi-eus-catalogo-estadistica-territorio-zona-geografica-y-dimension-municipal-lectura-y-bibliotecas-personas-que-leen-habitualmente-diarios-y-revistas-

[^20]: https://www.euskadi.eus/contenidos/informacion/osk_trbg_planes_programas/es_def/adjuntos/Estrategia-de-Seguridad-del-Paciente-20-30.pdf

