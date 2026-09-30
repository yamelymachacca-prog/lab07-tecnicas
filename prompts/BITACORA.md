# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: (escribe aqui cual usaste)

## Ejercicio 2: Zero-shot, one-shot y few-shot
| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|--------------------------|------------------------------------|
| Zero-shot | 5 | En una tabla | No |
| One-shot | 5 | En una lista | No |
| Few-shot | 5 | Igual que los ejemplos | Si |
## Ejercicio 3: Chain of Thought
| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo | 106.2 | No | No |
| Paso a paso | 318.60 | Si | Si |

Ver los pasos me ayudó a darme cuenta de que en la primera respuesta solo se calculó una unidad.
Al hacerlo paso a paso pude comprobar que el total correcto de las 3 unidades era S/ 318.60.
## Ejercicio 4: Role prompting
| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|---------------------------------|-----------------------|----------------------|
| A. Sin rol | Sencillo | Ejemplos y codigo | Publico en general |
| B. Rol docente | Sencillo | Ejemplos faciles | Estudiantes que recien empiezan |
| C. Rol senior | Tecnico | Ejemplos y codigo Java | Programadores con experiencia |
## Ejercicio 5: Descomposicion
- Paso 1: La IA identificó como requisitos la gestión de productos, control de stock, alertas de stock mínimo, registro de ventas y almacenamiento de los datos.

- Paso 2: Diseñó las clases Producto, MovimientoInventario, DetalleVenta y Venta, indicando los atributos y tipos de datos de cada una.

- Paso 3: Generó la clase Producto en Java con datos como código de barras, nombre, categoría, precios y stock, además del constructor, getters y setters.

- Paso 4: Al revisar el código propuso agregar validaciones para evitar valores incorrectos, mejorar el manejo del stock y comparar correctamente los productos.

Al pedir el sistema de una sola vez, la IA me dio una propuesta muy amplia que incluía base de datos, backend e interfaz. En cambio, al dividirlo en pasos fui obteniendo primero los requisitos, después las clases y finalmente el código, por lo que fue más fácil seguir y revisar cada parte.
## Ejercicio 6: Prompt estructurado y autocritica
| Qué revisar | Cumple (Sí / No) |
|-------------|------------------|
| ¿Tiene las 4 columnas pedidas? | Sí |
| ¿Incluye el bloqueo después de 3 intentos? | Sí |
| ¿Incluye casos con campos vacíos? | Sí |
| ¿Indica qué casos agregó en la autocrítica? | Sí |
| ¿Hay algún caso repetido o que no tenga sentido? | No |

### Prompt estructurado

```text
<rol>Actua como analista de pruebas de software.</rol>

<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>

<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>

<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>
```

### Mensaje de autocritica

```text
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```s


