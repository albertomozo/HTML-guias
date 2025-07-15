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

Estos objetos son fundamentales para crear aplicaciones web que se adapten al entorno del usuario y manejen la navegación de forma inteligente.