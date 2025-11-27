# 10 · Ejercicios resueltos (modo chuleta)

Cada ejercicio incluye **enunciado**, **solución mínima** y **explicación "para tontos"**. Se usan solo los conceptos vistos hasta ese punto del temario.

---

### Ejercicio 1 · Operadores aritméticos incrementales

**Enunciado**

Declara una variable entera `x`, súmale 1 con `x++` y muestra en consola el valor antes y después del incremento.

**Solución en Java**

```java
public class Ejercicio01 {
    public static void main(String[] args) {
        int x = 10;
        System.out.println("Valor inicial: " + x);
        x++;
        System.out.println("Tras x++: " + x);
    }
}
```

**Explicación para tontos**

1. Creamos `x` con valor 10.
2. Mostramos ese valor.
3. Usamos `x++` para sumarle 1 automáticamente.
4. Volvemos a imprimir para ver el cambio.

---

### Ejercicio 2 · Preincremento vs postincremento

**Enunciado**

Muestra cómo cambian dos variables cuando usas `++x` y `y++` dentro de una asignación.

**Solución en Java**

```java
public class Ejercicio02 {
    public static void main(String[] args) {
        int x = 5;
        int y = 5;
        int a = ++x;
        int b = y++;

        System.out.println("x = " + x + ", a = " + a);
        System.out.println("y = " + y + ", b = " + b);
    }
}
```

**Explicación para tontos**

- `++x` incrementa antes y asigna después.
- `y++` asigna primero y luego incrementa, por eso `b` mantiene el valor antiguo.

---

### Ejercicio 3 · Operador condicional ternario

**Enunciado**

Pide tres enteros y muestra el mayor y el menor usando únicamente el operador `?:`.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio03 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Número 1: ");
        int a = teclado.nextInt();
        System.out.print("Número 2: ");
        int b = teclado.nextInt();
        System.out.print("Número 3: ");
        int c = teclado.nextInt();

        int mayor = (a > b) ? a : b;
        mayor = (mayor > c) ? mayor : c;

        int menor = (a < b) ? a : b;
        menor = (menor < c) ? menor : c;

        System.out.println("Mayor: " + mayor);
        System.out.println("Menor: " + menor);
    }
}
```

**Explicación para tontos**

- El ternario elige entre dos valores según una condición.
- Reutilizamos `mayor` y `menor` para comparar con el tercer número.

---

### Ejercicio 4 · Ventas con `Scanner`

**Enunciado**

Solicita: nombre del artículo, unidades (enteras) y precio unitario (decimal). Muestra "X unidades de ART a PRECIO son TOTAL euros".

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio04 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Artículo: ");
        String articulo = teclado.nextLine();
        System.out.print("Unidades: ");
        int unidades = teclado.nextInt();
        System.out.print("Precio unitario: ");
        float precio = teclado.nextFloat();

        float total = unidades * precio;
        System.out.println(unidades + " " + articulo + " a " + precio + " la unidad son " + total + " euros");
    }
}
```

**Explicación para tontos**

- `Scanner` lee texto y números.
- Multiplicamos unidades * precio y mostramos todo en una frase.

---

### Ejercicio 5 · Problema del buffer con `Scanner`

**Enunciado**

Primero pide las unidades (int) y después el nombre del artículo. Asegúrate de que el `nextLine()` que lee el nombre funcione correctamente.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio05 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Unidades: ");
        int unidades = teclado.nextInt();
        teclado.nextLine();
        System.out.print("Artículo: ");
        String articulo = teclado.nextLine();
        System.out.println("Has pedido " + unidades + " unidad(es) de " + articulo);
    }
}
```

**Explicación para tontos**

- Tras `nextInt()` queda un salto de línea pendiente.
- Llamamos a `nextLine()` vacío para consumirlo antes de leer el nombre real.

---

### Ejercicio 6 · Datos de un paciente con `BufferedReader`

**Enunciado**

Lee con `BufferedReader`: nombre, edad, peso (decimal) y sexo (`h/d/a`). Muestra los datos en una sola línea.

**Solución en Java**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Ejercicio06 {
    public static void main(String[] args) {
        BufferedReader teclado = new BufferedReader(new InputStreamReader(System.in));
        try {
            System.out.print("Nombre: ");
            String nombre = teclado.readLine();
            System.out.print("Edad: ");
            int edad = Integer.parseInt(teclado.readLine());
            System.out.print("Peso (kg): ");
            float peso = Float.parseFloat(teclado.readLine());
            System.out.print("Sexo (h/d/a): ");
            char sexo = teclado.readLine().charAt(0);

            System.out.println(nombre + " | " + edad + " años | " + peso + " kg | Sexo: " + sexo);
        } catch (IOException e) {
            System.out.println("Error en la entrada de datos");
        }
    }
}
```

