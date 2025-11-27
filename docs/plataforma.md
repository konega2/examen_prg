# 1 · Plataforma Java

## 1.1 Introducción express

Java es un **lenguaje de propósito general**: sirve para apps de escritorio, servicios web, móviles, IoT, tarjetas bancarias y más.

Ventajas clave:

- ✅ **Multiplataforma real** gracias a la JVM: compilas una vez (`.class`) y lo ejecutas en Windows, Linux, macOS, etc.
- ✅ **Gratuito y bien documentado**. Oracle y la comunidad mantienen versiones de largo soporte.
- ✅ **Orientado a objetos** desde la base: fomenta código modular y reutilizable.
- ✅ **Seguro y robusto**: gestiona memoria, tiene excepciones y librerías probadas.
- ✅ **Concurrencia integrada**: puedes lanzar hilos sin librerías externas.

!!! info "¿Qué se puede programar con Java?"
    - Aplicaciones independientes (CLI, GUI, servicios backend).
    - Applets (legacy) incrustados en HTML.
    - Aplicaciones Android (con variantes del lenguaje).
    - Juegos, herramientas científicas y casi cualquier otra cosa.

## 1.2 Arquitectura: del `.java` al `.class`

```text
Código fuente (.java) ──► Compilador `javac` ──► Bytecode (.class) ──► JVM específica de cada plataforma
```

- **Bytecode**: instrucciones intermedias casi a nivel máquina.
- **JVM/JRE**: intérprete + entorno de ejecución que traduce bytecode a instrucciones nativas cuando se lanza el programa.
- **Resultado**: mismo `.class` se ejecuta en distintos sistemas sin recompilar.

!!! tip "La JVM también es la JRE"
    El término JRE (Java Runtime Environment) suele usarse como sinónimo de JVM porque incluye la máquina virtual más las librerías estándar necesarias para ejecutar programas.

## 1.3 Características destacadas

| Característica | Por qué importa |
| --- | --- |
| Independencia de hardware/SO | Distribuyes un único `.jar` y la JVM se encarga del resto |
| Seguridad | Verificador de bytecode, gestión de memoria, sandbox para código remoto |
| Librería estándar inmensa | Entrada/salida, colecciones, red, criptografía, UI, etc. |
| Portabilidad del compilador | `javac` es el mismo en todas las plataformas |
| Comunidad y ecosistema | IDEs, frameworks (Spring, Jakarta EE), herramientas de build |

## 1.4 ¿Qué necesitas instalado?

1. **JVM**: para ejecutar programas (`java`).
2. **JDK**: Kit de Desarrollo (incluye `javac`, `javadoc`, `jdb`, etc.).
3. **IDE**: IntelliJ, NetBeans, Eclipse… En esta chuleta usamos **IntelliJ IDEA Community Edition**.

!!! question "¿Por qué no solo un editor cualquiera?"
    Puedes escribir Java en un bloc de notas, pero un IDE compila, ejecuta, depura, autocompleta, colorea errores y te ahorra mucho tiempo.

## 1.5 Checklist de instalación

| Paso | Acción | Comentario |
| --- | --- | --- |
| 1 | Descarga el **JDK** (OpenJDK u Oracle) | Apunta la versión (17 LTS es buena elección) |
| 2 | Instala el **IDE IntelliJ** | Recomendado: vía [JetBrains Toolbox](herramientas.md#instalacion-con-toolbox) |
| 3 | Configura el **SDK del proyecto** | IntelliJ descarga el JDK si no lo encuentra |
| 4 | Crea un proyecto vacío | Build System: IntelliJ, sin código de ejemplo |
| 5 | Crea tu clase `HolaMundo` dentro de `src` | Recuerda que el nombre del archivo debe coincidir con la clase pública |

Con esto ya estás listo para pasar a las herramientas y la estructura de un programa Java.