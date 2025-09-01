## ¿Qué son los Datasets?

Los **datasets** son atributos HTML personalizados que permiten almacenar información adicional en elementos del DOM. Se definen con el prefijo `data-` y se acceden desde JavaScript mediante la propiedad `dataset`.

## Sintaxis HTML

```html
<div data-user-id="123" data-role="admin" data-active="true">
  Usuario
</div>
```

## Acceso desde JavaScript

### Lectura de datos
```javascript
const elemento = document.querySelector('div');

// Acceder a data-user-id
console.log(elemento.dataset.userId); // "123"

// Acceder a data-role  
console.log(elemento.dataset.role); // "admin"

// Acceder a data-active
console.log(elemento.dataset.active); // "true"
```

### Escritura de datos
```javascript
// Modificar valores existentes
elemento.dataset.userId = "456";

// Agregar nuevos datasets
elemento.dataset.status = "online";
elemento.dataset.lastLogin = "2024-01-15";
```

### Eliminar datasets
```javascript
delete elemento.dataset.userId;
// o
elemento.removeAttribute('data-user-id');
```

## Conversión de nombres

JavaScript convierte automáticamente entre kebab-case (HTML) y camelCase (JS):

| HTML | JavaScript |
|------|------------|
| `data-user-id` | `dataset.userId` |
| `data-first-name` | `dataset.firstName` |
| `data-is-active` | `dataset.isActive` |

## Casos de uso comunes

### 1. Almacenar IDs para eventos
```javascript
// HTML: <button data-product-id="123">Comprar</button>
document.querySelectorAll('button').forEach(btn => {
  btn.addEventListener('click', (e) => {
    const productId = e.target.dataset.productId;
    comprarProducto(productId);
  });
});
```

### 2. Configuración de componentes
```javascript
// HTML: <div data-animation="fade" data-duration="300"></div>
function iniciarAnimacion(elemento) {
  const tipo = elemento.dataset.animation;
  const duracion = parseInt(elemento.dataset.duration);
  // Lógica de animación...
}
```

### 3. Estados de elementos
```javascript
// Cambiar estado visual basado en dataset
elemento.dataset.status = "loading";
// CSS: [data-status="loading"] { opacity: 0.5; }
```

## Ventajas

- **Válido HTML**: Estándar W3C
- **Fácil acceso**: API simple con `dataset`
- **CSS friendly**: Se pueden usar en selectores CSS
- **Flexible**: Almacena cualquier string

## Limitaciones

- Solo almacena strings (necesitas parsear números/booleanos)
- Visible en el HTML (no para datos sensibles)
- Performance: mejor usar propiedades JS para datos complejos

## Ejemplo práctico completo

```html
<div id="usuario" data-id="123" data-name="Juan" data-premium="true">
  <button data-action="edit">Editar</button>
  <button data-action="delete">Eliminar</button>
</div>
```

```javascript
const usuario = document.getElementById('usuario');
const botones = usuario.querySelectorAll('button');

// Leer datos del usuario
const datosUsuario = {
  id: parseInt(usuario.dataset.id),
  name: usuario.dataset.name,
  premium: usuario.dataset.premium === 'true'
};

// Manejar acciones
botones.forEach(btn => {
  btn.addEventListener('click', () => {
    const accion = btn.dataset.action;
    const userId = usuario.dataset.id;
    
    switch(accion) {
      case 'edit':
        editarUsuario(userId);
        break;
      case 'delete':
        eliminarUsuario(userId);
        break;
    }
  });
});
```

Los datasets son perfectos para pasar datos del servidor al cliente y mantener el HTML semántico y organizado.