**Explicación para tontos**

- `readLine()` devuelve texto, así que convertimos con `Integer.parseInt` y `Float.parseFloat`.
- `charAt(0)` se queda con la primera letra para el sexo.
- Usamos `try-catch` obligatorio en lecturas con `BufferedReader`.

---

### Ejercicio 7 · Mayor de tres números (if-else)

**Enunciado**

Pide tres enteros y muestra el mayor con `if-else`.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio07 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Número 1: ");
        int a = teclado.nextInt();
        System.out.print("Número 2: ");
        int b = teclado.nextInt();
        System.out.print("Número 3: ");
        int c = teclado.nextInt();

        int mayor = a;
        if (b > mayor) {
            mayor = b;
        }
        if (c > mayor) {
            mayor = c;
        }

        System.out.println("El mayor es " + mayor);
    }
}
```

**Explicación para tontos**

- Suponemos que el mayor es el primero.
- Si encontramos uno más grande, reemplazamos.

---

### Ejercicio 8 · Notas con if-else (decimales)

**Enunciado**

Pide una nota decimal (0–10) y muestra `ins`, `suf`, `bé`, `not`, `exc` o `error` si está fuera de rango.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio08 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Nota (0-10): ");
        double nota = teclado.nextDouble();

        if (nota < 0 || nota > 10) {
            System.out.println("error");
        } else if (nota < 5) {
            System.out.println("ins");
        } else if (nota < 6) {
            System.out.println("suf");
        } else if (nota < 7) {
            System.out.println("bé");
        } else if (nota < 9) {
            System.out.println("not");
        } else {
            System.out.println("exc");
        }
    }
}
```

**Explicación para tontos**

- Comprobamos el rango primero.
- Luego vamos cubriendo tramos crecientes de nota.

---

### Ejercicio 9 · Notas con `switch` (enteros)

**Enunciado**

