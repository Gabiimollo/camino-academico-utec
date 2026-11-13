# Sistema de diseño — Acadelime

Vigente desde 2026-11-12. Define la identidad visual del LMS: marca, tokens, componentes y el camino de aprendizaje.

## 1. Marca

- **Nombre del producto:** Acadelime. Forma parte del ecosistema de apps del autor, con nombres de frutas.
- **Logo:** una rodaja de lima y la palabra `acadelime` en minúsculas, en Bricolage Grotesque.
- **Personalidad:** gamificada y motivadora, como la app de referencia (camino de lecciones que se desbloquean, XP, racha y contador de progreso), con identidad visual propia.

### Diferencias obligatorias con Duolingo
Las mecánicas de juego (camino, desbloqueo, XP, racha) se pueden usar. Lo que no se copia es el aspecto reconocible de Duolingo. Si el producto se va a comercializar, conviene que un abogado de propiedad intelectual lo revise antes del lanzamiento.

| No usar (Duolingo / app de referencia) | Usar en Acadelime |
|---|---|
| Verde #58CC02 | Lima amarillo-verdoso #B5D334 |
| Mascota (búho) | Rodaja de lima como logo, sin mascota |
| Tipografía redondeada | Bricolage Grotesque + Lexend |
| Nodos circulares | Cuadrados con bordes redondeados |
| Nodos sueltos, solo con ícono | Nodos unidos por un trazo, con etiqueta de texto al lado |
| Botones con relieve inferior que se hunden | Botones planos |
| Globo flotante "EMPEZAR" | Texto "seguí acá" dentro de la etiqueta del nodo |
| Emojis | Íconos de línea |

### Regla: sin emojis
**No se usan emojis en ninguna parte del sistema**: interfaz, camino, certificados, notificaciones, mensajes ni contenido generado por el sistema. Todo ícono sale de una única librería de íconos de línea (en los bocetos se usó Tabler Icons, versión outline).

### Principio: pantallas livianas y sin repetir (vigente desde 2026-11-13)
- El diseño **no debe verse cargado**. Cada pantalla muestra solo lo necesario para la tarea.
- **No se repite información entre secciones.** Cada dato tiene un lugar principal. Por ejemplo, el profesor y la sede van en el camino del curso y en la oferta de cursos, no en las tarjetas del inicio.
- Ante la duda, se quita texto en lugar de agregarlo.

## 2. Personalización por organización

Cada instalación (una organización) personaliza **solo**:
- **Logo** de la organización (y su nombre). Se muestra como distintivo a la derecha de la barra superior, al lado del logo de Acadelime.
- **Certificado:** logo, firmas, sello y textos.

Todo lo demás (colores, tipografías, formas, íconos) es fijo de Acadelime, para que siempre se reconozca el producto.

**Implicancia de esta decisión:** la organización no puede usar sus colores institucionales dentro de la app. Si más adelante se quiere, se puede sumar un color de acento por organización sin rehacer nada: el acento (violeta) ya está separado como token propio (`--color-accent-*`).

### Certificado
- La institución es la protagonista: logo grande arriba y el texto "<Organización> certifica que…".
- Al pie va, en chico: "emitido con **acadelime** · código verificable".
- Debajo del nombre del alumno va su **DNI** (vigente desde 2026-11-13).

## 3. Tokens

Se implementan como variables CSS globales en Angular. Los componentes solo usan tokens, nunca valores sueltos.

