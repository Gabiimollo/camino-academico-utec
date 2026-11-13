# Documentación del proyecto LMS — Índice

Leé este archivo primero. Explica qué hay en cada documento de esta carpeta.

| Archivo | Qué contiene | Cuándo leerlo |
|---|---|---|
| `01-vision-y-contexto.md` | Qué es el sistema, para quién es y qué problema resuelve | Siempre, antes de empezar |
| `02-stack-tecnologico.md` | Tecnologías elegidas y los cuidados que implican | Antes de escribir código |
| `03-decisiones-clave-roles-y-sedes.md` | Decisiones caras de cambiar: roles, sedes, una organización por instalación | Antes de diseñar datos, permisos o deploy |
| `04-reglas-de-negocio.md` | Reglas acordadas: inscripción, correlativas, acreditación, acceso al material, asistencia, trazabilidad | Al implementar cualquier historia |
| `05-glosario.md` | Significado de los términos del dominio (microcápsula, bloque, trayecto, sede, etc.) | Cuando un término no esté claro |
| `06-backlog-historias-de-usuario.md` | Historias de usuario en orden y sus dependencias | Para saber qué construir y en qué orden |
| `07-sistema-de-diseno.md` | Identidad visual de Acadelime: marca, diferencias con Duolingo, qué personaliza cada organización, tokens (color, tipografía, espaciado), componentes, el camino de aprendizaje por bloques y el modo oscuro | Antes de diseñar o construir cualquier interfaz |
| `08-pantallas-y-flujos-alumno.md` | Navegación y pantallas del alumno por flujo (ingreso, aprendizaje, inscripción, acreditación, asistencia, perfil, tienda). Enlaza al prototipo en `Prototipos/` | Antes de construir cualquier pantalla del alumno |

## Cómo trabajar con esta documentación

- Las historias del backlog se implementan completas: datos, backend e interfaz juntos.
- No agregues requisitos que no estén en estos documentos. Si falta algo, preguntá.
- Si una decisión cambia, actualizá el documento que corresponde.
- Los prototipos navegables están en la carpeta `Prototipos/`, en la raíz del proyecto.
