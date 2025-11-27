# Funcionetes · Librería de entrada personalizada

Para evitar repetir `Scanner` o `BufferedReader` en cada actividad, trabajaremos con la clase `Funcionetes`. Debes guardar el fichero `Funcionetes.java` en el mismo paquete que tus ejercicios y llamarlo con métodos estáticos como `Funcionetes.lligInt("Pregunta: ")`.

## Código completo

```java
import java.util.Locale;
import java.util.Scanner;
import javax.swing.JOptionPane;

public class Funcionetes {
    static Scanner teclat = new Scanner(System.in);
    // Si prefieres el punto como separador decimal, usa:
    // static Scanner teclat = new Scanner(System.in).useLocale(Locale.US);

    public static int lligInt(String pregunta) {
        int numero;
        do {
            try {
                System.out.print(pregunta);
                numero = teclat.nextInt();
                teclat.nextLine();
                return numero;
            } catch (Exception e) {
                System.out.print("Ha de ser un número enter: ");
                teclat.nextLine();
            }
        } while (true);
    }

    public static long lligLong(String pregunta) {
        long numero;
        do {
            try {
                System.out.print(pregunta);
                numero = teclat.nextLong();
                teclat.nextLine();
                return numero;
            } catch (Exception e) {
                System.out.print("Ha de ser un número enter: ");
                teclat.nextLine();
            }
        } while (true);
    }

    public static float lligFloat(String pregunta) {
        float numero;
        do {
            try {
                System.out.print(pregunta);
                numero = teclat.nextFloat();
                teclat.nextLine();
                return numero;
            } catch (Exception e) {
                System.out.print("Ha de ser un número real: ");
                teclat.nextLine();
            }
        } while (true);
    }

    public static double lligDouble(String pregunta) {
        double numero;
        do {
            try {
                System.out.print(pregunta);
                numero = teclat.nextDouble();
                teclat.nextLine();
                return numero;
            } catch (Exception e) {
                System.out.print("Ha de ser un número real: ");
                teclat.nextLine();
            }
        } while (true);
    }

    public static char lligLletra(String pregunta) {
        System.out.print(pregunta);
        return teclat.nextLine().charAt(0);
    }

    public static String lligText(String pregunta) {
        System.out.print(pregunta);
        return teclat.nextLine();
    }

    public static void printMG(String missatge) {
        JOptionPane.showMessageDialog(null, missatge);
    }

    public static String lligTextG(String missatge) {
        String llegit = JOptionPane.showInputDialog(missatge);
        return (llegit == null) ? "" : llegit;
    }

    public static char lligLletraG(String missatge) {
        String llegit = JOptionPane.showInputDialog(missatge);
        return (llegit == null || llegit.isEmpty()) ? ' ' : llegit.charAt(0);
    }

    public static float lligFloatG(String missatge) {
        return Float.parseFloat(lligTextG(missatge));
    }

    public static double lligDoubleG(String missatge) {
        return Double.parseDouble(lligTextG(missatge));
    }

    public static int lligIntG(String missatge) {
        return Integer.parseInt(lligTextG(missatge));
    }

    public static long lligLongG(String missatge) {
        return Long.parseLong(lligTextG(missatge));
    }
}
```

## Cómo usarla en los ejercicios

- Sustituye cualquier `Scanner teclado = new Scanner(System.in);` por llamadas directas como `int num = Funcionetes.lligInt("Número: ");`.
- Para decimales usa `lligFloat` o `lligDouble` según necesites.
- Si necesitas letras o cadenas, llama a `lligLletra` o `lligText`.
- Los métodos con sufijo `G` permiten leer mediante cuadros de diálogo (`JOptionPane`).

A partir del **Ejercicio 7** las soluciones usan `Funcionetes` para mantener el mismo estilo de entrada que se emplea en clase.
