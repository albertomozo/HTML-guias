
# CARRITO CON ARRAYS



```javascript
let productos = ["Camiseta", "Pantalón", "Zapatos"];
let precios = [15, 30, 50];
let cantidades = [2, 1, 3];

let resultado = "<table border='1'>";
resultado += "<tr><th>Producto</th><th>Precio</th><th>Cantidad</th><th>Total</th></tr>";

let importeTotal = 0; // Variable para acumular el total general

for (let i = 0; i < productos.length; i++) {
  let total = precios[i] * cantidades[i];
  importeTotal += total; // Sumar al total general
  resultado += "<tr>";
  resultado += "<td>" + productos[i] + "</td>";
  resultado += "<td>" + precios[i] + " €</td>";
  resultado += "<td>" + cantidades[i] + "</td>";
  resultado += "<td>" + total + " €</td>";
  resultado += "</tr>";
}

// Fila para mostrar el importe total
resultado += "<tr>";
resultado += "<td colspan='3' style='text-align:right; font-weight:bold;'>Importe Total:</td>";
resultado += "<td style='font-weight:bold;'>" + importeTotal + " €</td>";
resultado += "</tr>";

resultado += "</table>";

document.getElementById("resultado").innerHTML = resultado;
```


### Explicación rápida:

- Se declara la variable `importeTotal` antes del bucle para acumular el total de todos los productos.
- En cada iteración, se calcula el total de esa fila (`precio * cantidad`) y se suma a `importeTotal`.
- Después del bucle, se añade una fila extra a la tabla para mostrar el importe total acumulado.
- Finalmente, se asigna todo el contenido generado a `innerHTML` del contenedor.

Este ejercicio es muy útil para que los alumnos practiquen arrays paralelos, concatenación de HTML dinámico y cálculos básicos dentro de un bucle.

<div style="text-align: center">⁂</div>

[^1]: https://programadorwebvalencia.com/javascript-ejemplo-carrito-de-compra/

[^2]: https://certidevs.com/ejercicios-javascript-proyecto-tienda-carrito-compra-ecommerce

[^3]: https://www.youtube.com/watch?v=3L_Wt6rfBvQ

[^4]: https://es.stackoverflow.com/questions/494942/cómo-calculo-el-total-de-los-productos-que-voy-agregando-al-carrito-javascript

[^5]: https://www.youtube.com/watch?v=48xYrIczhG0

[^6]: https://es.stackoverflow.com/questions/443987/sumar-items-a-comprar-con-javascript

[^7]: https://www.youtube.com/watch?v=lduIpYA66mM

[^8]: https://github.com/urian121/carrito-de-compras-con-javascript-en-tiempo-real

[^9]: https://es.linkedin.com/learning/desafio-de-programacion-javascript-basico/carrito-de-compras

[^10]: https://www.youtube.com/watch?v=6CMrP9e9uGc

