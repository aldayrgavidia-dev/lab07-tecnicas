# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: ChatGPT

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5 | Tabla con comentario, clasificación y sentimiento | Si |
| One-shot | 5 | Tabla con comentario, clasificación y sentimiento | Si |
| Few-shot | 5 | Comentario -> Clasificación | Si |

## Ejercicio 3: Chain of Thought

| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo | 318.60 | No | Si |
| Paso a paso | S/ 318.60 | Si | Si |

## Ejercicio 4: Role prompting

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol | Sencillo | Sí, ejemplos en Python | Personas que conocen conceptos básicos de programación |
| B. Rol docente | Muy sencillo y didáctico | Sí, ejemplos en Python y situaciones cotidianas | Estudiantes que nunca han programado |
| C. Rol senior | Técnico y profesional | Sí, ejemplos de código Java | Desarrolladores Java y compañeros de trabajo |
## Ejercicio 5: Descomposicion

- Paso 1: La IA generó una propuesta general del sistema de inventario con tres clases y sus respectivos códigos.
- Paso 2: La IA identificó las clases Producto, Inventario y Principal, indicando sus atributos y tipos de datos.
- Paso 3: La IA generó el código Java de la clase Producto con cinco atributos, constructor y métodos get y set.
- Paso 4: La IA revisó el código y propuso tres mejoras: validar precio y cantidad, validar el código y agregar toString().

**Comparación:** El pedido de una sola vez generó una respuesta extensa y general. Al dividir la tarea en pasos, obtuve resultados más ordenados y específicos, pudiendo revisar cada parte antes de continuar.


## Ejercicio 6: Prompt estructurado y autocritica

| Qué revisar | Cumple (Sí / No) |
|---|---|
| ¿Tiene las 4 columnas pedidas? | Sí |
| ¿Incluye el bloqueo después de 3 intentos? | Sí |
| ¿Incluye casos con campos vacíos? | Sí |
| ¿Indica qué casos agregó en la autocrítica? | Sí |
| ¿Hay algún caso repetido o que no tenga sentido? | No |

**Prompt estructurado y autocrítica:**

```text
<rol>Actua como analista de pruebas de software.</rol>

<contexto>Login web con correo y contrasena. La cuenta se bloquea
despues de 3 intentos fallidos.</contexto>

<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>

<formato>Tabla con las columnas: ID, escenario, datos de entrada,
resultado esperado.</formato>

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @
o contrasena con espacios? Agrega los que falten e indica cuales agregaste.