### Color — marca y neutros
| Token | Valor | Uso |
|---|---|---|
| `--color-lime-500` | #B5D334 | Color principal: botón principal, nodos completados, encabezado de clase |
| `--color-lime-300` | #D4EE4E | Lima sobre tinta (texto o íconos sobre fondo oscuro), halo del nodo actual |
| `--color-lime-100` | #E8F5B0 | Fondos suaves de avance (chip "Aprobado", XP) |
| `--color-lime-700` | #5C7A0A | Texto lima sobre fondo claro, botón fantasma |
| `--color-ink-900` | #1B2B1E | Tinta: texto principal, barra superior, botón de énfasis |
| `--color-ink-500` | #5D6B4F | Texto secundario |
| `--color-line` | #DCE3C4 | Bordes, separadores, trazo pendiente del camino |
| `--color-locked-bg` | #E6EAD9 | Nodo y clase bloqueados |
| `--color-locked-fg` | #8A9479 | Ícono de nodo bloqueado |
| `--color-paper` | #FBFCF2 | Fondo de página |
| `--color-surface` | #FFFFFF | Tarjetas |

### Color — acento y semánticos
| Token | Valor | Uso |
|---|---|---|
| `--color-accent-500` | #6B4EFF | Violeta: racha, logros, autoevaluación |
| `--color-accent-50` | #EDE9FF | Fondo de autoevaluación y racha |
| `--color-accent-800` | #3B2A99 | Texto sobre `--color-accent-50` |
| `--color-warning` | #B45309 (fondo #FEF3C7, texto #8A4B06) | Pendiente (por ejemplo, inscripción por aprobar) |
| `--color-danger` | #C2362B (fondo #FDE8E6, texto #9B2A20) | Errores, abandono, acciones destructivas |
| `--color-info` | #1F5FAD (fondo #E6F0FB, texto #174A87) | Cursando, información |

### Reglas de color
- El lima **siempre lleva texto oscuro** (`--color-ink-900`), con un contraste de 8.6:1. Nunca va texto blanco sobre lima.
- El lima **nunca se usa como color de texto sobre fondo claro**. Para eso está `--color-lime-700`.
- Significados fijos: **lima** = avance (completado, XP, aprobado); **violeta** = racha, logros y autoevaluación; **azul** = cursando; **ámbar** = pendiente; **rojo** = abandono y errores.
- El texto sobre un fondo de color usa el tono oscuro de la misma familia.

### Tipografía
| Rol | Fuente | Tamaños |
|---|---|---|
| Títulos y marca | Bricolage Grotesque, 700 | 32 · 24 · 20 · 16 px |
| Texto e interfaz | Lexend, 400 y 500 | 16 (lectura) · 14 (interfaz) · 12 (metadatos) px |

Lexend se diseñó para facilitar la lectura, algo que suma en un contexto educativo.

### Espaciado, radios, elevación y movimiento
- **Espaciado:** escala de 4 px (4, 8, 12, 16, 24, 32, 48).
- **Radios:** 6 px para chips · 12 px para botones y campos · 14 px para nodos chicos (40–44 px) · 18 px para nodos del camino (60 px) · 16 px para tarjetas y encabezados de clase.
- **Elevación:** plana. La profundidad se marca con bordes (`--color-line`) y, como mucho, una sombra suave para menús y diálogos. **No hay relieve inferior en botones ni nodos.**
- **Movimiento:** 150 ms para la interfaz y 300 ms para celebraciones (completar una microcápsula, aprobar). Se respeta `prefers-reduced-motion`.

## 4. Componentes base

### Botones
| Variante | Estilo | Uso |
|---|---|---|
| Principal | Fondo lima, texto tinta | La acción principal de la pantalla (una por vista) |
| Énfasis | Fondo tinta, texto lima-300 | Acción destacada sobre fondos claros o lima |
| Secundario | Blanco con borde tinta de 1.5 px | Acciones de apoyo |
| Fantasma | Sin fondo, texto lima-700 | Acciones terciarias |
| Peligro | Fondo rojo, texto blanco | Acciones destructivas (dar de baja, rechazar) |

### Chips de estado
| Estado | Fondo / texto |
|---|---|
| Cursando | #E6F0FB / #174A87 |
| Aprobado | #E8F5B0 / #3A4A10 |
| Abandonado | #FDE8E6 / #9B2A20 |
| Inscripción pendiente | #FEF3C7 / #8A4B06 |
| Rechazada | #EDEFE6 / #3B4A3C |

