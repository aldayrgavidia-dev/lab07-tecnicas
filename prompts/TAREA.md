
# Tarea: Mi prompt avanzado

## Tarea elegida

Generar casos de prueba para un sistema de inicio de sesión web que utiliza correo electrónico y contraseña. La cuenta debe bloquearse después de tres intentos fallidos. El objetivo es obtener casos de prueba claros, ordenados y que permitan comprobar el funcionamiento correcto del login.

## Version 1: prompt basico

**Prompt utilizado:**

```text
Dame casos de prueba para un login web.
```

**Técnica agregada:** Zero-shot.

**Por qué:** Se utilizó una instrucción sencilla y directa, sin proporcionar ejemplos ni información adicional.

**Qué mejoró en la respuesta:** La IA pudo generar casos generales de inicio de sesión, pero no tenía información específica sobre las reglas del sistema ni un formato obligatorio.

## Version 2

**Prompt utilizado:**

```text
Actúa como analista de pruebas de software.
Necesito casos de prueba para un login web que utiliza correo electrónico y contraseña.
La cuenta se bloquea después de 3 intentos fallidos.
Presenta 6 casos de prueba en una tabla con las columnas:
ID, escenario, datos de entrada y resultado esperado.
```

**Técnica agregada:** Role prompting y prompt estructurado.

**Por qué:** Se definió un rol específico y se organizó la solicitud indicando el contexto, las condiciones del login y el formato de respuesta.

**Qué mejoró en la respuesta:** La IA generó casos más específicos, incluyó el bloqueo después de tres intentos y presentó la información en una tabla organizada.

## Version 3: prompt final

**Prompt utilizado:**

```text
<rol>
Actúa como analista de pruebas de software especializado en pruebas funcionales.
</rol>

<contexto>
Sistema de inicio de sesión web que utiliza correo electrónico y contraseña.
La cuenta se bloquea después de 3 intentos fallidos consecutivos.
</contexto>

<tarea>
Piensa paso a paso qué situaciones pueden fallar.
Genera 6 casos de prueba iniciales que incluyan acceso correcto,
contraseña incorrecta, bloqueo de cuenta y campos vacíos.
Después revisa los casos y agrega situaciones límite como
correo sin el símbolo @ y contraseñas con espacios.
Indica qué casos agregaste durante la revisión.
</tarea>

<formato>
Presenta el resultado en una tabla con las columnas:
ID, escenario, datos de entrada y resultado esperado.
</formato>

<revision>
Comprueba que los casos sean diferentes, que incluyan el bloqueo
después de 3 intentos y que no existan escenarios repetidos.
</revision>
```

**Técnicas agregadas:** Role prompting, prompt estructurado, descomposición y autocrítica.

**Por qué:** Se combinaron estas técnicas para definir el rol, organizar la información, dividir la tarea en una generación inicial y una revisión posterior.

**Qué mejoró en la respuesta:** Se obtuvo una solicitud más completa, con casos funcionales, validaciones de campos y situaciones límite. También se pidió revisar los posibles errores y evitar casos repetidos.

## Tecnicas usadas en el prompt final

| Técnica | Parte del prompt | Función |
|---|---|---|
| Role prompting | `<rol>` | Define el papel de analista de pruebas. |
| Prompt estructurado | `<contexto>`, `<tarea>` y `<formato>` | Organiza las instrucciones. |
| Descomposición | Generar casos iniciales y después revisarlos. | Divide la tarea en etapas. |
| Autocrítica | `<revision>` | Solicita revisar y mejorar los resultados. |

## Evaluacion del resultado

| Criterio | Cumple (Sí / No) |
|---|---|
| ¿El prompt define un rol específico? | Sí |
| ¿Incluye el contexto y las reglas del login? | Sí |
| ¿Solicita una tabla con las cuatro columnas? | Sí |
| ¿Incluye el bloqueo después de tres intentos fallidos? | Sí |
| ¿Solicita casos límite y una revisión final? | Sí |

## Por que elegi estas tecnicas

Elegí estas técnicas porque necesitaba generar casos de prueba claros y completos para un sistema de inicio de sesión. El role prompting permite establecer el papel de un analista de pruebas, el prompt estructurado organiza las instrucciones y la descomposición permite separar la generación de casos de su revisión. Finalmente, la autocrítica ayuda a detectar posibles errores y casos que podrían faltar. Estas técnicas permiten obtener una respuesta más organizada y útil que un prompt básico.
