
### 1. ¿Qué es un objeto en JSON?

- Es una **colección de pares clave-valor** encerrada entre llaves `{ }`
- Una **clave** siempre es una cadena entre comillas dobles.
- El **valor** puede ser una cadena, número, booleano, objeto, array o `null`.


### 2. Sintaxis básica

```json
{
  "clave1": "valor1",
  "clave2": 123,
  "clave3": true,
  "clave4": ["valorA", "valorB"],
  "clave5": {
    "subclave": "subvalor"
  }
}
```


### 3. Características principales

- Los pares clave-valor se **separan por comas**[^1][^2][^3].
- Las **claves** se escriben SIEMPRE entre **comillas dobles**.
- Pueden estar **anidados** (objetos dentro de objetos)[^2][^3].
- Los **objetos** son ideales para describir entidades completas, por ejemplo, un usuario:

```json
{
  "nombre": "Ana",
  "edad": 25,
  "perfil": {
    "profesion": "Ingeniera",
    "pais": "España"
  }
}
```


### 4. Tipos de valores soportados

| Tipo | Ejemplo |
| :-- | :-- |
| Número | `"edad": 38` |
| Cadena | `"nombre": "Ana"` |
| Booleano | `"activo": true` |
| Objeto | `"perfil": {"pais": "España"}` |
| Array | `"hobbies": ["leer", "viajar", "correr"]` |
| Null | `"direccion": null` |

[^3]

### 5. Buenas prácticas

- Mantén las claves consistentes y descriptivas.
- No uses comas al final del último par.
- Utiliza **comillas dobles** para todas las claves y cadenas.
- El formato es **sensible** a pequeñas fallas de sintaxis.


### 6. ¿Para qué se usan los objetos en JSON?

- **Almacenar** y **transmitir** información en la web[^1][^2][^10].
- Estructurar respuestas de APIs o archivos de configuración[^1][^2][^10].
- Facilitar la interoperabilidad entre sistemas.

Conoce estas reglas y tendrás la base para entender, crear y leer objetos en JSON de forma efectiva[^1][^2][^3].

<div style="text-align: center">⁂</div>

[^1]: https://www.hostingtg.com/blog/guia-completa-json/

[^2]: https://apidog.com/es/blog/json-api-responses-4/

[^3]: https://dinahosting.com/blog/guia-sobre-json/

[^4]: https://developer.mozilla.org/es/docs/Learn_web_development/Core/Scripting/JSON

[^5]: https://es.javascript.info/json

[^6]: https://www.youtube.com/watch?v=YYfediyCwAU

[^7]: https://www.hostinet.com/formacion/diseno-web/json/

[^8]: https://www.youtube.com/watch?v=JrsToGENE4Q

[^9]: https://docs.teradata.com/r/v9bmEGRxIXSPfbhmbVFE_g/W9E2UuCuzeGR1aKGiAQX_g?contentId=D7y~pA_XmzP5SIgTkJoHiA

[^10]: https://www.labiznagadigital.es/blog/archivo-json/

