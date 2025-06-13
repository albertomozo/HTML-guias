## Estructura y Organización

**Orden de las reglas CSS:**
1. Reset/normalize
2. Variables CSS (custom properties)
3. Estilos base (html, body, elementos principales)
4. Layout general (grid, flexbox principales)
5. Componentes específicos
6. Utilidades y modificadores
7. Media queries

**Metodología de nomenclatura:**
- Usa BEM (Block Element Modifier) para mantener consistencia
- Ejemplo: `.card`, `.card__title`, `.card--featured`
- O utiliza nombres descriptivos y jerárquicos como `.header-navigation-item`

## Nesting (Anidamiento)

**CSS Nativo (moderno):**
```css
.card {
    padding: 1rem;
    border: 1px solid #ddd;

    & h2 {
        margin-bottom: 0.5rem;
        color: #333;
    }

    & p {
        line-height: 1.6;
    }

    &:hover {
        box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }

    &--featured {
        border-color: blue;
    }
}
```

**Reglas para nesting:**
- Máximo 3-4 niveles de anidamiento
- Usa `&` para pseudo-clases y modificadores
- Agrupa selectores relacionados
- Mantén la legibilidad como prioridad

**Con preprocesadores (Sass/SCSS):**
```scss
.navigation {
    display: flex;

    ul {
        list-style: none;
        margin: 0;

        li {
            padding: 0.5rem;

            a {
                text-decoration: none;
                color: $primary-color;

                &:hover {
                    color: $primary-dark;
                }
            }
        }
    }

    @media (max-width: 768px) {
        flex-direction: column;
    }
}
```

## Escritura del Código

**Formato y sintaxis:**
- Una propiedad por línea
- Usa espacios después de los dos puntos
- Agrupa propiedades relacionadas
- Mantén consistencia en el orden de propiedades dentro de cada regla

**Orden sugerido de propiedades:**
1. Posicionamiento (position, top, left, z-index)
2. Modelo de caja (display, width, height, margin, padding)
3. Tipografía (font-family, font-size, line-height, color)
4. Fondos y bordes (background, border)
5. Otros efectos (transform, transition, opacity)

## Eficiencia y Rendimiento

**Optimización:**
- Evita selectores demasiado específicos
- Usa clases en lugar de IDs cuando sea posible
- Minimiza el uso de `!important`
- Agrupa media queries al final o usa un enfoque mobile-first

**Variables CSS:**
- Define variables para colores, espaciados y tipografías principales
- Ejemplo: `--color-primary: #3b82f6;`
- Úsalas consistentemente en todo el proyecto

## Comentarios y Documentación

**Secciones claras:**
```css
/* ==========================================================================
     COMPONENTES - Botones
     ========================================================================== */

/* Botón base */
.btn { ... }

/* Variantes de botón */
.btn--primary { ... }
```

## Mantenimiento

**Buenas prácticas:**
- Elimina CSS no utilizado regularmente
- Usa herramientas de linting (stylelint)
- Mantén archivos separados por componentes o secciones
- Considera usar preprocesadores (Sass, Less) para proyectos grandes

El nesting hace el código más legible y organizado, especialmente cuando trabajas con componentes complejos.