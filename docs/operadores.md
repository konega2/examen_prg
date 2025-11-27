# 4 · Operadores en Java

## 4.1 Tabla general (orden de prioridad)

| Categoría | Operadores en Java | Asociatividad |
| --- | --- | --- |
| Paréntesis / arrays | `( )`, `[ ]` | Izquierda |
| Unarios | `++`, `--`, `+`, `-`, `!` | Derecha |
| Multiplicación | `*`, `/`, `%` | Izquierda |
| Suma / resta | `+`, `-` | Izquierda |
| Relacionales | `<`, `<=`, `>`, `>=`, `==`, `!=` | Izquierda |
| Lógicos | `&&`, `||`, `!`, `^` | Izquierda (excepto `!`) |
| Ternario | `?:` | Derecha |
| Asignación | `=`, `+=`, `-=`, `*=`, `/=`, `%=` | Derecha |

!!! info "Diferencias con Python"
    - No existe `**` para potencias (usa `Math.pow`).
    - El operador `//` (división entera) no existe: combina `/` entre enteros o usa `Math.floorDiv`.
    - Aparece el `^` lógico (OR exclusivo) y los incrementos `++`, `--`.

## 4.2 Operador XOR `^`

| `x` | `y` | `x ^ y` |
| --- | --- | --- |
| false | false | false |
| false | true | true |
| true | false | true |
| true | true | false |

Solo devuelve `true` cuando **exactamente un** operando es `true`.

## 4.3 Incrementos `++` y decrementos `--`

```java
int x = 10;
x++; // ahora vale 11
```

Dentro de expresiones importa la posición:

- `++x`: primero incrementa, luego usa el valor.
- `x++`: primero usa el valor, luego incrementa.

```java
int a = 5;
int b = ++a; // a = 6, b = 6
int c = a++; // a = 7, c = 6
```

## 4.4 Operador ternario `?:`

Sintaxis:

```java
resultado = condicion ? valorSiTrue : valorSiFalse;
```

Ejemplo:

```java
int mayor = (a > b) ? a : b;
```

Puedes anidar ternarios, pero si no queda claro mejor usa `if`.

## 4.5 Resumen visual

- **Aritméticos**: `+ - * / %`.
- **Relacionales**: comparan dos valores y devuelven `boolean`.
- **Lógicos**: combinan condiciones (`&&`, `||`, `!`, `^`).
- **Asignación compuesta**: `x += 2` equivale a `x = x + 2`.
- **Concatenación**: `"Hola" + nombre` produce un `String`.

!!! tip "Evita errores comunes"
    - No confundas `=` (asignación) con `==` (comparación).
    - El operador `%` devuelve el **resto** de una división.
    - Cuando mezcles `int` y `double` en operaciones, el resultado se promociona a `double`.

Practica estos operadores en los [ejercicios finales](ejercicios.md) para afianzar la teoría.