### Barra superior
Fondo tinta. A la izquierda va el logo de Acadelime, a la derecha el logo de la organización como distintivo. En la vista del alumno muestra los contadores de XP, racha y progreso (completadas / total).

## 5. El camino de aprendizaje

Es la pieza central de la experiencia del alumno. Mantiene la estructura de la app de referencia.

> ⚠️ **En desuso desde 2026-11-12.** Reemplazado por la versión 2 (ver abajo). Motivo: el bloque es la unidad principal del material y una clase puede desarrollar uno o varios bloques, así que el encabezado fijo pasa a ser el del bloque.

### Estructura (de arriba hacia abajo)
1. **Separador de agrupador:** línea, nombre del agrupador de clases, línea. En la app de referencia se llama "Bloque" (por ejemplo, "Bloque 1 · Fundamentos").
2. **Encabezado de clase:** tarjeta lima con radio de 16 px. Muestra "Clase NN · fecha · sede", el título de la clase y un botón al calendario. Queda fijo arriba mientras se recorre el camino de esa clase.
3. **Camino sinuoso:** los nodos se desplazan hacia los costados siguiendo el patrón `0, −55, −85, −55, 0, 55, 85, 55` px.
4. **Siguiente clase:** encabezado gris (bloqueado) con su fecha y sede.

### Estructura — Versión 2 (vigente desde 2026-11-12)
El camino se organiza por **bloques** (ver glosario). De arriba hacia abajo:
1. **Encabezado de bloque:** tarjeta lima con radio de 16 px. Muestra "Bloque N · Clase NN · fecha · sede", el nombre del bloque y un botón al calendario. Si el bloque se da en varias clases, lo indica: "Bloque 2 · Clases 02 y 03 · desde mar 19 nov". Queda fijo arriba mientras se recorre el camino de ese bloque.
2. **Camino sinuoso:** los nodos se desplazan hacia los costados siguiendo el patrón `0, −55, −85, −55, 0, 55, 85, 55` px.
3. **Siguiente bloque:** encabezado gris (bloqueado) con su referencia de clase o clases.

Ya no hay separador de agrupador aparte: el encabezado de bloque cumple esa función.

### Nodos
- **Forma:** cuadrado de 60 px con radio de 18 px, ícono de línea de 24 px.
- **Trazo:** una línea une los centros de los nodos. Es lima sólida de 8 px en el tramo recorrido y punteada gris (`--color-line`) en el pendiente.
- **Etiqueta:** al lado de cada nodo, del lado opuesto al desplazamiento. Lleva el tipo y número en chico ("Tema 3") y el título debajo ("Unidades de medida").

| Estado | Estilo |
|---|---|
| Completado | Fondo lima-500, ícono de tilde |
| Actual | Fondo tinta, ícono lima-300 (reproducir). Detrás lleva un **halo sólido** lima-300 de 80 px con radio de 24 px. La etiqueta dice "Tema N · seguí acá". Hay uno solo en todo el camino: la primera lección pendiente |
| Bloqueado | Fondo #E6EAD9, ícono de candado #8A9479, etiqueta en gris |
| Autoevaluación | Fondo violeta-50, ícono de trofeo violeta-500, etiqueta violeta |

**Tipos de nodo vistos en la app de referencia:** tema (microcápsula), resumen, práctica y autoevaluación (en la app de referencia, "Quiz"). Cada tipo tiene su ícono de línea.

**Tipos de nodo — confirmado 2026-11-12.** Resumen y práctica son tipos de material del LMS (ver glosario). Orden dentro de un bloque: temas, resumen, práctica, autoevaluación. Íconos de línea: tema = reproducir (actual) o tilde (completado); resumen = apuntes (no caja ni cofre, porque es material para estudiar, no un premio); práctica = herramienta; autoevaluación = trofeo.

## 6. Pendientes por definir

