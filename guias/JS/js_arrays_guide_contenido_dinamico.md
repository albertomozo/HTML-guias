# Contenido "dinámico" con arrays 


Al recorrer  un array para mostrar su contenido de forma visual usando `innerHTML`, es recomendable seguir estos pasos para que el resultado sea correcto y eficiente:

### 1. **Inicializar una variable con la etiqueta contenedora**

Antes de empezar el bucle, crea una variable (por ejemplo, llamada `resultado`) que contenga la etiqueta de apertura del elemento HTML que vas a usar como contenedor. Puede ser `<ul>`, `<table>`, `<select>`, etc.

```javascript
let resultado = "<ul>";
```


### 2. **Concatenar el contenido en cada paso del bucle**

Dentro del bucle `for`, vas añadiendo (concatenando) a esa variable el HTML correspondiente a cada elemento del array. Por ejemplo, si tienes un array de frutas:

```javascript
let frutas = ["Manzana", "Banana", "Pera"];
for (let i = 0; i < frutas.length; i++) {
  resultado += "<li>" + frutas[i] + "</li>";
}
```


### 3. **Cerrar la etiqueta contenedora**

Después del bucle, cierra la etiqueta del contenedor:

```javascript
resultado += "</ul>";
```


### 4. **Mostrar el resultado con innerHTML**

Finalmente, asigna el contenido de la variable al `innerHTML` del elemento contenedor en tu HTML (por ejemplo, un `<div id="resultado">`):

```javascript
document.getElementById("resultado").innerHTML = resultado;
```


#### **Resumen del flujo completo**

```javascript
let frutas = ["Manzana", "Banana", "Pera"];
let resultado = "<ul>"; // 1. Iniciar con la etiqueta contenedora
for (let i = 0; i < frutas.length; i++) { // 2. Concatenar en cada paso
  resultado += "<li>" + frutas[i] + "</li>";
}
resultado += "</ul>"; // 3. Cerrar la etiqueta
document.getElementById("resultado").innerHTML = resultado; // 4. Mostrar en el HTML
```

**Consejo:**
No modifiques el `innerHTML` dentro del bucle, sino solo una vez al final. Así evitas problemas de rendimiento y errores de visualización[^1][^6].

