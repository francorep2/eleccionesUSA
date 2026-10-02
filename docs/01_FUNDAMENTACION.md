# Fundamentación — Elecciones de EE.UU. (Midterms 2026)

> Borrador. Completar los campos `[COMPLETAR]` con datos del grupo.

**Integrantes:** [COMPLETAR nombres]
**Materia / TPO:** [COMPLETAR]

## 1. Tipo de trabajo: exploratorio

El trabajo es **exploratorio**: no busca probar una hipótesis causal ni construir un
modelo predictivo validado, sino identificar **posibles correlaciones** entre
resultados electorales históricos y variables económicas, para decidir qué vale la
pena profundizar. Las conclusiones se formulan como asociaciones, no como causas.

## 2. Pregunta guía

¿Se asocian los resultados históricos de las elecciones legislativas de EE.UU.
(House y Senate) con el contexto económico, y qué distritos/estados son los más
competitivos de cara a las elecciones de medio término del 3/11/2026?

Sub-preguntas:
1. ¿Qué distritos House y estados Senate son *swing* según su historial reciente?
2. ¿Hay correlación entre desempleo/inflación y el cambio de voto del partido oficialista?
3. ¿Las midterms muestran un patrón de castigo al partido del presidente (2018, 2022)?

## 3. Estado del arte

La literatura de ciencia política ofrece varios marcos relevantes
(**verificar y completar las referencias bibliográficas antes de entregar**):

- **Castigo al oficialismo en midterms.** Tufte (1975) documentó que el partido del
  presidente pierde bancas en la elección de medio término en casi todos los ciclos
  de posguerra; la magnitud se asocia con la aprobación presidencial y la economía.
  Campbell (1960) lo explicó con la teoría de *surge and decline*.
- **Voto económico.** Lewis-Beck y Stegmaier revisan la evidencia de que el
  desempeño económico (desempleo, inflación, ingreso) influye en el voto al partido
  de gobierno; Erikson (1990) lo aplica específicamente al voto al Congreso.
- **Modelos de fundamentals.** Abramowitz y otros modelos de pronóstico usan
  variables estructurales (economía, aprobación, incumbencia) sin depender de
  encuestas de intención de voto, que es el enfoque aquí adoptado.
- **Competitividad y redistricting.** El rediseño de distritos (gerrymandering,
  mapas 2021) altera la comparabilidad entre ciclos, lo que obliga a tratar con
  cuidado las series de House (ver `DECISIONES.md`, D-02 y D-06).

**Brecha que aborda el trabajo:** cruzar, a nivel de distrito/estado, el historial
de márgenes (datos abiertos) con indicadores económicos oficiales (BLS), sin
depender de polling ni de ratings de expertos.

## 4. Fuentes y procedencia

| Fuente | Organismo | Tipo | Rol |
|---|---|---|---|
| MIT Election Lab (Harvard Dataverse) | MIT | CSV/TAB, sin API | Datos primarios House/Senate 1976–2024 |
| BLS (LAUS, CPI) | U.S. Dept. of Labor | API REST (key gratuita) | Variables económicas |
| FEC – Election results | Federal Election Commission | XLS/CSV por ciclo | Tabla de referencia oficial |
| Election Statistics 1920–present | U.S. House of Representatives (History, Art & Archives) | Tablas por año | Tabla de referencia histórica |

Detalle de acceso y variables: ver `02_DATASETS_Y_VARIABLES.md`.

## 5. Alcance y limitaciones

- Sin polling ni ratings (Cook, Sabato): solo *fundamentals*.
- Correlación ≠ causalidad; n reducido de ciclos (pocas midterms comparables).
- Cambios de mapa por redistricting limitan la comparación House entre ciclos.
- Datos 2024 pueden no estar completos en todas las fuentes (verificar, roadmap 1.3).
- Census ACS queda fuera de alcance (posible extensión futura).
