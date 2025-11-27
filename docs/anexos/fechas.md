# Anexo II · Gestión y formato de fechas

Trabajar con fechas en Java se realiza cómodamente con `java.text.SimpleDateFormat`, que hereda de `DateFormat`. Permite convertir entre `String` y `java.util.Date` usando patrones personalizables.

## Conversión de `String` a `Date`

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class StringToDateExample {
    public static void main(String[] args) {
        try {
            String patron = "dd/MM/yyyy";
            SimpleDateFormat sdf = new SimpleDateFormat(patron);
            String texto = "20/11/2024";
            Date fecha = sdf.parse(texto);
            System.out.println("Fecha: " + fecha);
        } catch (Exception e) {
            System.out.println("Error al parsear la fecha");
        }
    }
}
```

**Pasos clave**

1. Define el patrón (día/mes/año, ISO, etc.).
2. Crea `SimpleDateFormat` con ese patrón.
3. Llama a `parse(String)`. Si el texto no encaja, lanza `ParseException`.

## Conversión de `Date` a `String`

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class DateToStringExample {
    public static void main(String[] args) {
        String patron = "dd/MM/yyyy";
        SimpleDateFormat sdf = new SimpleDateFormat(patron);
        Date hoy = new Date();
        String formateada = sdf.format(hoy);
        System.out.println("Hoy es " + formateada);
    }
}
```

## Patrones habituales

| Patrón | Ejemplo | Descripción |
| --- | --- | --- |
| `dd/MM/yyyy` | `20/11/2024` | Día/Mes/Año formato europeo |
| `yyyy-MM-dd` | `2024-11-20` | ISO 8601 |
| `dd-MMM-yyyy` | `20-nov-2024` | Mes abreviado |
| `EEEE, dd MMMM yyyy` | `jueves, 20 noviembre 2024` | Día/mes en texto completo |
| `HH:mm:ss` | `14:35:50` | Hora 24h |
| `hh:mm:ss a` | `02:35:50 PM` | Hora 12h |
| `yyyy.MM.dd G 'at' HH:mm:ss z` | `2024.11.20 AD at 14:35:50 CET` | Con era y zona |
| `E, MMM dd yyyy` | `Thu, Nov 20 2024` | Formato cabecera correo |

## Manejo de errores

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class ParseGuard {
    public static void main(String[] args) {
        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy");
        try {
            Date fecha = sdf.parse("2024-11-20");
        } catch (ParseException e) {
            System.out.println("Formato incorrecto");
        }
    }
}
```

!!! warning "Trucos rápidos"
    - `parse` exige que el texto coincida exactamente con el patrón.
    - `SimpleDateFormat` no es seguro para hilos: crea una instancia por hilo si trabajas en paralelo.
    - Para APIs modernas (`java.time`), usarías `DateTimeFormatter`, pero aquí nos centramos en la clase vista en la UD5.

Con estas plantillas puedes convertir fechas y mostrarlas bonitas en tus programas Java.