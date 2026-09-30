# Tarea: Mi prompt avanzado

## Tarea elegida
Crear casos de prueba para el registro de clientes de una tienda.
## Version 1: prompt basico
```text
Crea casos de prueba para el registro de clientes de una tienda.
```
### Resultado de la version 1

La IA genero varios casos de prueba, pero la respuesta fue muy extensa y agrego datos que no habia especificado, como contraseña, terminos y condiciones y confirmacion por correo.

**Tecnica usada:** Ninguna, fue un prompt basico.

**Que falta mejorar:** Indicar mejor los datos que tiene el registro y limitar la cantidad de casos de prueba.
## Version 2
```text
Actua como analista de pruebas de software.

Debes probar el registro de clientes de una tienda. El registro tiene los campos: ID, nombre, apellido, correo y telefono. El correo debe contener @.

Crea 6 casos de prueba para comprobar que el registro funciona correctamente.
```
**Tecnica agregada:** Role prompting.

**Por que la agregue:** Para que la IA responda como un analista de pruebas y se enfoque en revisar el registro de clientes.

**Que espero mejorar:** Que los casos de prueba se enfoquen en los campos que realmente tiene el registro y no agregue datos que no pedi.
### Resultado de la version 2

La respuesta mejoro porque genero solamente 6 casos de prueba y se enfoco en los campos que indique. Tambien considero la validacion del correo con @. Sin embargo, todavia agrego algunas reglas que no habia especificado, como el ID duplicado y la validacion del telefono.
## Version 3: prompt final
```text
<rol>
Actua como analista de pruebas de software.
</rol>

<contexto>
Se debe probar el registro de clientes de una tienda.
Los campos son: ID, nombre, apellido, correo y telefono.
La unica regla definida es que el correo debe contener @.
No agregues reglas que no hayan sido indicadas.
</contexto>

<tarea>
Realiza lo siguiente:
1. Identifica que aspectos del registro se deben probar.
2. Crea 6 casos de prueba.
3. Revisa los casos generados y comprueba que no hayas agregado reglas que no fueron indicadas.
</tarea>

<formato>
Presenta el resultado en una tabla con las columnas:
ID, escenario, datos de entrada y resultado esperado.
</formato>
```
### Resultado de la version 3

La respuesta fue mas precisa porque respeto las reglas que indique, genero los 6 casos de prueba y no agrego validaciones que no habia pedido. Ademas, al final reviso si habia cumplido con las condiciones del prompt.

**Que mejoro:** La respuesta estuvo mas ordenada y se enfoco solamente en los requisitos indicados.

## Tecnicas usadas en el prompt final
| Parte del prompt | Tecnica utilizada | Para que se utilizo |
|---|---|---|
| "Actua como analista de pruebas de software" | Role prompting | Para indicar el rol que debe asumir la IA. |
| Contexto con los campos y la regla del correo | Prompt estructurado | Para darle informacion clara sobre el registro de clientes. |
| Los 3 pasos indicados en la tarea | Descomposicion | Para dividir el trabajo y hacerlo mas ordenado. |
| "Revisa los casos generados..." | Autocritica | Para que revise su propia respuesta antes de terminar. |
## Evaluacion del resultado
| Criterio | Si/No |
|---|---|
| ¿Genero exactamente 6 casos de prueba? | Si |
| ¿Uso los campos indicados para el registro? | Si |
| ¿Considero que el correo debe contener @? | Si |
| ¿Evito agregar reglas que no fueron indicadas? | Si |
| ¿Reviso al final si cumplio con lo solicitado? | Si |
## Por que elegi estas tecnicas
Elegí estas tecnicas porque me ayudaron a mejorar el prompt poco a poco. El role prompting sirvio para indicar desde que rol debia responder la IA, la descomposicion para dividir la tarea en pasos y el prompt estructurado para ordenar mejor las indicaciones. Tambien use la autocritica para que la IA revise su respuesta. No utilice few-shot porque en este caso no necesitaba darle ejemplos de casos de prueba para obtener el resultado que buscaba.