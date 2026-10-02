# Datasets, variables y criterios de selección

> Borrador. Cada integrante debe aportar sus datasets/variables y criterios en la
> sección 4 (`[COMPLETAR]`).

## 1. Datasets seleccionados

| # | Dataset | Acceso | Cobertura | Rol |
|---|---|---|---|---|
| 1 | MIT Election Lab – U.S. House (`doi:10.7910/DVN/IG0UN2`) | descarga manual | 1976–2024, por distrito | primario |
| 2 | MIT Election Lab – U.S. Senate (`doi:10.7910/DVN/PEJ5QU`) | descarga manual | 1976–2024, por estado | primario |
| 3 | BLS – LAUS (desempleo estatal) | API v2 | mensual | variable explicativa |
| 4 | BLS – CPI (inflación) | API v2 | mensual, nacional/áreas | variable explicativa |
| 5 | FEC – resultados oficiales | descarga manual | por ciclo | validación |
| 6 | House.gov – Election Statistics | descarga manual | 1920–presente | validación / respaldo histórico |

## 2. Variables

**Dependientes (resultado electoral)**
- `margin` two-party por distrito/estado y ciclo (pp, R − D).
- `winner_party`, `flip` (cambio de partido ganador entre ciclos).
- `swing` (booleano): |margen promedio| < 10 pp o ≥ 1 flip (D-01).

**Independientes (contexto económico)**
- Tasa de desempleo estatal (LAUS), nivel y variación interanual.
- Inflación CPI, nivel y variación interanual.
- Medidas en el año de elección y/o 12 meses previos (a definir).

**De control / contexto**
- Partido del presidente en cada ciclo; tipo de elección (midterm vs. presidencial).
- Año de redistricting (para filtrar series House, D-02/D-06).

## 3. Correlaciones candidatas a explorar

1. Δ desempleo estatal (12 m) vs. cambio de margen del oficialismo, en estados Senate swing.
2. Inflación nacional vs. pérdida de bancas del partido del presidente por midterm.
3. Margen promedio vs. probabilidad de flip (¿los márgenes chicos predicen flips?).
4. Comparación midterm vs. presidencial en distritos swing.

## 4. Criterios de selección

Criterios comunes del grupo:
- **Oficialidad y trazabilidad:** fuente gubernamental o académica con documentación.
- **Granularidad:** distrito/estado, no solo agregado nacional.
- **Cobertura temporal** suficiente (≥ 2016–2024).
- **Acceso reproducible** (descarga o API pública y gratuita).
- **Cruzabilidad:** claves comunes (estado, año) entre datasets.
- **Validación cruzada:** FEC y House.gov permiten contrastar a MIT.

Aporte por integrante:

| Integrante | Dataset/variable propuesta | Criterio / justificación |
|---|---|---|
| [COMPLETAR] | | |
| [COMPLETAR] | | |
| [COMPLETAR] | | |

## 5. Avance técnico actual

Ya implementado (`analysis/01_mit_swing_classification.py`): clasificación swing →
74 distritos House y 11 estados Senate Class 2 (`output/`). Pendiente: ingesta BLS,
cruce con FEC/House.gov (roadmap 2.5, Fase 3).
