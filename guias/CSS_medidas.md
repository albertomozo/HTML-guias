# Resumen de Medidas CSS

## **Medidas Más Usadas Actualmente**

### **1. rem (Root EM)**
- **Uso principal:** Tipografía, espaciados, componentes
- **Por qué:** Escalable, accesible, consistente
- **Ejemplo:** `font-size: 1.2rem;` `margin: 2rem;`

### **2. % (Porcentajes)**
- **Uso principal:** Layouts responsivos, anchos de contenedores
- **Por qué:** Flexibilidad total en diferentes pantallas
- **Ejemplo:** `width: 100%;` `max-width: 80%;`

### **3. vh/vw (Viewport units)**
- **Uso principal:** Alturas de secciones, elementos a pantalla completa
- **Por qué:** Se adaptan perfectamente al tamaño de pantalla
- **Ejemplo:** `height: 100vh;` `width: 50vw;`

### **4. px (Píxeles)**
- **Uso principal:** Bordes, sombras, detalles pequeños
- **Por qué:** Precisión exacta cuando es necesaria
- **Ejemplo:** `border: 1px solid;` `box-shadow: 0 2px 4px;`

## **Otras Medidas Relevantes**

### **em**
- Relativa al elemento padre
- **Uso:** Espaciados internos de componentes
- **Ejemplo:** `padding: 0.5em;`

### **fr (Fraction)**
- Solo para CSS Grid
- **Uso:** Distribución de columnas/filas
- **Ejemplo:** `grid-template-columns: 1fr 2fr 1fr;`

### **ch**
- Ancho del carácter "0"
- **Uso:** Límites de líneas de texto
- **Ejemplo:** `max-width: 60ch;` (para párrafos legibles)

## **Recomendación General**
- **Tipografía y espaciados:** `rem`
- **Layouts y contenedores:** `%` y `fr`
- **Alturas de secciones:** `vh`
- **Detalles precisos:** `px`

Esta combinación te da flexibilidad, responsividad y control preciso donde lo necesites.

[ejemplo](../ejemplos/css-units-demo.html)

