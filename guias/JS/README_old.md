# Guías Rápidas de JavaScript

Este directorio contiene guías prácticas y resúmenes (cheatsheets) de los conceptos fundamentales de JavaScript, ordenados para un aprendizaje progresivo.

---

## Índice de Guías

1. **Sintaxis Básica**
   - [js-variables-guide.md](js-variables-guide.md)  
     *Variables, tipos de datos, operadores, comentarios, estructura básica de un script.*

        JavaScript tiene **3 formas** de declarar variables:

        | Palabra clave | Scope | Reasignación | Redeclaración | ¿Cuándo usar? |
        |---------------|-------|--------------|---------------|---------------|
        | `var` | Función | ✅ Sí | ✅ Sí | ❌ **No usar** (obsoleto) |
        | `let` | Bloque | ✅ Sí | ❌ No | ✅ **Variables que cambian** |
        | `const` | Bloque | ❌ No | ❌ No | ✅ **Variables constantes** |

    - [js-quote-guide.md](js-quote-guide.md)  
     *Las comillas*

        | Tipo | Símbolo | Mejor uso | Superpoderes |
        |------|---------|-----------|--------------|
        | Simples | `'` | Strings simples | Ninguno especial |
        | Dobles | `"` | Strings simples, JSON | Ninguno especial |
        | Template | `` ` `` | Variables, multilínea | ${interpolación}, saltos de línea |

        **Regla de oro**: Si tu string tiene variables o necesita saltos de línea, usa template literals. Para todo lo demás, usa comillas simples o dobles según tu preferencia.

2. **Condicionales**
   - [js-conditionals-guide.md](js-conditionals-guide.md)  
     *if, else, else if, switch, operadores lógicos y de comparación.*

        | Sentencia | Uso | Cuándo usarla |
        |-----------|-----|---------------|
        | `if` | Condición simple | Una sola condición |
        | `if...else` | Dos opciones | Verdadero o falso |
        | `if...else if...else` | Múltiples condiciones | Varias opciones |
        | `switch` | Comparar un valor | Muchas opciones específicas |
        | Operador ternario `?:` | Condición inline | Asignaciones simples |
        | Operadores lógicos | Evaluación corta | Validaciones rápidas |

3. **Bucles**
   - [js-loops-guide.md](js-loops-guide.md)  
     *for, while, do...while, break y continue.*

        - **`for`**: Ideal para contadores y arrays (conoces las iteraciones)
        - **`while`**: Perfecto cuando no sabes cuántas veces (condición dinámica)
        - **`do...while`**: Garantiza al menos una ejecución
        - **`for...in`**: Para objetos (propiedades)
        - **`for...of`**: Para arrays y strings (elementos)
        - **Siempre modifica la condición** en `while` para evitar bucles infinitos
        - **Usa `break`** para salir temprano
        - **Usa `continue`** para saltar iteraciones
        - **Cuidado con el scope** - usa `let` en lugar de `var`

<!-- 4. **Funciones**
   - [js-functions-guide.md](js-functions-guide.md)  
     *Declaración, expresión, parámetros, retorno, arrow functions.*

5. **Arrays**
   - [js-arrays-guide.md](js-arrays-guide.md)  
     *Creación, métodos principales, recorrido, manipulación.*

6. **Objetos**
   - [js-objects-guide.md](js-objects-guide.md)  
     *Propiedades, métodos, this, acceso y modificación.*

7. **DOM y Eventos**
   - [js-dom-guide.md](js-dom-guide.md)  
     *Selección de elementos, modificación, eventos básicos.*

8. **Extras y Buenas Prácticas**
   - [js-extras-guide.md](js-extras-guide.md)  
     *Plantillas literales, destructuring, spread/rest, buenas prácticas.*

---

Cada guía incluye ejemplos y un resumen tipo cheatsheet para consulta rápida.

¡Feliz aprendizaje! -->