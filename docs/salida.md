# 5 · Salida de datos

## 5.1 `System.out.println` vs `System.out.print`

| Método | ¿Qué hace? | Comentario |
| --- | --- | --- |
| `System.out.println(arg)` | Muestra el argumento y salta de línea | Es como `print()` en Python con `\n` automático |
| `System.out.print(arg)` | Muestra el argumento **sin** salto final | Úsalo cuando quieras seguir en la misma línea |
| `System.out.printf(format, args...)` | Da formato tipo C | Se verá más adelante |

Ejemplo:

```java
System.out.print("Hola ");
System.out.println("mundo"); // salida: Hola mundo\n
```

## 5.2 Sobrecarga de métodos

`println` acepta cualquier tipo porque existe una versión distinta para `String`, `int`, `float`, objetos, etc. Eso se llama **sobrecarga**: mismo nombre, diferentes parámetros.

!!! tip "Sout y amigos"
    En IntelliJ escribe `sout` + `Tab` para insertar `System.out.println("");` automáticamente.

## 5.3 Concatenación con `+`

```java
int edad = 20;
System.out.println("Tengo " + edad + " años");
```

Si alguno de los operandos es un `String`, el `+` concatenará texto.

## 5.4 Plantilla para depurar

```java
System.out.println("DEBUG | valor de x = " + x);
```

Útil para seguir la ejecución cuando aún no manejas el depurador.

Con la salida controlada, toca ver cómo **leer** datos en consola.