Pide una nota entera y muestra el texto correspondiente usando `switch`. Si está fuera de 0–10, muestra `error`.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio09 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Nota entera (0-10): ");
        int nota = teclado.nextInt();

        switch (nota) {
            case 0: case 1: case 2: case 3: case 4:
                System.out.println("ins");
                break;
            case 5:
                System.out.println("suf");
                break;
            case 6:
                System.out.println("bé");
                break;
            case 7: case 8:
                System.out.println("not");
                break;
            case 9: case 10:
                System.out.println("exc");
                break;
            default:
                System.out.println("error");
        }
    }
}
```

**Explicación para tontos**

- Agrupamos casos sin repetir código.
- `default` cubre notas no válidas.

---

### Ejercicio 10 · Mini calculadora con `switch`

**Enunciado**

Lee dos números y un carácter (`s/+`, `r/-`, `m/*/x`, `d/`/) y realiza la operación indicada.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio10 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Número A: ");
        double a = teclado.nextDouble();
        System.out.print("Número B: ");
        double b = teclado.nextDouble();
        teclado.nextLine();
        System.out.print("Operación (s/r/m/d): ");
        char op = teclado.nextLine().charAt(0);

        double resultado;
        switch (op) {
            case 's': case 'S': case '+':
                resultado = a + b;
                break;
            case 'r': case 'R': case '-':
                resultado = a - b;
                break;
            case 'm': case 'M': case '*': case 'x': case 'X':
                resultado = a * b;
                break;
            case 'd': case 'D': case '/':
                if (b == 0) {
                    System.out.println("No se puede dividir entre cero");
                    return;
                }
                resultado = a / b;
                break;
            default:
                System.out.println("Operación no válida");
                return;
        }
        System.out.println("Resultado: " + resultado);
    }
}
```

**Explicación para tontos**

- Aceptamos varias letras/símbolos para cada operación.
- Si la operación no existe o b es 0, avisamos y salimos.

---

### Ejercicio 11 · Adivinar un cuadrado

**Enunciado**

Pide un número y luego pregunta continuamente por su cuadrado hasta que el usuario acierte.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio11 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Número base: ");
        int numero = teclado.nextInt();
        int esperado = numero * numero;
        int respuesta;

        do {
            System.out.print("¿Cuál es su cuadrado? ");
            respuesta = teclado.nextInt();
        } while (respuesta != esperado);

        System.out.println("¡Correcto!");
    }
}
```

**Explicación para tontos**

- Calculamos el cuadrado una vez.
- Usamos `do-while` para que la pregunta salga mínimo una vez.

---

### Ejercicio 12 · Estadísticas con nota -1

**Enunciado**

Pide notas hasta que se introduzca `-1`. Muestra la media, cuántas aprobadas y cuántas suspensas.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio12 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int suma = 0;
        int contador = 0;
        int aprobadas = 0;
        int suspensas = 0;

        while (true) {
            System.out.print("Nota (-1 para terminar): ");
            int nota = teclado.nextInt();
            if (nota == -1) {
                break;
            }
            suma += nota;
            contador++;
            if (nota >= 5) {
                aprobadas++;
            } else {
                suspensas++;
            }
        }

        if (contador > 0) {
            double media = (double) suma / contador;
            System.out.println("Media: " + media);
            System.out.println("Aprobadas: " + aprobadas);
            System.out.println("Suspensas: " + suspensas);
        } else {
            System.out.println("No se introdujeron notas");
        }
    }
}
```

**Explicación para tontos**

- `while(true)` y `break` al ver `-1`.
- Contamos todos los datos para la media.

---

### Ejercicio 13 · Números del 10 al 20

**Enunciado**

Muestra los números del 10 al 20 incluidos.

**Solución en Java**

```java
public class Ejercicio13 {
    public static void main(String[] args) {
        for (int i = 10; i <= 20; i++) {
            System.out.println(i);
        }
    }
}
```

**Explicación para tontos**

- Bucle `for` que arranca en 10 y termina en 20.

---

### Ejercicio 14 · Números del 20 al 10 de 3 en 3

**Enunciado**

Muestra los números desde 20 hasta 10, restando 3 cada vez.

**Solución en Java**

```java
public class Ejercicio14 {
    public static void main(String[] args) {
        for (int i = 20; i >= 10; i -= 3) {
            System.out.println(i);
        }
    }
}
```

**Explicación para tontos**

- Empezamos en 20 y restamos 3 cada vuelta hasta bajar de 10.

---

### Ejercicio 15 · Tabla de multiplicar personalizada

**Enunciado**

Pide un número y muestra su tabla de multiplicar del 1 al 10.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio15 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Tabla del: ");
        int n = teclado.nextInt();
        for (int i = 1; i <= 10; i++) {
            System.out.println(n + " x " + i + " = " + (n * i));
        }
    }
}
```

**Explicación para tontos**

- El contador va de 1 a 10 y multiplicamos por `n`.

---

### Ejercicio 16 · Máximo de 10 números

**Enunciado**

Lee 10 números y muestra el mayor de todos.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio16 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int maximo = Integer.MIN_VALUE;
        for (int i = 1; i <= 10; i++) {
            System.out.print("Número " + i + ": ");
            int n = teclado.nextInt();
            if (n > maximo) {
                maximo = n;
            }
        }
        System.out.println("El máximo es " + maximo);
    }
}
```

**Explicación para tontos**

- Partimos del valor más pequeño posible y lo vamos sustituyendo.

---

### Ejercicio 17 · Máximo, mínimo y media

**Enunciado**

Lee 10 números y calcula máximo, mínimo y media.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio17 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int max = Integer.MIN_VALUE;
        int min = Integer.MAX_VALUE;
        int suma = 0;
        for (int i = 1; i <= 10; i++) {
            System.out.print("Número " + i + ": ");
            int n = teclado.nextInt();
            if (n > max) {
                max = n;
            }
            if (n < min) {
                min = n;
            }
            suma += n;
        }
        double media = (double) suma / 10;
        System.out.println("Máximo: " + max);
        System.out.println("Mínimo: " + min);
        System.out.println("Media: " + media);
    }
}
```

**Explicación para tontos**

- Actualizamos `max` y `min` a medida que leemos.
- Al final dividimos la suma entre 10.

---

### Ejercicio 18 · Tablas del 2 al 9

**Enunciado**

Muestra todas las tablas de multiplicar del 2 al 9.

**Solución en Java**

```java
public class Ejercicio18 {
    public static void main(String[] args) {
        for (int tabla = 2; tabla <= 9; tabla++) {
            System.out.println("Tabla del " + tabla);
            for (int i = 1; i <= 10; i++) {
                System.out.println(tabla + " x " + i + " = " + (tabla * i));
            }
            System.out.println();
        }
    }
}
```

**Explicación para tontos**

- Dos bucles anidados: el externo elige la tabla y el interno recorre del 1 al 10.

---

### Ejercicio 19 · Factorial con distintas estructuras

**Enunciado**

Calcula `n!` usando las variantes pedidas (for ascendente/descendente, while ascendente/descendente). Muestra una de las soluciones completas.

**Solución en Java (for ascendente)**

```java
import java.util.Scanner;

public class Ejercicio19 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Número (>=0): ");
        int n = teclado.nextInt();
        long factorial = 1;
        for (int i = 1; i <= n; i++) {
            factorial *= i;
        }
        System.out.println(n + "! = " + factorial);
    }
}
```

**Variantes rápidas**

```java
// for descendente
for (int i = n; i >= 1; i--) {
    factorial *= i;
}

// while ascendente
int i = 1;
while (i <= n) {
    factorial *= i;
    i++;
}

// while descendente
int j = n;
while (j >= 1) {
    factorial *= j;
    j--;
}
```

**Explicación para tontos**

- Multiplicamos todos los números desde 1 hasta n.
- Si n es 0 el resultado debe ser 1, así que dejamos factorial inicializado a 1.

---

### Ejercicio 20 · Analiza el programa E20

**Enunciado**

En el programa del tema (`E20`), determina la salida si introduces: 2, 0 y letras.

**Solución**

1. **Entrada 2**: se ejecuta el `try` completo, imprime el valor calculado, entra en `finally` y suma 1 dos veces (dentro de `finally` y fuera).
2. **Entrada 0**: se produce `ArithmeticException`, imprime "Error de división por 0" y al intentar dividir dentro del `catch` vuelve a fallar, deteniendo el programa antes de `finally`.
3. **Entrada no numérica**: `InputMismatchException`, muestra el mensaje correspondiente, ejecuta `finally`, incrementa `valor` y termina.

**Explicación para tontos**

- Cada `catch` gestiona un tipo de error distinto.
- Si dentro de un `catch` vuelves a causar el mismo error y no lo capturas, el programa se detiene.

---

### Ejercicio 21 · Evalúa expresiones lógicas

**Enunciado**

Determina el resultado lógico de:
1. `(x >= 0) || (x < 0)`
2. `(x == y) || (x != y)`
3. `(x == y) ^ (x != y)`
4. `(4 > 3) ^ (3 < 4)`

**Solución**

1. Siempre `true`.
2. Siempre `true`.
3. Siempre `true` (exactamente una de las condiciones es cierta).
4. `false` (ambas condiciones son verdaderas y el XOR devuelve `false`).

**Explicación para tontos**

- `||` = al menos una cierta.
- `^` = exactamente una cierta.

---

### Ejercicio 22 · Desglose de billetes y monedas

**Enunciado**

Pide una cantidad de euros y desglósala en el mínimo número de billetes (500, 200, 100, 50, 20, 10, 5) y monedas de 1.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio22 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Cantidad en euros: ");
        int cantidad = teclado.nextInt();
        int[] billetes = {500, 200, 100, 50, 20, 10, 5, 1};

        for (int valor : billetes) {
            int unidades = cantidad / valor;
            cantidad %= valor;
            if (valor >= 5) {
                System.out.println(unidades + " billete(s) de " + valor);
            } else {
                System.out.println(unidades + " moneda(s) de 1 euro");
            }
        }
    }
}
```

**Explicación para tontos**

- Dividimos por cada billete empezando por el más grande.
- Guardamos el resto para los billetes siguientes.

---

### Ejercicio 23 · Negativos, pares e impares

**Enunciado**

Lee 10 números y di si hubo algún negativo, además de contar pares e impares.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio23 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        boolean hayNegativo = false;
        int pares = 0;
        int impares = 0;

        for (int i = 1; i <= 10; i++) {
            System.out.print("Número " + i + ": ");
            int n = teclado.nextInt();
            if (n < 0) {
                hayNegativo = true;
            }
            if (n % 2 == 0) {
                pares++;
            } else {
                impares++;
            }
        }

        System.out.println(hayNegativo ? "Hubo algún negativo" : "No hubo negativos");
        System.out.println("Pares: " + pares);
        System.out.println("Impares: " + impares);
    }
}
```

**Explicación para tontos**

- Marcamos una bandera cuando aparece un negativo.
- `% 2` nos dice si es par (`resto 0`).

---

### Ejercicio 24 · Potencia con bucle

**Enunciado**

Calcula `base^exponente` solo con multiplicaciones repetidas. Maneja exponentes negativos.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio24 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.print("Base: ");
        int base = teclado.nextInt();
        System.out.print("Exponente: ");
        int exp = teclado.nextInt();

        double resultado = 1;
        int veces = Math.abs(exp);
        for (int i = 0; i < veces; i++) {
            resultado *= base;
        }
        if (exp < 0) {
            resultado = 1 / resultado;
        }
        System.out.println("Resultado: " + resultado);
    }
}
```

**Explicación para tontos**

- Multiplicamos `base` por sí misma `|exp|` veces.
- Si el exponente es negativo, damos la vuelta (`1 / resultado`).

---

### Ejercicio 25 · El ordenador adivina tu número

**Enunciado**

El usuario piensa un número entre 1 y 100. El programa lo adivina preguntando si es mayor, menor o igual.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio25 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int minimo = 1;
        int maximo = 100;

        while (true) {
            int intento = (minimo + maximo) / 2;
            System.out.print("¿Es " + intento + "? (m=mayor, n=menor, i=igual): ");
            char respuesta = teclado.nextLine().charAt(0);

            if (respuesta == 'i') {
                System.out.println("¡Adivinado!");
                break;
            } else if (respuesta == 'm') {
                minimo = intento + 1;
            } else if (respuesta == 'n') {
                maximo = intento - 1;
            } else {
                System.out.println("Respuesta no válida");
            }
        }
    }
}
```

**Explicación para tontos**

- Usamos búsqueda binaria: probamos siempre la mitad del intervalo.
- Si el usuario dice "mayor", descartamos la mitad inferior; si dice "menor", la superior.
- Terminamos cuando responde "igual".

---

### Ejercicio 26 · Tú adivinas el número del ordenador

**Enunciado**

El ordenador genera un número aleatorio (1–100) y el usuario intenta adivinarlo. El programa indica si el intento es mayor o menor hasta acertar.

**Solución en Java**

```java
import java.util.Scanner;

public class Ejercicio26 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int secreto = (int) (Math.random() * 100) + 1;
        int intento;

        do {
            System.out.print("Adivina (1-100): ");
            intento = teclado.nextInt();
            if (intento < secreto) {
                System.out.println("Es mayor");
            } else if (intento > secreto) {
                System.out.println("Es menor");
            }
        } while (intento != secreto);

        System.out.println("¡Correcto! Era " + secreto);
    }
}
```

**Explicación para tontos**

- `Math.random()` devuelve un decimal 0–1; lo escalamos a 1–100.
- Repetimos con `do-while` hasta acertar, dando pistas comparando con el número secreto.

---

Con estos 26 ejercicios practicas todas las piezas de la UD5: variables, operadores, entrada/salida, condicionales, bucles, excepciones y lógica básica.