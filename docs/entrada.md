# 6 · Entrada de datos

Leer desde teclado en Java requiere crear objetos que conecten el flujo de entrada con tu programa. Veremos **Scanner**, **BufferedReader** y una librería casera.

## 6.1 Lectura con `Scanner`

1. **Importa** la clase:

```java
import java.util.Scanner;
```

2. **Crea** el escáner apuntando a `System.in` (teclado):

```java
Scanner teclado = new Scanner(System.in);
```

3. **Usa** los métodos según el tipo:

```java
String nombre = teclado.nextLine(); // varias palabras
int edad = teclado.nextInt();       // entero
float altura = teclado.nextFloat(); // real
char letra = teclado.next().charAt(0); // primer carácter leído
```

Ejemplo completo:

```java
import java.util.Scanner;

public class LecturaTeclado {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("¿Cómo te llamas? ");
        String nombre = teclado.nextLine();

        System.out.print("¿Cuántos años tienes? ");
        int edad = teclado.nextInt();

        System.out.print("¿Cuánto mides (en metros)? ");
        float altura = teclado.nextFloat();

        System.out.println("Hola " + nombre + "!");
        System.out.println("Tienes " + edad + " años y " + (altura * 100) + " cm.");
    }
}
```

!!! warning "Problema del buffer con Scanner"
    Después de leer números (`nextInt`, `nextFloat`), queda un salto de línea pendiente. Si luego llamas a `nextLine()`, consumirá esa línea vacía. Solución: llama a `teclado.nextLine();` justo después de la lectura numérica para limpiar el buffer.

### Manejo manual del buffer

```java
int edad = teclado.nextInt();
teclado.nextLine(); // limpia la línea pendiente
String nombre = teclado.nextLine();
```

## 6.2 Lectura con `BufferedReader`

1. **Importa** las clases IO:

```java
import java.io.*;
```

2. **Crea** el lector:

```java
BufferedReader teclado = new BufferedReader(new InputStreamReader(System.in));
```

3. **Lee** siempre cadenas y luego convierte:

```java
try {
    System.out.print("¿Cómo te llamas? ");
    String nombre = teclado.readLine();

    System.out.print("¿Cuántos años tienes? ");
    int edad = Integer.parseInt(teclado.readLine());

    System.out.print("¿Cuánto mides (en metros)? ");
    float altura = Float.parseFloat(teclado.readLine());
} catch (IOException e) {
    System.out.println("Error en la entrada de datos");
}
```

!!! warning "Obligatorio try-catch"
    `readLine()` puede lanzar `IOException`, así que debes envolver la lectura en un bloque `try-catch`.

### Conversión de `String` a números

Usa las *wrapper classes*:

| Tipo | Método |
| --- | --- |
| `int` | `Integer.parseInt(cadena)` |
| `float` | `Float.parseFloat(cadena)` |
| `double` | `Double.parseDouble(cadena)` |
| `long` | `Long.parseLong(cadena)` |
| `boolean` | `Boolean.parseBoolean(cadena)` |

Para leer un único carácter:

```java
char letra = teclado.readLine().charAt(0);
```

### Conversión inversa (número → String)

```java
String texto = String.valueOf(numero); // o numero + ""
```

## 6.3 Funciones caseras de entrada

Puedes crear una clase utilitaria con métodos reutilizables (ver [Anexo de funciones IO](anexos/funciones_io.md)).

Ejemplo básico:

```java
import java.util.Scanner;

public class FuncionesIO {
    static Scanner teclado = new Scanner(System.in);

    public static int leerEntero(String pregunta) {
        while (true) {
            try {
                System.out.print(pregunta);
                int numero = teclado.nextInt();
                teclado.nextLine();
                return numero;
            } catch (Exception e) {
                teclado.nextLine();
                System.out.println("Debes escribir un número entero.");
            }
        }
    }
}
```

Y en tu `main`:

```java
int edad = FuncionesIO.leerEntero("¿Cuántos años tienes? ");
```

## 6.4 Scanner vs BufferedReader

| Aspecto | `Scanner` | `BufferedReader` |
| --- | --- | --- |
| Lectura de números | Directa (`nextInt`) | Lee cadenas → convierte |
| Manejo de errores | Opcional | Obligatorio (`try-catch`) |
| Buffer | Debes limpiarlo | No hace falta |
| Separador decimal | Usa coma por defecto (puedes cambiar a punto con `useLocale`) | Usa punto |

Elige `Scanner` para empezar y `BufferedReader` cuando necesites más control o leer ficheros.

Con la entrada y salida cubiertas, en el siguiente bloque vemos cómo tomar decisiones y repetir código.