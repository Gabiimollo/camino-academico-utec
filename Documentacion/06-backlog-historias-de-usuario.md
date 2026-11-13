# Backlog — Historias de usuario

Orden sugerido de implementación. `Requires: #N` indica que la historia no tiene sentido sin otra.
Cada historia se implementa completa (datos, backend e interfaz). La #1 es la mínima que funciona de punta a punta.

1. Como alumno, quiero registrarme e iniciar sesión, para acceder al material de estudio.
2. Como profesor o administrador, quiero registrarme e iniciar sesión, para usar las funciones que corresponden a mi rol. Requires: #1
3. Como administrador, quiero dar de alta, editar y dar de baja usuarios y asignarles roles, para controlar quién accede y qué puede hacer. Requires: #2
4. Como administrador, quiero asociar a los alumnos a sedes, para que cada uno acceda a la oferta de su sede. Requires: #3
5. ⚠️ **En desuso desde 2026-11-12.** Reemplazada por la versión 2 (abajo). Motivo: lo que se llamaba trayecto ahora es bloque. Texto anterior: Como profesor, quiero crear cursos y organizar su material en trayectos de microcápsulas, para armar el contenido de cada clase. Requires: #2
   - **Versión 2 (vigente desde 2026-11-12):** Como profesor, quiero crear cursos y organizar su material en bloques de microcápsulas, para armar el contenido de cada clase. Requires: #2
6. Como administrador, quiero cargar las fechas y la sede en que se dicta cada curso, para que la inscripción se abra sola 15 días antes del inicio. Requires: #4, #5
7. Como alumno, quiero ver solo los cursos de mi sede con inscripción abierta y pedir la inscripción para que un administrador o profesor la apruebe o rechace, para entrar únicamente donde me autorizaron. Requires: #6
8. Como administrador, quiero definir las correlativas de un curso, para que solo puedan inscribirse los alumnos que aprobaron los cursos previos. Requires: #7
9. Como alumno, quiero acreditar una competencia rindiendo un examen multiple choice, subiendo evidencias o entregando un proyecto para que un profesor lo corrija, para inscribirme a un curso sin haber hecho la correlativa. Requires: #8
10. Como alumno, quiero ver un calendario con las clases y los temas de mis cursos, para saber qué se va a dar y cuándo. Requires: #7
11. Como profesor, quiero generar un QR en cada clase para que los alumnos lo escaneen, para que quede registrada su asistencia. Requires: #10
12. ⚠️ **En desuso desde 2026-11-12.** Reemplazada por la versión 2 (abajo). Motivo: lo que se llamaba trayecto ahora es bloque. Texto anterior: Como alumno, quiero responder un multiple choice de autoevaluación al terminar un trayecto de microcápsulas, para saber cuánto comprendí (y que el profesor también lo sepa). Requires: #5
    - **Versión 2 (vigente desde 2026-11-12):** Como alumno, quiero responder un multiple choice de autoevaluación al terminar un bloque, para saber cuánto comprendí (y que el profesor también lo sepa). Requires: #5
13. Como profesor, quiero cargar notas y marcar el estado de cada alumno en el curso (cursando, aprobado, abandonado), para que quien termina conserve siempre el acceso al material y quien abandona lo pierda. Requires: #7
14. Como alumno, quiero obtener un certificado al aprobar un curso, para acreditar lo que hice. Requires: #13
15. Como administrador o profesor, quiero ver la trayectoria completa de un alumno (cursos, estados, notas, asistencias, autoevaluaciones, acreditaciones y certificados) con el historial de quién cambió qué y cuándo, para tener trazabilidad. Requires: #13
