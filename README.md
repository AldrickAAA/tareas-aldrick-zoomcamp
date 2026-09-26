# ML Zoomcamp 2026

Tareas, prácticas y proyectos del [Machine Learning Zoomcamp 2026](https://github.com/DataTalksClub/machine-learning-zoomcamp) (DataTalks.Club).

## Estructura

```
├── 01-intro/          Módulo 1 · Introducción al ML
├── 02-regression/     Módulo 2 · Regresión
├── ...                (una carpeta por módulo)
├── pyproject.toml     Dependencias (uv)
└── uv.lock            Versiones fijadas
```

Convención de nombres dentro de cada módulo:

| Archivo | Contenido |
|---|---|
| `homework.ipynb` | Tarea evaluable del módulo |
| `X.Y-tema-guia.ipynb` | Guía de estudio de una lección |
| `X.Y-tema-practica.ipynb` | Práctica siguiendo el vídeo de la lección |
| `GUIA_TAREAn.md` | Pistas paso a paso de la tarea |

Los datasets **no** se versionan (`*.csv` en `.gitignore`): cada notebook indica de dónde descargarlos.

## Progreso

| Módulo | Tarea | Prácticas |
|---|---|---|
| 01 · Intro | [homework.ipynb](01-intro/homework.ipynb) | [NumPy](01-intro/1.7-numpy-guia.ipynb) · [Álgebra lineal](01-intro/1.8-algebra-lineal-practica.ipynb) · [Pandas](01-intro/1.9-pandas-practica.ipynb) |
| 02 · Regresión | — | — |

## Entorno

```bash
uv sync                    # crea .venv con las versiones de uv.lock
uv run jupyter notebook    # o abre los notebooks en el editor con el kernel .venv
```

Dataset del módulo 1:

```bash
cd 01-intro
curl -LO https://raw.githubusercontent.com/DataTalksClub/machine-learning-zoomcamp/main/cohorts/2026/data/car_fuel_efficiency_2026.csv
```
