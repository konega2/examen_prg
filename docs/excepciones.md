# 8 · Tratamiento de excepciones

Una **excepción** es un error en tiempo de ejecución que puede detener el programa (dividir por cero, leer mal datos, etc.). Java permite capturarlas para reaccionar sin que todo reviente.

## 8.1 Estructura `try-catch-finally`

```java
try {
    // Código que puede fallar
} catch (TipoDeExcepcion e) {
    // Qué hacer si ocurre ese error
} finally {
    // Código que se ejecuta SIEMPRE (opcional)
}
```

Puedes tener varios `catch` si quieres tratar errores diferentes.

## 8.2 Ejemplo completo

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Excepciones {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int alumnos, ordenadores;
        float media;

        System.out.println("Calculemos la media de ordenadores por alumno");
        try {
            System.out.print("¿Cuántos alumnos? ");
            alumnos = teclado.nextInt();
            System.out.print("¿Cuántos ordenadores? ");
            ordenadores = teclado.nextInt();

            media = (float) ordenadores / alumnos;
            if (ordenadores >= alumnos) {
                System.out.println("Cada alumno tiene ordenador propio");
            } else {
                System.out.println("1 ordenador cada " + media + " alumnos");
            }
        } catch (ArithmeticException ae) {
            System.out.println("Sin alumnos no hay media");
        } catch (InputMismatchException ime) {
            System.out.println("Debes introducir números enteros");
        } finally {
            System.out.println("¡Fin del cálculo!");
        }
    }
}
```

## 8.3 Jerarquía básica

| Error común | Clase de excepción |
| --- | --- |
| División por cero | `ArithmeticException` |
| Entrada no numérica con `Scanner` | `InputMismatchException` |
| Lectura/escritura fallida | `IOException` |
| Índice fuera de rango | `ArrayIndexOutOfBoundsException` |

!!! tip "Buenas prácticas"
    - Captura solo lo que puedas gestionar.
    - Muestra mensajes claros al usuario.
    - Usa `finally` para cerrar recursos (ficheros, conexiones, etc.).

Practica con el [Ejercicio 20](ejercicios.md) para entender el flujo cuando ocurren distintas excepciones.