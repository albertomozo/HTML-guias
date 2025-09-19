# LOCALSTORAGE - LISTA DE DESEOS 

## 1. Conceptos básicos

* **LocalStorage**: almacena pares clave/valor en el navegador sin fecha de caducidad.
* Los datos solo se guardan como **strings**, así que necesitaremos `JSON.stringify()` y `JSON.parse()` para guardar y leer arrays/objetos.
* Flujo básico de la wishlist:

  1. Mostrar una lista de productos.
  2. Al hacer clic en "Añadir a deseos", se guarda en LocalStorage.
  3. Mostrar la lista de deseos guardada.
  4. Permitir eliminar elementos.

---

## 2. Estructura básica del HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mi Lista de Deseos</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    .producto, .wishlist-item {
      border: 1px solid #ccc; padding: 10px; margin: 10px 0;
      display: flex; justify-content: space-between; align-items: center;
    }
    button { cursor: pointer; }
  </style>
</head>
<body>
  <h1>Productos</h1>
  <div id="productos"></div>

  <h2>Mi Lista de Deseos</h2>
  <div id="wishlist"></div>

  <script src="script.js"></script>
</body>
</html>
```

---

## 3. Datos de ejemplo (productos)

```js
// script.js
const productos = [
  { id: 1, nombre: "Portátil", precio: 900 },
  { id: 2, nombre: "Móvil", precio: 600 },
  { id: 3, nombre: "Auriculares", precio: 150 }
];
```

---

## 4. Funciones clave para LocalStorage

```js
// Guardar en LocalStorage
function guardarWishlist(lista) {
  localStorage.setItem("wishlist", JSON.stringify(lista));
}

// Obtener de LocalStorage
function obtenerWishlist() {
  const data = localStorage.getItem("wishlist");
  return data ? JSON.parse(data) : [];
}
```

---

## 5. Mostrar productos y wishlist

```js
const contenedorProductos = document.getElementById("productos");
const contenedorWishlist = document.getElementById("wishlist");

function mostrarProductos() {
  contenedorProductos.innerHTML = "";
  productos.forEach(prod => {
    const div = document.createElement("div");
    div.classList.add("producto");
    div.innerHTML = `
      <span>${prod.nombre} - ${prod.precio}€</span>
      <button onclick="agregarAWishlist(${prod.id})">Añadir a deseos</button>
    `;
    contenedorProductos.appendChild(div);
  });
}

function mostrarWishlist() {
  const wishlist = obtenerWishlist();
  contenedorWishlist.innerHTML = "";
  wishlist.forEach(item => {
    const div = document.createElement("div");
    div.classList.add("wishlist-item");
    div.innerHTML = `
      <span>${item.nombre} - ${item.precio}€</span>
      <button onclick="eliminarDeWishlist(${item.id})">❌</button>
    `;
    contenedorWishlist.appendChild(div);
  });
}
```

---

## 6. Funciones para añadir y eliminar

```js
function agregarAWishlist(id) {
  let wishlist = obtenerWishlist();
  const producto = productos.find(p => p.id === id);
  
  // Evitar duplicados
  if (!wishlist.some(p => p.id === id)) {
    wishlist.push(producto);
    guardarWishlist(wishlist);
    mostrarWishlist();
  }
}

function eliminarDeWishlist(id) {
  let wishlist = obtenerWishlist();
  wishlist = wishlist.filter(p => p.id !== id);
  guardarWishlist(wishlist);
  mostrarWishlist();
}
```

---

## 7. Inicialización

```js
// Cuando cargue la página
mostrarProductos();
mostrarWishlist();
```

---

## 8. Resultado esperado

* Se listan productos con botón **"Añadir a deseos"**.
* Al pulsar, se guardan en LocalStorage y aparecen en la sección "Mi Lista de Deseos".
* Puedes **eliminar** elementos de la wishlist.
* Si recargas la página, la lista se mantiene. ✅

[ejemplo](js__localstorage_listadeseos_01.html) 

[ejemplo con array method](js__localstorage_listadeseos.html) 



