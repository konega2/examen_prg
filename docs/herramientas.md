# 2 · Herramientas básicas

## 2.1 JVM (Java Virtual Machine)

Java se **compila** a bytecode y después se **interpreta** dentro de la JVM.

- Compilas con `javac Archivo.java` → obtienes `Archivo.class`.
- Ejecutas con `java Archivo` → la JVM traduce el bytecode a instrucciones del microprocesador.
- El bytecode es el mismo sin importar si tu PC usa Windows, macOS o Linux.

!!! note "¿Es lenta la JVM?"
    No: la JVM usa técnicas de compilación *Just-In-Time* (JIT). Suele ser más rápida que lenguajes puramente interpretados como el antiguo Visual Basic, aunque algo más lenta que C++ nativo.

## 2.2 JDK (Java Development Kit)

El JDK incluye todas las herramientas para programar:

| Carpeta | Contenido clave |
| --- | --- |
| `bin` | Ejecutables (`javac`, `java`, `javadoc`, `jdb`, `appletviewer`, etc.) |
| `lib` | Librerías estándar comprimidas (`modules`, `.jar`) |
| `include` | Cabeceras para integrar C/C++ |

Otros recursos:

- `javac`: compila.
- `java`: ejecuta.
- `javadoc`: genera documentación HTML de tus clases.
- `jdb`: depurador.
- `jar`: empaqueta bytecode.

## 2.3 IDE IntelliJ IDEA

### ¿Qué es?

Entorno de JetBrains con dos ediciones:

- **Community Edition** (gratis): ideal para Java SE, Kotlin, Scala y Android básico.
- **Ultimate Edition** (pago): añade herramientas web, empresariales y de bases de datos.

Descarga desde: <https://www.jetbrains.com/idea/download/other.html>

### Instalación con JetBrains Toolbox

1. Descarga JetBrains Toolbox desde la web oficial.
2. Instálalo y ejecuta la app.
3. Elige *IntelliJ IDEA Community* y pulsa **Install**.
4. Desde Toolbox puedes actualizar, desinstalar o tener varias versiones del IDE.

## 2.4 Creación de un proyecto

1. Abre IntelliJ y elige **New Project**.
2. Selecciona **Java** en la columna izquierda.
3. Build System → **IntelliJ** (por defecto).
4. SDK → deja el que propone (p. ej. `openjdk-22`).
5. Desmarca *Add sample code* para empezar limpio.
6. Pulsa **Create**. IntelliJ descargará el JDK si hace falta.
7. Crea tus clases dentro de `src` (clic derecho → *New > Java Class*).

### Estructura mínima de un programa

```java
public class Hola {
    /**
     * Mi primer programa Java
     */
    public static void main(String[] args) {
        System.out.println("Hola, mundo!");
    }
}
```

!!! warning "Nombres y mayúsculas"
    Si el archivo se llama `Hola.java`, la clase pública debe llamarse `Hola`. Java distingue mayúsculas y minúsculas.

## 2.5 Compilar y ejecutar

- Desde terminal: `javac Hola.java` → `java Hola`.
- En IntelliJ: pulsa el botón **Run** (icono ▶️). El IDE compila y ejecuta automáticamente.

## 2.6 Atajos útiles en IntelliJ

| Atajo | Expansión | Uso |
| --- | --- | --- |
| `sout` + `Tab` | `System.out.println("");` | Plantilla de salida |
| `soutv` + `Tab` | `System.out.println(var);` | Imprime la última variable |
| `fori` + `Tab` | Estructura `for` clásica | Contadores |
| `main` + `Tab` | `public static void main(String[] args)` | Punto de entrada |
| `Ctrl + B` | Ir a definición | Navegación rápida |

!!! tip "Mantén limpio tu proyecto"
    - Un archivo `.java` → una clase pública con el mismo nombre.
    - Agrupa el código en funciones dentro de la clase.
    - Usa paquetes (`package`) cuando empieces a tener muchas clases.

Con estas herramientas ya tienes el entorno listo para seguir con tipos de datos, operadores y el resto del temario.