> ⚠️ **En desuso desde 2026-11-12.** Reemplazado por la versión 2 (ver abajo). Motivo: el usuario resolvió el modo oscuro, el bloque y los nodos de resumen y práctica.


Estos puntos no están confirmados. No se implementan hasta resolverlos con el usuario:
- **Modo oscuro:** si existe y con qué valores.
- **Agrupador de clases ("Bloque"):** no figura en el glosario. Falta definir si es un concepto del dominio.
- **Relación camino, clase y trayecto:** el boceto muestra un camino por clase, y el glosario define el trayecto como una secuencia de microcápsulas que termina en autoevaluación. Falta confirmar si cada clase tiene su trayecto.
- **Nodos de resumen y práctica:** vienen de la app de referencia. Falta confirmar si son tipos de material del LMS.

### Pendientes — Versión 2 (vigente desde 2026-11-12)
Resueltos:
- **Modo oscuro:** existe. Ver sección 7.
- **Bloque:** es la unidad didáctica y está en el glosario. El camino se organiza por bloques (sección 5, estructura versión 2).
- **Resumen y práctica:** son tipos de material (glosario y sección 5).

Sigue pendiente:
- **Bloque y trayecto:** el glosario define el trayecto como una secuencia de microcápsulas que termina en autoevaluación, y eso se parece al bloque. Falta definir si son lo mismo o cómo se relacionan.

**Resuelto el 2026-11-12:** el bloque es lo que antes se llamaba trayecto. El trayecto ahora es un conjunto de cursos (ver glosario). No quedan pendientes en este documento.

## 7. Modo oscuro

Vigente desde 2026-11-12. Usa los mismos colores, ajustados para mantener el contraste. Sigue la preferencia del sistema operativo (`prefers-color-scheme`) y se puede cambiar a mano. Las mismas variables CSS cambian de valor; los componentes no cambian.

### Superficies y texto
| Token | Claro | Oscuro |
|---|---|---|
| `--color-paper` (fondo) | #FBFCF2 | #111A13 |
| `--color-surface` (tarjeta) | #FFFFFF | #1A251C, con borde |
| Barra superior | #1B2B1E | #0A110B, con línea inferior `--color-line` |
| Texto principal | #1B2B1E | #EEF3E2 |
| `--color-ink-500` (texto secundario) | #5D6B4F | #A9B59A |
| `--color-line` | #DCE3C4 | #34443A (trazo pendiente del camino: #3F5144) |
| `--color-locked-bg` | #E6EAD9 | #26322A |
| `--color-locked-fg` | #8A9479 | #7E8A72 (etiqueta bloqueada: #8E9A82) |

### Marca y acento
- **Lima-500 (#B5D334) no cambia** y sigue llevando texto tinta #1B2B1E. Lo mismo vale para el encabezado de bloque y los nodos completados.
- **Lima como texto o ícono:** sobre fondo oscuro se usa lima-300 (#D4EE4E), en lugar de lima-700.
- **Nodo actual:** se mantiene tinta #1B2B1E con ícono lima-300. El halo sólido lima-300 es el que lo separa del fondo.
- **Violeta:** como texto o ícono, #A898FF. El fondo de autoevaluación pasa a #2A2350 y su texto a #C9BFFF.

### Botones
| Variante | Oscuro |
|---|---|
| Principal | Fondo lima-500, texto tinta (igual que en claro) |
| Énfasis | Fondo lima-300, texto tinta |
| Secundario | Transparente, borde y texto #EEF3E2 |
| Fantasma | Sin fondo, texto lima-300 |
| Peligro | Fondo #E5544A, texto #1B0B09 |

### Chips de estado
| Estado | Fondo / texto |
|---|---|
| Cursando | #13304F / #9CC7F5 |
| Aprobado | #33410F / #E0F29A |
| Abandonado | #4A1A16 / #F5ABA3 |
| Inscripción pendiente | #4A3208 / #F8CF7A |
| Rechazada | #26322A / #B8C2A8 |
