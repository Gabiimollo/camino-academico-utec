# Pantallas y flujos del alumno

Vigente desde 2026-11-13. Define cómo se ve y cómo se recorre Acadelime desde la vista del alumno. El aspecto visual (colores, tipografías, componentes, camino) está en `07-sistema-de-diseno.md`, y las reglas que aplican las pantallas están en `04-reglas-de-negocio.md`.

> ⚠️ **En desuso desde 2026-11-13.** Reemplazado por la versión 2 (abajo). Motivo: se unificó todo en un solo prototipo, sin lista de validaciones ni panel de pantallas.
>
> **Prototipo navegable:** `Prototipos/01-prototipo-alumno.html`. Se abre en cualquier navegador. Agregando `#` y el nombre de la pantalla al final de la dirección (por ejemplo `#inicio`, `#tienda`, `#certificado`), abre directo en esa pantalla. Los nombres, horarios y cursos que muestra son **datos de ejemplo**.
>
> **Versión para presentar:** `Prototipos/02-presentacion-acadelime.html`. Es el mismo prototipo, con un resumen de las decisiones para validar.
> No se edita a mano: se genera desde el `01` con `python Prototipos/herramientas/generar-presentacion.py Prototipos Prototipos/herramientas/iconos`. Si se usa un ícono nuevo en el `01`, hay que sumar su archivo `.svg` (de Tabler Icons, versión outline) a `Prototipos/herramientas/iconos/`.

**Prototipo — Versión 2 (vigente desde 2026-11-13):** hay **un solo prototipo**, `Prototipos/01-prototipo-alumno.html`. Abre directamente en la app, en la pantalla de inicio de sesión, sin panel de pantallas ni lista de validaciones. Se recorre tocando dentro de la app. Los íconos están incluidos en el mismo archivo, así que no depende de recursos externos salvo las tipografías. También está publicado como página privada en claude.ai (hay que compartirla para que otros la vean). Los nombres, horarios y cursos que muestra son **datos de ejemplo**.

## 1. Decisiones generales

- **Celular primero:** se diseña para 360–430 px de ancho y después se adapta a computadora. Motivo: la asistencia se registra escaneando un QR y el camino gamificado está pensado para pantallas angostas.
- **Pantallas livianas y sin repetir información** entre secciones (ver principio en `07-sistema-de-diseno.md`).
- **Sin emojis.** Solo íconos de línea.
- **Modo claro y oscuro.** El alumno elige Claro, Oscuro o Sistema en Perfil.

## 2. Navegación

**Barra superior** (en las pestañas principales): logo de Acadelime · contador de limes (al tocarlo abre la tienda) · racha semanal · campana de notificaciones (con punto si hay avisos sin leer) · logo de la organización.

**Barra inferior con 4 pestañas:**

| Pestaña | Qué contiene |
|---|---|
| Inicio | Tarjetas de mis cursos con su progreso. Al tocar un curso se abre su camino |
| Cursos | "Nuevos Cursos y Oferta" e "Inscripciones" |
| Calendario | Clases y temas de mis cursos. Desde la clase se registra la asistencia con QR |
| Perfil | Limes, racha, tienda, mi trayectoria, certificados, notificaciones, sede, apariencia y cerrar sesión |

El QR **no tiene pestaña propia**: se escanea desde la clase (en Calendario, en el detalle de la clase o en el botón "Clase de hoy" del encabezado de bloque).

## 3. Flujos y pantallas

### 3.1 Ingreso
| Pantalla | Contenido |
|---|---|
| Iniciar sesión | Logo de Acadelime, nombre de la organización, correo, contraseña, "Olvidé mi contraseña", "Crear cuenta" |
| Crear cuenta | Nombre y apellido, **DNI** (obligatorio, único, solo números), correo, contraseña. Aviso: la sede la asigna un administrador |
| Cuenta creada | Confirmación y sede "Sin asignar" hasta que un administrador la asigne |
| Recuperar contraseña | Correo y "Enviar enlace". Valida que el correo tenga formato válido |
| Revisá tu correo | "Si hay una cuenta con ese correo, te enviamos un enlace. Vence en 1 hora." Opción de enviar otro enlace |
| Nueva contraseña | Contraseña nueva y repetida (mínimo 8 caracteres, deben coincidir) |
| Contraseña actualizada | Confirmación y vuelta a iniciar sesión |

