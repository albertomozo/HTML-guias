Cuando digo "usar propiedades JS para datos complejos", me refiero a 
## Datasets vs Propiedades JS

### Datasets (limitado a strings)
```javascript
// Solo puedes almacenar strings
elemento.dataset.config = JSON.stringify({
  animation: 'fade',
  duration: 300,
  callbacks: ['onStart', 'onEnd']
});

// Tienes que parsear cada vez que lo uses
const config = JSON.parse(elemento.dataset.config);
```

### Propiedades JS (cualquier tipo de dato)
```javascript
// Puedes almacenar objetos, funciones, arrays directamente
elemento.miConfig = {
  animation: 'fade',
  duration: 300,
  callbacks: [
    () => console.log('Iniciado'),
    () => console.log('Terminado')
  ],
  usuario: {
    id: 123,
    permisos: ['read', 'write']
  }
};

// Acceso directo sin parsear
elemento.miConfig.callbacks[0](); // Ejecuta la función
```

## Ejemplos prácticos

### ❌ Problemático con datasets
```javascript
// Almacenar array de objetos en dataset
const productos = [
  { id: 1, nombre: 'Laptop', precio: 999.99 },
  { id: 2, nombre: 'Mouse', precio: 29.99 }
];

elemento.dataset.productos = JSON.stringify(productos);

// Cada vez que necesites los datos:
const productosParseados = JSON.parse(elemento.dataset.productos);
// Lento y propenso a errores
```

### ✅ Mejor con propiedades JS
```javascript
// Almacenamiento directo
elemento.productos = [
  { id: 1, nombre: 'Laptop', precio: 999.99 },
  { id: 2, nombre: 'Mouse', precio: 29.99 }
];

// Acceso inmediato
elemento.productos.forEach(producto => {
  console.log(producto.nombre);
});
```

## Casos donde usar propiedades JS

### 1. Funciones y callbacks
```javascript
// Imposible con datasets
elemento.onCustomEvent = function(data) {
  console.log('Evento personalizado:', data);
};

elemento.validadores = [
  (valor) => valor.length > 3,
  (valor) => /^[a-zA-Z]+$/.test(valor)
];
```

### 2. Referencias a otros objetos
```javascript
// Referencia a instancias de clases
elemento.controlador = new MiControlador();
elemento.cache = new Map();
elemento.websocket = new WebSocket('ws://localhost:8080');
```

### 3. Configuraciones complejas
```javascript
elemento.configuracion = {
  api: {
    endpoint: '/api/users',
    headers: { 'Authorization': 'Bearer token' },
    retries: 3,
    timeout: 5000
  },
  ui: {
    theme: 'dark',
    animations: true,
    shortcuts: new Map([
      ['ctrl+s', 'save'],
      ['ctrl+z', 'undo']
    ])
  },
  handlers: {
    onError: (error) => showNotification(error),
    onSuccess: (data) => updateUI(data)
  }
};
```

## Comparación de rendimiento

```javascript
// Datasets - más lento
for(let i = 0; i < 1000; i++) {
  const data = JSON.parse(elemento.dataset.items); // Parse cada vez
  // procesar data...
}

// Propiedades JS - más rápido  
for(let i = 0; i < 1000; i++) {
  const data = elemento.items; // Acceso directo
  // procesar data...
}
```

## Cuándo usar cada uno

### Usa **datasets** para:
- Datos simples (strings, números)
- Información que necesita ser visible en HTML
- Datos que se usan en CSS
- Comunicación servidor → cliente

### Usa **propiedades JS** para:
- Objetos complejos
- Arrays de datos
- Funciones y callbacks
- Referencias a instancias
- Datos que cambian frecuentemente
- Mejor rendimiento

## Ejemplo híbrido
```javascript
// Dataset para datos simples
elemento.dataset.id = "123";
elemento.dataset.type = "premium";

// Propiedad JS para datos complejos
elemento.userData = {
  profile: { /* objeto complejo */ },
  preferences: new Map(),
  updateCallback: (data) => { /* función */ }
};
```

La clave es elegir la herramienta correcta según la complejidad y uso de tus datos.