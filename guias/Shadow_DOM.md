El Shadow DOM es una tecnología web que permite encapsular el DOM y los estilos de un componente, creando un árbol DOM "en la sombra" que está aislado del documento principal. Esto evita conflictos de estilos y permite crear componentes verdaderamente reutilizables.

Te muestro un ejemplo práctico de cómo crear un componente personalizado con Shadow DOM:## Conceptos clave del Shadow DOM:

**1. Encapsulación de estilos:**
- Los estilos CSS dentro del Shadow DOM no afectan al documento principal
- Los estilos del documento principal no afectan al Shadow DOM
- Cada Shadow DOM tiene su propio contexto de estilos

**2. Creación:**
```javascript
this.attachShadow({ mode: 'open' });
```
- `mode: 'open'` permite acceso desde JavaScript externo
- `mode: 'closed'` bloquea el acceso externo

**3. Selector `:host`:**
- Se refiere al elemento que contiene el Shadow DOM
- Útil para estilar el contenedor desde dentro

**4. Ventajas:**
- **Aislamiento:** Evita conflictos de CSS
- **Reutilización:** Componentes verdaderamente independientes
- **Mantenimiento:** Estilos y lógica encapsulados

**5. Casos de uso:**
- Web Components
- Widgets reutilizables
- Bibliotecas de componentes
- Elementos de interfaz complejos

En el ejemplo puedes ver cómo los párrafos `<p>` del DOM principal se ven azules y en negrita (por los estilos globales), mientras que los párrafos dentro del Shadow DOM mantienen sus propios estilos blancos, demostrando la encapsulación completa.
