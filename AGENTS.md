# LMS — Guía de entrada para agentes de IA

Sistema de gestión de aprendizaje (LMS) para administradores, profesores y alumnos: trayectorias académicas, inscripción con aprobación y correlativas, calendario de clases y material en microcápsulas. Es una sola organización por instalación, con sedes.

Stack: Angular (TypeScript) + Node.js + MongoDB.

## Antes de empezar
Leé `Documentacion/00-LEEME-indice.md`. Ahí está qué contiene cada documento y cuándo leerlo.

## Reglas de trabajo
- No inventes requisitos. Si algo no está en `Documentacion/`, preguntá.
- Cada historia del backlog (`Documentacion/06-backlog-historias-de-usuario.md`) se implementa completa: datos, backend e interfaz.
- MongoDB no garantiza la integridad de las relaciones: validala en el backend. La integridad y la trazabilidad son el objetivo central del proyecto.
- Si cambia una decisión, actualizá el documento de `Documentacion/` que corresponde.

## Cómo trabajar con el usuario
Estas preferencias valen para cualquier agente o chat que trabaje en este proyecto.

- **Git y GitHub los maneja el usuario.** No hagas commits, push, ramas ni pull requests, y no los ofrezcas. Limitate a crear y editar archivos.
- **Idioma:** comunicate y documentá en español.
- **Alcance por fases.** Trabajá solo en la fase o tarea acordada. No avances a la siguiente sin que el usuario lo pida.
- **Nombres intuitivos.** Usá nombres de archivos y carpetas descriptivos, que una persona o un agente entiendan sin abrirlos. Si son documentos que se leen en orden, numeralos (`00-`, `01-`…).
- **La documentación vive en `Documentacion/`.** Ver "Flujo de trabajo y documentación" más abajo.
- **Decisiones técnicas explicadas en simple.** Cuando haya que elegir algo técnico, explicá las opciones en términos simples y dá tu opinión honesta con una recomendación. La decisión final es del usuario: si elige otra opción, respetala y anotá sus implicancias en la documentación.
- **Preguntá antes de suponer.** Si algo no está claro, hacé una pregunta por vez y proponé una respuesta sugerida.

## Flujo de trabajo y documentación
El proyecto se trabaja con chats especializados por rol (por ejemplo: Product Owner, UX/UI Designer, desarrollo). Todos comparten `Documentacion/` como fuente de verdad.

1. **Trabajá y consultá con el usuario** hasta que confirme el resultado.
2. **Una vez confirmado, creá o actualizá el archivo en `Documentacion/`**:
   - Si es un tema nuevo, creá un archivo con el siguiente número libre y un nombre descriptivo (por ejemplo, `07-sistema-de-diseno.md`).
   - Si el tema ya tiene archivo, actualizalo en lugar de crear otro, siguiendo las reglas de "Cambios en la documentación".
3. **Actualizá el índice** (`Documentacion/00-LEEME-indice.md`): agregá o corregí la fila con el archivo, qué contiene y cuándo leerlo.
4. No documentes borradores ni opciones descartadas, solo lo confirmado.

## Cambios en la documentación
- **Prohibido borrar archivos de `Documentacion/`**, y también borrar contenido ya confirmado dentro de ellos.
- Si algo cambia, **no lo reemplaces: marcalo como en desuso** y escribí la versión nueva a continuación. Usá este formato:

  ```markdown
  > ⚠️ **En desuso desde AAAA-MM-DD.** Reemplazado por la versión 2 (ver abajo). Motivo: <por qué cambió>.

  <contenido anterior, sin modificar>

  ### Versión 2 (vigente desde AAAA-MM-DD)
  <contenido nuevo>
  ```

- Si cambia un archivo entero, el anterior queda en su lugar con el aviso de desuso arriba de todo y un enlace al archivo que lo reemplaza. El nuevo archivo toma el siguiente número libre.
- En el índice, marcá los archivos en desuso e indicá cuál es su reemplazo.
- Al leer la documentación, tomá siempre como válida la versión vigente, no la que está en desuso.