### 3.2 Inicio y aprendizaje
| Pantalla | Contenido |
|---|---|
| Inicio | Saludo. Tarjetas agrupadas en "Cursando" y "Terminados". Cada tarjeta: nombre, estado, barra de progreso, próxima clase y bloque actual. El curso activo muestra el siguiente nodo ("Tema 3 · Unidades de medida"). Aprobado: nota, "Ver material" y "Certificado". Abandonado: gris, "Sin acceso al material". **No muestra profesor ni sede** |
| Camino del curso | Volver, profesor y sede, nombre del curso, progreso. Camino por bloques (ver `07-sistema-de-diseno.md`, sección 5). Si hay clase hoy, el encabezado del bloque muestra "Clase de hoy · registrar asistencia" |
| Tema (microcápsula) | Pasos cortos con barra de progreso y "Continuar". Al terminar: pantalla de logro con los limes ganados |
| Resumen | Puntos clave del bloque y "Listo, lo repasé" |
| Práctica | Consigna y lista de pasos para marcar. Se termina recién cuando todos los pasos están marcados |
| Autoevaluación | Multiple choice, una pregunta por vez: elegir, "Comprobar", ver si es correcta y "Siguiente". Pide elegir una respuesta antes de comprobar |
| Resultado de autoevaluación | Correctas sobre total, limes ganados según el puntaje, aviso de que el profesor también ve el resultado, "Repetir autoevaluación" |

Al completar un nodo se ganan limes **una sola vez**. Si se repite, la pantalla de logro lo aclara.

### 3.3 Inscripción
| Pantalla | Contenido |
|---|---|
| Nuevos Cursos y Oferta | Solo cursos de la sede del alumno con inscripción abierta. Cada uno: nombre, profesor, fechas, cierre de inscripción y, si corresponde, "Requiere <correlativa>" |
| Detalle del curso | Descripción, profesor, fechas, sede, cantidad de clases, correlativa y "Pedir inscripción" |
| Pedido enviado | Aviso de que lo revisa un administrador o profesor |
| Inscripciones | Estado de cada pedido: inscripción pendiente, rechazada (con motivo) o acreditación en revisión |

### 3.4 Correlativa y acreditación de competencias
| Pantalla | Contenido |
|---|---|
| Detalle de curso con correlativa faltante | Aviso "Te falta una correlativa" y "Acreditar competencia" |
| Elegir forma de acreditar | Examen multiple choice, subir evidencias o entregar proyecto |
| Examen | Preguntas multiple choice y "Enviar examen". Lo revisa un profesor |
| Evidencias | Subir archivos, lista de archivos cargados y comentario para quien revisa |
| Proyecto | Consigna y subida del proyecto. Lo corrige un profesor |
| En revisión | Aviso de que un profesor la revisa y que el resultado queda en la trayectoria |

### 3.5 Clases y asistencia
| Pantalla | Contenido |
|---|---|
| Calendario | Semana con el día actual marcado, clase de hoy destacada (con "Presente" si ya se registró) y próximas clases con bloque y sede |
| Detalle de clase | Fecha, hora, sede, profesor, temas de la clase, "Registrar asistencia" e "Ir al bloque" |
| Escanear QR | Cámara con marco y "Apuntá la cámara al QR que muestra tu profesor" |
| Presente | Confirmación con clase y hora de registro |

### 3.6 Perfil, tienda y notificaciones
| Pantalla | Contenido |
|---|---|
| Perfil | Nombre y correo, limes (con acceso a la tienda) y racha, explicación breve, Tienda, Mi trayectoria, Certificados, Notificaciones, sede (no editable), apariencia y cerrar sesión |
| Tienda de limes | Saldo, pestañas "Tienda" y "Mis canjes". Cada producto: tipo (Skill para IA o Video), título, descripción, docente que lo cargó y precio. Si el saldo no alcanza: bloqueado con "Te faltan N limes". Si ya se canjeó: "Canjeado · abrir" |
| Confirmar canje | Precio, saldo actual y saldo restante. "Canjear" o "Cancelar". Aclara "acceso para siempre" |
| Canje hecho | "Ya es tuyo", saldo restante, "Abrir ahora" y "Ver mis canjes" |
| Mis canjes | Productos canjeados con "Abrir". Si no hay ninguno, invitación a ver la tienda |
| Mi trayectoria | Por curso: estado, nota, asistencia, autoevaluaciones y acreditaciones. Acceso al certificado de los cursos aprobados |
| Certificados | Lista de certificados obtenidos |
| Certificado | Logo de la organización destacado, "certifica que", nombre, **DNI**, curso, sede y fecha, firmas, "emitido con acadelime" y código verificable. "Descargar PDF" y "Copiar enlace de verificación" |
| Notificaciones | Avisos con acceso directo: clase del día, inscripción abierta, pedido rechazado, certificado obtenido |
