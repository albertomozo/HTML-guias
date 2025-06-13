# Guía de Contenedores CSS para Principiantes

## ¿Qué es un Contenedor?
Un contenedor es un elemento HTML que envuelve y organiza otros elementos, controlando su ancho, posición y espaciado en la página.

## Propiedades Principales para Contenedores

### 1. Width (Ancho)
Controla el ancho del contenedor:
- `width: 100%` - Ocupa todo el ancho disponible
- `width: 800px` - Ancho fijo de 800 píxeles
- `width: 50vw` - 50% del ancho de la ventana del navegador
- `width: auto` - Ancho automático (valor por defecto)

### 2. Max-width (Ancho Máximo)
Establece el ancho máximo que puede tener el contenedor:
- `max-width: 1200px` - Nunca será más ancho que 1200px
- `max-width: 90%` - Máximo 90% del contenedor padre
- `max-width: none` - Sin límite máximo

### 3. Min-width (Ancho Mínimo)
Establece el ancho mínimo del contenedor:
- `min-width: 320px` - Nunca será más estrecho que 320px
- `min-width: 20%` - Mínimo 20% del contenedor padre

### 4. Margin (Margen)
Espacio exterior alrededor del contenedor:
- `margin: 0 auto` - Centra horizontalmente el contenedor
- `margin: 20px` - 20px de margen en todos los lados
- `margin: 20px 40px` - 20px arriba/abajo, 40px izquierda/derecha
- `margin: 10px 20px 30px 40px` - arriba, derecha, abajo, izquierda

### 5. Padding (Relleno)
Espacio interior dentro del contenedor:
- `padding: 20px` - 20px de relleno en todos los lados
- `padding: 20px 40px` - 20px arriba/abajo, 40px izquierda/derecha
- `padding: 1rem 2rem` - Usando unidades rem

### 6. Box-sizing
Controla cómo se calcula el tamaño total:
- `box-sizing: border-box` - Incluye padding y border en el width
- `box-sizing: content-box` - Solo cuenta el contenido (por defecto)

### 7. Display
Tipo de visualización del contenedor:
- `display: block` - Elemento de bloque (ocupa toda la línea)
- `display: flex` - Contenedor flexible
- `display: grid` - Contenedor de cuadrícula
- `display: inline-block` - Bloque en línea

## Tipos Comunes de Contenedores

### Contenedor Principal (Main Container)
```css
.container {
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
    padding: 0 20px;
}
```

### Contenedor Fluido
```css
.container-fluid {
    width: 100%;
    padding: 0 15px;
}
```

### Contenedor Centrado
```css
.centered-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 40px 20px;
}
```

### Contenedor Flexible
```css
.flex-container {
    display: flex;
    max-width: 1000px;
    margin: 0 auto;
    gap: 20px;
}
```

## Breakpoints Comunes para Responsividad

### Móvil Pequeño
```css
@media (max-width: 480px) {
    .container { padding: 0 15px; }
}
```

### Tablet
```css
@media (max-width: 768px) {
    .container { max-width: 720px; }
}
```

### Desktop
```css
@media (min-width: 1024px) {
    .container { max-width: 1200px; }
}
```

## Consejos Importantes

1. **Usa `box-sizing: border-box`** para cálculos más predecibles
2. **Combina `max-width` con `width: 100%`** para responsividad
3. **Usa `margin: 0 auto`** para centrar contenedores
4. **Aplica padding interno** para separar contenido de los bordes
5. **Considera unidades relativas** (rem, em, %) para mejor escalabilidad

## Errores Comunes a Evitar

- No usar `max-width` en contenedores principales
- Olvidar el `margin: 0 auto` para centrar
- No considerar el padding en cálculos de ancho
- Usar solo píxeles sin considerar responsividad
- No definir un ancho máximo para pantallas grandes