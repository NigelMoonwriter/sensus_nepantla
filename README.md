# SENSUS NEPANTLA

> *We didn't break English. English broke on us. Y de esa ruptura hicimos lengua.*

Un diccionario de la frontera lingüística, 27 entradas organizadas en cinco líneas editoriales, dichos de frontera, prosa nepantlera, literatura punk, humor fronterizo y carteles políticos, que documentan el Spanglish no como error sino como sistema completo: una lengua que opera perfectamente en el umbral entre dos mundos que no la diseñaron.

Un solo archivo HTML. Sin servidor. Sin dependencias. Doble clic y funciona.

**[Ver en vivo](https://nigelmoonwriter.github.io/sensus_nepantla/)**

---

## La posición

Hay un momento en la frontera, no la frontera geográfica, aunque también esa, donde dos lenguas se tocan sin fusionarse. No se funden. Se rozan. Y en ese roce nace algo que ninguna gramática oficial ha sabido nombrar sin mutilarlo.

A ese espacio Gloria Anzaldúa le dio un nombre náhuatl: **nepantla**. El lugar del medio. El umbral. El entre.

SENSUS NEPANTLA es un diccionario construido desde ese umbral. No es un diccionario de errores corregidos. No es un glosario de "cómo hablan los de allá". No es folklore lingüístico empaquetado para consumo académico. No es traducción. La traducción presupone que hay dos sistemas completos y uno puede verter en el otro. El Spanglish niega esa premisa desde el primer code-switch.

Paulo Freire escribió que el oprimido no puede liberarse usando las herramientas del opresor. Pero nadie dijo que no pudiera hackearlas. El Spanglish es ese hackeo: toma el inglés del poder, lo tuerce con la sintaxis del cuerpo, y produce algo que el sistema no puede parsear limpiamente. Eso no es corrupción lingüística. Es **resistencia semántica**.

SENSUS NEPANTLA documenta esa resistencia entrada por entrada, mes por mes, cartel por cartel.

---

## Contenido

### Inventario de entradas

El diccionario tiene 27 entradas organizadas en dos grupos:

#### Calendario fronterizo (#1–12)

Entradas mensuales que capturan la vida en el umbral a lo largo de un año:

| # | Mes | Línea editorial |
|---|---|---|
| 1 | Enero | border-sayings |
| 2 | Febrero | prosa-nepantlera |
| 3 | Marzo | border-sayings |
| 4 | Abril | literatura-punk |
| 5 | Mayo | prosa-nepantlera |
| 6 | Junio | humor-fronterizo |
| 7 | Julio | literatura-punk |
| 8 | Agosto | prosa-nepantlera |
| 9 | Septiembre | prosa-nepantlera |
| 10 | Octubre | literatura-punk |
| 11 | Noviembre | prosa-nepantlera |
| 12 | Diciembre | border-sayings |

#### Carteles políticos (#13–27)

15 carteles en Spanglish crítico con densidad teórica. Cada uno incluye una frase principal, una explicación, una tesis teórica y los referentes teóricos que la sostienen.

| # | Tema | Teóricos referenciados |
|---|---|---|
| 13 | El algoritmo como frontera | Foucault |
| 14 | La lengua como territorio | Anzaldúa |
| 15 | Traducción como violencia | — |
| 16 | Subsunción algoritmos | Foucault, Agamben |
| 17 | La pantalla como muro | Debord, Lukács |
| 18 | El code-switch como insurgencia | Freire, Anzaldúa |
| 19 | Datos como extractivismo | — |
| 20 | El español como resistencia | Bonfil Batalla |
| 21 | Inglés como debt | Graeber |
| 22 | La app como patrón | Foucault |
| 23 | El meme como武器 | Debord, Baudrillard |
| 24 | Bilingüismo como código | — |
| 25 | El accent como clase | Bourdieu, Freire |
| 26 | La lime como geopolítica | — |
| 27 | Nepantla como método | Anzaldúa, Deleuze, Agamben |

### Líneas editoriales

| Línea | Etiqueta | Entradas | Descripción |
|---|---|---|---|
| border-sayings | `border-sayings` | 3 | Dichos en tránsito. La sabiduría que se produce en el cruce, no en la academia. |
| prosa-nepantlera | `prosa-nepantlera` | 5 | Escritura del cuerpo, de la herida, de la memoria que sangra en dos idiomas. |
| literatura-punk | `literatura-punk` | 3 | Gramática rota a propósito. El glitch como forma literaria. |
| humor-fronterizo | `humor-fronterizo` | 1 | El albur como epistemología. La ironía como supervivencia. |
| cartel-politico | `cartel-politico` | 15 | Spanglish crítico con densidad teórica. Foucault en las calles. |

---

## Arquitectura técnica

SENSUS NEPANTLA es un archivo HTML autónomo de 655 líneas:

```
sensus-nepantla.html
├── <style>         — CSS embebido
│   ├── Paleta: negro, crema, terracota, neón, caliche
│   └── Textura de rejilla (referencia a formularios migratorios)
├── <body>          — Estructura HTML
│   ├── Hero (DoNotTryToReadThis)
│   ├── Manifesto (6 tarjetas horizontales desplazables)
│   ├── Filtros editoriales (5 líneas + "TODAS")
│   ├── Búsqueda con debounce
│   ├── Entradas renderizadas dinámicamente
│   ├── Sección de análisis conceptual (3 secciones colapsables + síntesis)
│   └── Footer
└── <script>        — JavaScript embebido (IIFE, ~410 líneas)
    ├── ENTRIES[]   — 27 entradas (8–10 campos cada una)
    └── Lógica      — Búsqueda, filtrado editorial, toggle de análisis
```

### Funcionalidades

- **Búsqueda en tiempo real** — Debounce de 150ms. Busca en: phrase, caption, hashtags, thesis, theorists.
- **Filtrado por línea editorial** — 5 botones + "TODAS" que aislan entradas por orientación creativa.
- **Análisis conceptual desplegable** — 3 secciones teóricas + síntesis que se expanden/colapsan.
- **Responsive** — Media query a 600px.

---

## Esquema de datos

### Entrada de calendario (#1–12)

```json
{
  "num": 1,
  "month": "Enero",
  "theme": "El ano nuevo bicultural",
  "phrase": "New year, misma vaina.",
  "caption": "Mientras el mundo hace resoluciones que no va a cumplir, en la frontera ya estamos resolviendo problemas que no deberíamos tener.",
  "hashtags": ["#BorderSyntax", "#Spanglish", "#Nepantla"],
  "color": "#C65D3E",
  "line": "border-sayings"
}
```

### Entrada de cartel político (#13–27)

```json
{
  "num": 13,
  "month": "El algoritmo como nueva frontera",
  "theme": "Foucault no previó que el panóptico tendría API",
  "phrase": "Tu accent no es bug, es feature del sistema que te diseñó para hablar sin ser escuchado.",
  "caption": "Cuando el sistema te pide que hables 'proper English', no está corrigiendo tu gramática: está pidiendo que borres la huella de tu cuerpo en tu lengua. Cada acento es una topografía del cuerpo que lo carga.",
  "hashtags": ["#BorderSyntax", "#AlgoColonialismo", "#FoucaultEnElBorder"],
  "color": "#8B1A1A",
  "line": "cartel-politico",
  "thesis": "El algoritmo de reconocimiento de voz que falla con acentos mestizos no es un error técnico: es la continuación lógica de un sistema diseñado para que ciertos cuerpos sean menos legibles que otros.",
  "theorists": ["Foucault", "Nakamura"]
}
```

### Campos detallados

| Campo | Tipo | Calendario | Cartel | Descripción |
|---|---|---|---|---|
| `num` | int | Si | Si | Número secuencial (1–27) |
| `month` | string | Si | Si | Mes (calendario) o título temático (cartel) |
| `theme` | string | Si | Si | Subtítulo / descripción temática |
| `phrase` | string | Si | Si | Frase principal en Spanglish |
| `caption` | string | Si | Si | Texto explicativo / creativo |
| `hashtags` | string[] | Si | Si | Tags temáticos |
| `color` | string | Si | Si | Código hex del color de la entrada |
| `line` | string | Si | Si | Línea editorial |
| `thesis` | string | — | Si | Tesis teórica (solo carteles) |
| `theorists` | string[] | — | Si | Referentes teóricos (solo carteles) |

---

## Corpus teórico y fuentes

SENSUS NEPANTLA no lleva bibliografía al final. La teoría está dentro del lenguaje mismo, como la gravedad está en el mármol antes de que llegue el cincel. Pero los interlocutores son visibles:

**Gloria Anzaldúa** — *Borderlands / La Frontera* (1987). La frontera no como línea sino como herida abierta que nunca cicatriza del todo. La *mestiza consciousness* que puede sostener contradicciones sin resolverlas.

**Paulo Freire** — *Pedagogía del oprimido* (1968). El lenguaje del oprimido no es deficiente: es la única epistemología que nace desde abajo. La *concientización* como acto lingüístico antes que político.

**Guillermo Bonfil Batalla** — *México profundo* (1987). Hay un México que no aparece en los datos oficiales, que habla lenguas que el Estado no registra. Ese México aparece en el Spanglish cada vez que alguien dice "mi jefita" en medio de una oración en inglés.

**Guy Debord** — *La sociedad del espectáculo* (1967). Las plataformas digitales son el espectáculo integrado: no representan la vida, la sustituyen.

**György Lukács** — La reificación como proceso por el cual las relaciones humanas se convierten en relaciones entre cosas. Google Translate que "corrige" el Spanglish hacia monolingüismo es reificación lingüística.

**Michel Foucault / Giorgio Agamben** — El biopoder como administración de los cuerpos. Los sistemas de reconocimiento facial que fallan con acentos mestizos: el cuerpo del migrante como dato antes que como sujeto.

Otros referentes: Theodor Adorno, Erich Fromm, Karl Marx, Tiqqun, Gilles Deleuze, Jean Baudrillard, David Graeber, Pierre Bourdieu.

---

## Diseño como posición

La paleta de SENSUS NEPANTLA es una arqueología cromática de la frontera:

- **Negro profundo `#0D0D0D`** — La noche del desierto. La vigilancia que no se ve pero opera.
- **Crema `#E8E0D0`** — La tierra seca del altiplano.
- **Terracota `#C65D3E`** — La tierra de la frontera. El adobe. Lo que se construye con lo que hay.
- **Neón `#00B4D8`** — El semáforo del cruce. La pantalla del teléfono en la oscuridad. La luz que se filtra por el muro.
- **Caliche `#8B1A1A`** — La sangre seca en el desierto de Sonora.

El fondo tiene una textura de rejilla microscópica: la misma que tienen los formularios migratorios, los cuadriculados de los centros de detención, los píxeles de las cámaras de vigilancia. Ese patrón visual no es decoración: es documentación.

El héroe dice **DoNotTryToReadThis** porque el primer acto de resistencia es nombrar la vigilancia que pesa sobre el texto antes de que el lector lo toque.

---

## Nepantla como método

Anzaldúa describe la nepantlera — la habitante del umbral — no como alguien atrapado entre dos mundos sino como alguien que puede ver desde ambos sin pertenecer a ninguno. Esa posición no es desventaja epistemológica: es la única desde la que ciertas verdades son visibles.

SENSUS NEPANTLA practica eso como método lexicográfico. Cada entrada existe en los dos idiomas al mismo tiempo. No alterna: coexiste. El significado no está en el español ni en el inglés sino en la tensión entre ambos, en lo que se produce exactamente donde el code-switch ocurre.

Esa tensión no se resuelve. Se habita.

---

## Cómo usarlo

### Opción A — Clonar el repositorio
```bash
git clone https://github.com/NigelMoonwriter/sensus_nepantla.git
```
Abrir `sensus-nepantla.html` en cualquier navegador.

### Opción B — Descargar directamente
Ir al repositorio → `sensus-nepantla.html` → Download raw file → doble clic.

### Opción C — Usar en línea
**[sensus-nepantla en GitHub Pages](https://nigelmoonwriter.github.io/sensus_nepantla/)**

---

## Parte del Entorno Greka

| Diccionario | Campo | Entradas |
|---|---|---|
| [SENSUS LATINUS](https://github.com/NigelMoonwriter/sensus_latinus) | Latín · Griego | 27 |
| [SENSUS GRAECUS](https://github.com/NigelMoonwriter/sensus_graecus) | Griego clásico | 31 |
| [SENSUS SEMANNSIS](https://github.com/NigelMoonwriter/sensus_semannsis) | Griego · IA | 61 |
| [SENSUS NEPANTLA](https://github.com/NigelMoonwriter/sensus_nepantla) | Spanglish | 27 |

El índice central: [entorno_greka](https://github.com/NigelMoonwriter/entorno_greka)

---

## Licencia

`CC BY-NC-SA 4.0` — Libre para uso y adaptación no comercial con atribución.

---

**Rei García / KhaosLiminal / Sarayu Aguilar**
Morelia, Michoacán, México — 2026

*Un diccionario que documenta lo que otros diccionarios declararon inexistente. No corrige. No estandariza. Registra. Analiza. Celebra. Teoriza.*

#DoNotTryToReadThis #Nepantla #BorderSyntax