# 3 · Tipos de datos y constantes

## 3.1 Tipado fuerte en Java

Java **requiere declarar el tipo** de cada variable antes de usarla. Eso implica:

- Decir si la variable guarda enteros, reales, caracteres, etc.
- Respetar el tipo al asignar valores.
- Especificar el tipo de retorno de cada función.

```java
int edad = 20;
double altura;
boolean aprobado = false;
```

Cada instrucción termina con `;`.

## 3.2 Tipos primitivos

| Tipo | Categoría | Tamaño | Rango / valores |
| --- | --- | --- | --- |
| `boolean` | Lógico | 1 bit | `true` o `false` |
| `char` | Carácter (Unicode) | 2 bytes | 0 a 2^16 − 1 |
| `byte` | Entero | 1 byte | −128 a 127 |
| `short` | Entero | 2 bytes | −32 768 a 32 767 |
| `int` | Entero | 4 bytes | −2 147 483 648 a 2 147 483 647 |
| `long` | Entero | 8 bytes | −2^63 a 2^63 − 1 |
| `float` | Real | 4 bytes | ~ ±3.4E38 |
| `double` | Real | 8 bytes | ~ ±1.7E308 |

!!! tip "Diferencias con Python"
    - `boolean` usa minúsculas: `true`, `false`.
    - No existe `str` como tipo primitivo: las cadenas son objetos `String`.
    - `char` solo admite un carácter y se declara con comillas simples `'A'`.

## 3.3 Identificadores y valores

Para cada variable debes tener presente:

- **Tipo**: define el dominio de valores y operaciones permitidas.
- **Identificador**: nombre con el que accedes a la variable.
- **Valor**: dato almacenado en memoria (puede estar sin inicializar si usas variables de instancia; en locales debes inicializar antes de leer).

## 3.4 Declaración de constantes

Usa `final` para impedir que cambie el valor:

```java
final double PI = 3.141592;
final int IVA = 21;
final char BOMBA = 'Q';
```

Convención: nombres en mayúsculas y con guiones bajos si son compuestos (`MAX_INTENTOS`).

## 3.5 Palabras reservadas

No puedes usarlas como nombres de variables, métodos o clases.

```
abstract  continue  finally   int        public     throw
assert    default   float     interface  return     throws
boolean   do        for       long       short      transient
break     double    goto      native     static     true
byte      else      if        new        strictfp   try
case      enum      implements null      super      void
catch     extends   import    package    switch     volatile
class     false     instanceof private   synchronized while
const     final     this      protected  this       
```

## 3.6 Reglas para nombrar

- Empieza por letra, `_` o `$` (evita `$`).
- Puede contener números pero no empezar con ellos.
- Java distingue mayúsculas/minúsculas.
- Usa *camelCase* para variables y *PascalCase* para clases.

## 3.7 Consejos rápidos

!!! tip "Buenas prácticas"
    - Declara la variable justo antes de usarla.
    - Prefiere el tipo más pequeño que necesites (`int` en lugar de `long` si cabe).
    - Usa `var` solo a partir de Java 10 si el profesor lo permite.

Con los tipos controlados, pasamos a los operadores para manipular esos datos.