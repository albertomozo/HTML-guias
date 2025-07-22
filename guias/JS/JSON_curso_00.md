
# JSON

{"curso":"IFCD0609_202402",
"fecha inicio" : "2024-02-14",
"fecha fin" : "2024-02-25",
"tutor":
{"Nombre":"Alberto Mozo",
"email" : "albertomozodocente@gmail.com",
"linked" : "https://www.linkedin.com/in/alberto-mozo-avellaned-80615713/",
"github" : "https://github.com/albertomozo"

    },
    "alumnos" : [
{
"Nombre":"Alumno1",
"email" : "Alumno1@gmail.com",
"linked" : "https://www.linkedin.com/",
"github" : "https://github.com",
"inicio" : {
"html" : 1,
"css" : 1,
"JS" : 1,
"Vue" : 3
},
"fin" : {
"html" : 4,
"css" : 4,
"JS" : 4,
"Vue" : 4
}

        },
        {
            "Nombre":"Alumno2",
            "email" : "Alumno2@gmail.com",
            "linked" : "https://www.linkedin.com/",
            "github" : "https://github.com",
            "inicio" : {     
                "html":2,
                "css" :3,
                "JS" : 1,
                "Vue" : 3
            },
            "fin" :{     
                "html" : 4,
                "css" : 4,
                "JS" : 4,
                "Vue" : 4 
            } 
        
        },
        {
            "Nombre":"Alumno3",
           "email" : "Alumno4@gmail.com",
           "linked" : "https://www.linkedin.com/",
           "github" : "https://github.com",
           "inicio" : {     
               "html":2,
               "css" :3,
               "JS" : 1,
               "Vue" : 3
           },
           "fin" :{     
               "html" : 4,
               "css" : 4,
               "JS" : 4,
               "Vue" : 4 
           } 
       
       },
       {
        "Nombre":"Alumno4",
       "email" : "Alumno4@gmail.com",
       "linked" : "https://www.linkedin.com/",
       "github" : "https://github.com",
       "inicio" : {     
           "html":2,
           "css" :3,
           "JS" : 1,
           "Vue" : 3
       },
       "fin" :{     
           "html" : 4,
           "css" : 4,
           "JS" : 4,
           "Vue" : 4 
       } 
    }
]
}

**JSON** (JavaScript Object Notation) es un formato de texto ligero utilizado para estructurar e intercambiar datos entre sistemas de forma sencilla y legible tanto para humanos como para máquinas[^1_1][^1_5][^1_7].

Con el ejemplo que has proporcionado, puedes explicar los conceptos clave de JSON:

### 1. Objetos en JSON

Un **objeto** en JSON se define utilizando llaves `{}` y dentro contiene uno o más pares **clave-valor** separados por comas.
En tu ejemplo, todo el bloque está dentro de un objeto:

```json
{
  "curso": "IFCD0609_202402",
  ...
}
```

- **"curso"** es una clave, y su valor es una cadena de texto ("IFCD0609_202402").


### 2. Pares clave-valor

Cada dato dentro de un objeto es un **par clave-valor**.
La clave (siempre entre comillas dobles) identifica el dato, y el valor puede ser de distintos tipos: texto, número, booleano, objeto, array, etc.[^1_1][^1_3][^1_9].
Por ejemplo:

- `"fecha inicio": "2024-02-14"`
Clave: **"fecha inicio"**
Valor: **"2024-02-14"** (cadena de texto)


### 3. Objetos anidados

En JSON, los **valores** de una clave también pueden ser otros objetos JSON, permitiendo una estructura *jerárquica* o de árbol[^1_1][^1_4].
Por ejemplo, `"tutor"` es un objeto anidado con sus propios pares clave-valor:

```json
"tutor": {
  "Nombre": "Alberto Mozo",
  "email": "albertomozodocente@gmail.com",
  "linked": "...",
  "github": "..."
}
```


### 4. Arrays en JSON

Un **array** (arreglo) se representa con corchetes `[]` y contiene una lista ordenada de elementos, que pueden ser valores simples u objetos[^1_3][^1_5][^1_9].
En tu ejemplo:

```json
"alumnos": [
  { ... }, 
  { ... }, 
  ...
]
```

- `"alumnos"` es un array que contiene varios objetos, uno por cada alumno.


### 5. Tipos de datos en JSON

Dentro de JSON puedes usar varios **tipos de datos**:

- **Cadenas de texto:** entre comillas dobles, como `"Nombre": "Alumno1"`
- **Números:** sin comillas, como `"html": 1`
- **Booleanos:** `true` o `false` (no aparecen en tu ejemplo, pero son soportados)
- **null:** para valores vacíos (no aparece en tu ejemplo)
- **Arrays:** como el de `"alumnos"`
- **Objetos:** como cada alumno o el tutor[^1_7][^1_9]


### 6. Objetos y arrays combinados

El poder de JSON está en que puedes **combinar arrays y objetos** para estructurar información compleja.
Por ejemplo, cada alumno posee claves simples ("Nombre", "email") y también objetos anidados ("inicio" y "fin"):

```json
"inicio": {
  "html": 2,
  "css": 3,
  "JS": 1,
  "Vue": 3
}
```


### Resumiendo con tu ejemplo

- **El JSON** representa un curso, con información general, el tutor y varios alumnos.
- **Cada alumno** tiene datos personales y sus niveles al inicio y al final en varias materias (cada uno es otro objeto).
- **Estructura**:
    - Un objeto principal
    - Dentro, claves simples, un objeto (tutor) y un array de objetos (alumnos), que contienen otros objetos.

Así puedes explicar que **JSON** usa una estructura clara de pares clave-valor, permite anidamiento de objetos, y soporta arrays para representar listas de elementos, haciéndolo ideal para estructurar y transmitir información entre sistemas.

<div style="text-align: center">⁂</div>



