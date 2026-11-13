# Stack tecnológico

| Capa | Tecnología |
|---|---|
| Frontend | Angular |
| Backend | Node.js |
| Base de datos | MongoDB |

## Cuidados que implica este stack
- **Angular usa TypeScript**, no JavaScript plano.
- **Integridad de los datos:** los datos del dominio están muy relacionados (alumno → inscripción → curso → correlativas → notas → asistencia → certificado). MongoDB no impone esas relaciones por sí mismo. El backend debe validar que todas las referencias sean coherentes, porque la integridad y la trazabilidad son el objetivo principal del proyecto.
- **Piezas a resolver en el backend:** login, permisos por rol y almacenamiento de archivos (material, evidencias y proyectos que suben los alumnos).
