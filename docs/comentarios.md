# 9 · Comentarios en Java

Los comentarios explican tu código al resto del equipo (o a tu yo del futuro). El compilador los ignora.

## 9.1 Una sola línea

```java
float cantidad; // Guardará el importe en euros
char turno;    // 'N' si es nocturno, 'D' si es diurno
```

Se inician con `//` y llegan hasta el final de la línea.

## 9.2 Varias líneas

```java
/*
Autor: Equipo DAW
Fecha: 01-11-2024
Descripción: Explicar tipos de comentario
*/
```

Empezar con `/*` y terminar con `*/`.

## 9.3 Javadoc

Perfecto para documentar clases y métodos. Empieza con `/**`.

```java
/**
 * Calcula la suma de dos enteros.
 * @param a primer sumando
 * @param b segundo sumando
 * @return suma de a y b
 */
public static int sumar(int a, int b) {
    return a + b;
}
```

Si luego ejecutas `javadoc`, obtendrás documentación HTML basada en estos comentarios.

!!! tip "Documenta solo lo necesario"
    - Usa comentarios para explicar decisiones, no para repetir lo obvio.
    - Mantén actualizados los comentarios al modificar el código.
    - Prefiere nombres descriptivos antes que comentarios excesivos.

Listo: ya tienes todas las herramientas para escribir código claro y entendible.