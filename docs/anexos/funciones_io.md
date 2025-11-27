# Anexo I · funcionesIO.java

Este archivo agrupa funciones reutilizables para entrada/salida básica. Colócalo en la misma carpeta que tus programas y podrás llamarlo desde cualquier clase.

## Código listo para usar

```java
import java.util.Scanner;

public class FuncionesIO {
    private static final Scanner TECLADO = new Scanner(System.in);

    public static int leerEntero(String pregunta) {
        while (true) {
            try {
                System.out.print(pregunta);
                int numero = TECLADO.nextInt();
                TECLADO.nextLine();
                return numero;
            } catch (Exception e) {
                TECLADO.nextLine();
                System.out.println("Introduce un número entero válido.");
            }
        }
    }

    public static float leerFloat(String pregunta) {
        while (true) {
            try {
                System.out.print(pregunta);
                float numero = TECLADO.nextFloat();
                TECLADO.nextLine();
                return numero;
            } catch (Exception e) {
                TECLADO.nextLine();
                System.out.println("Introduce un número con decimales válido.");
            }
        }
    }

    public static String leerLinea(String pregunta) {
        System.out.print(pregunta);
        return TECLADO.nextLine();
    }

    public static char leerCaracter(String pregunta) {
        System.out.print(pregunta);
        String texto = TECLADO.nextLine();
        return texto.isEmpty() ? '\0' : texto.charAt(0);
    }
}
```

## Cómo usarlo

```java
public class Demo {
    public static void main(String[] args) {
        int edad = FuncionesIO.leerEntero("¿Cuántos años tienes? ");
        float precio = FuncionesIO.leerFloat("Precio del artículo: ");
        String nombre = FuncionesIO.leerLinea("Nombre: ");
        char turno = FuncionesIO.leerCaracter("Turno (M/T/N): ");

        System.out.println(nombre + " | " + edad + " | " + precio + " | " + turno);
    }
}
```

!!! tip "Ventajas"
    - Centralizas la validación.
    - Evitas repetir `try-catch` en cada programa.
    - Limpias el buffer `nextLine()` dentro de cada función.

Modifica o amplía estas funciones a medida que el temario avance (por ejemplo, para leer rangos concretos o menús).