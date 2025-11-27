# 7 · Estructuras de control

En Java todo el código vive dentro de **clases** y, dentro de ellas, en **métodos**. El punto de entrada sigue siendo `public static void main(String[] args)`.

## 7.1 Bifurcaciones (`if`, `if-else`)

```java
if (condicion) {
    // bloque verdadero
} else {
    // bloque falso
}
```

Ejemplo:

```java
if (a < b) {
    System.out.println("El menor es: " + a);
} else if (a > b) {
    System.out.println("El menor es: " + b);
} else {
    System.out.println("Son iguales");
}
```

!!! tip "Claves"
    - La condición va entre paréntesis.
    - Los bloques se encierran entre `{ }` (llaves). Indenta siempre aunque tengas una sola línea.

## 7.2 `switch`

Ideal cuando una variable puede tomar pocos valores discretos (`int`, `char`, `String`).

```java
switch (nota) {
    case 0: case 1: case 2: case 3: case 4:
        System.out.println("INS");
        break;
    case 5:
        System.out.println("SUF");
        break;
    case 6:
        System.out.println("BÉ");
        break;
    case 7: case 8:
        System.out.println("NOT");
        break;
    case 9: case 10:
        System.out.println("EXC");
        break;
    default:
        System.out.println("Error: nota fuera de rango");
}
```

!!! warning "No olvides el `break`"
    Si omites `break`, Java ejecutará el código del `case` actual **y** todos los siguientes hasta encontrar uno.

## 7.3 Bucles condicionales `while`

```java
while (condicion) {
    // se repite mientras la condición sea true
}
```

Si la condición es falsa desde el principio, el cuerpo puede no ejecutarse nunca.

## 7.4 Bucle `do-while`

```java
do {
    // acciones
} while (condicion);
```

- Ejecuta el cuerpo **al menos una vez**.
- Ideal para menús que deben mostrarse una vez antes de preguntar si continúas.

## 7.5 Bucle `for`

```java
for (inicializacion; condicion; actualizacion) {
    // cuerpo
}
```

Ejemplo: números del 1 al 9

```java
for (int i = 1; i < 10; i++) {
    System.out.println(i);
}
```

### Variantes frecuentes

| Objetivo | For recomendado |
| --- | --- |
| Contar de 10 a 30 de 5 en 5 | `for (int i = 10; i <= 30; i += 5)` |
| Contar hacia atrás | `for (int i = 10; i > 3; i--)` |
| Bucle infinito (evitar) | `for(;;)` o condiciones que nunca se vuelven falsas |

## 7.6 Consejos prácticos

- Usa `while`/`do-while` cuando **no sabes cuántas veces** repetirás el bloque.
- Usa `for` cuando el número de iteraciones está claro o depende de un contador.
- Rompe bucles con `break` si detectas una condición de salida interna.
- Usa `continue` para saltar a la siguiente iteración.

Todos los ejemplos de este bloque se practican en los [ejercicios 7 a 19](ejercicios.md).