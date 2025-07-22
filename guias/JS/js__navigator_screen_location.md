# Guía Rápida: Objetos Navigator, Screen y Location en JavaScript

## Objeto `navigator`
Proporciona información sobre el navegador y el sistema del usuario.

### Propiedades principales:
- `navigator.userAgent` - Cadena que identifica el navegador y sistema
- `navigator.language` - Idioma del navegador (ej: 'es-ES')
- `navigator.languages` - Array de idiomas preferidos
- `navigator.platform` - Plataforma del sistema operativo
- `navigator.cookieEnabled` - Si las cookies están habilitadas
- `navigator.onLine` - Si hay conexión a internet
- `navigator.geolocation` - API de geolocalización

### Métodos útiles:
```javascript
// Verificar conexión
if (navigator.onLine) {
  console.log('Conectado a internet');
}

// Obtener ubicación
navigator.geolocation.getCurrentPosition(
  position => console.log(position.coords),
  error => console.log('Error:', error)
);
```

## Objeto `screen`
Información sobre la pantalla del usuario.

### Propiedades principales:
- `screen.width` / `screen.height` - Dimensiones totales de la pantalla
- `screen.availWidth` / `screen.availHeight` - Área disponible (sin barra de tareas)
- `screen.colorDepth` - Profundidad de color en bits
- `screen.pixelDepth` - Bits por pixel
- `screen.orientation` - Orientación de la pantalla (móviles)

### Ejemplo:
```javascript
console.log(`Pantalla: ${screen.width}x${screen.height}`);
console.log(`Disponible: ${screen.availWidth}x${screen.availHeight}`);
```

## Objeto `location`
Información y control sobre la URL actual.

### Propiedades principales:
- `location.href` - URL completa
- `location.protocol` - Protocolo (http:, https:)
- `location.host` - Dominio + puerto
- `location.hostname` - Solo el dominio
- `location.port` - Puerto
- `location.pathname` - Ruta después del dominio
- `location.search` - Parámetros de consulta (?param=value)
- `location.hash` - Fragmento (#section)

### Métodos principales:
- `location.assign(url)` - Navegar a nueva URL
- `location.replace(url)` - Reemplazar URL actual (sin historial)
- `location.reload()` - Recargar página

### Ejemplos prácticos:
```javascript
// Obtener parámetros de URL
const urlParams = new URLSearchParams(location.search);
const valor = urlParams.get('parametro');

// Redirigir
location.href = 'https://ejemplo.com';

// Recargar página
location.reload();

// Cambiar solo el hash
location.hash = '#nueva-seccion';
```

### Casos de uso comunes:
```javascript
// Detectar dispositivo móvil
const esMobile = /Android|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);

// Adaptar contenido según resolución
if (screen.width < 768) {
  // Versión móvil
}

// Obtener dominio actual
const dominio = location.hostname;

// Verificar si estamos en HTTPS
const esSeguro = location.protocol === 'https:';
```


## Ejercicios prácticos con **navigator**

1. **Detectar el navegador y su versión**

```js
alert("Navegador: " + navigator.appName + "\nVersión: " + navigator.appVersion);
```

2. **Mostrar información del sistema**

```js
const info = `
  <p>Plataforma: ${navigator.platform}</p>
  <p>Cookies permitidas: ${navigator.cookieEnabled}</p>
  <p>User-Agent: ${navigator.userAgent}</p>
`;
document.body.innerHTML += info;
```

3. **Redirigir según navegador**

```js
if (navigator.userAgent.includes("Chrome")) {
  window.location.href = "https://www.google.com/chrome/";
} else {
  alert("Navegador no identificado para redirección.");
}
```

4. **Detectar si el navegador está en línea u offline**

```js
if (navigator.onLine) {
  alert("Estás conectado a Internet.");
} else {
  alert("No tienes conexión.");
}
```

5. **Mostrar el idioma preferido del navegador**

```js
document.body.innerHTML += "<p>Idioma: " + navigator.language + "</p>";
```

6. **Listar plugins instalados (donde esté permitido)**

```js
for (let i = 0; i < navigator.plugins.length; i++) {
  document.write(navigator.plugins[i].name + "<br>");
}
```

7. **Detectar sistema operativo y plataforma**

```js
alert("Plataforma: " + navigator.platform);
```


## Ejercicios prácticos con **screen**

1. **Mostrar las dimensiones de la pantalla**

```js
document.write("Anchura x Altura: " + screen.width + "x" + screen.height + "<br>");
document.write("Disponible: " + screen.availWidth + "x" + screen.availHeight + "<br>");
document.write("Profundidad de color: " + screen.colorDepth + "<br>");
document.write("Resolución de color: " + screen.pixelDepth + "<br>");
```

2. **Ajustar el contenido según la resolución**

```js
if (screen.availWidth < 800) {
  document.body.style.fontSize = "12px";
} else {
  document.body.style.fontSize = "16px";
}
```

3. **Detectar si la pantalla es Full HD o mayor**

```js
if (screen.width >= 1920 && screen.height >= 1080) {
  alert("Pantalla Full HD o superior.");
} else {
  alert("Pantalla de baja resolución.");
}
```

4. **Comparar área útil y área total**

```js
document.write("Total: " + screen.width + "x" + screen.height + "<br>");
document.write("Disponible: " + screen.availWidth + "x" + screen.availHeight + "<br>");
```

5. **Cambiar el color de fondo según la profundidad de color**

```js
if (screen.colorDepth > 24) {
  document.body.style.background = "lightgreen";
} else {
  document.body.style.background = "pink";
}
```


## Ejercicios prácticos con **location**

1. **Mostrar información detallada de la URL**

```js
document.write("href: " + location.href + "<br>");
document.write("protocol: " + location.protocol + "<br>");
document.write("host: " + location.host + "<br>");
document.write("hostname: " + location.hostname + "<br>");
document.write("port: " + location.port + "<br>");
document.write("pathname: " + location.pathname + "<br>");
document.write("search: " + location.search + "<br>");
document.write("hash: " + location.hash + "<br>");
document.write("origin: " + location.origin + "<br>");
```

2. **Recargar la página automáticamente cada cierto tiempo**

```js
setInterval(() => location.reload(), 10000); // cada 10 segundos
```

3. **Modificar el query string de la URL**

```js
location.search = "?nuevo=valor";
```

4. **Crear enlaces dinámicos basados en propiedades de location**

```js
let enlace = document.createElement('a');
enlace.href = location.protocol + "//" + location.host + "/nueva-pagina";
enlace.textContent = "Ir a nueva página";
document.body.appendChild(enlace);
```

5. **Redirección programada y mediante replace**

```js
setTimeout(() => {
  window.location.href = "https://ejemplo.com";
}, 3000); // redirecciona tras 3 segundos

// Redirección sin poder volver atrás
// location.replace("https://ejemplo.com/pagina-final");
```

6. **Modificar o leer el hash de la URL**

```js
location.hash = "#seccion2";
alert("Hash actual: " + location.hash);
```
