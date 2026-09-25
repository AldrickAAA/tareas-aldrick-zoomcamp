# Guía paso a paso · Tarea 1 (ML Zoomcamp 2026)

> Plazo: **lun 28 sep 23:00 UTC** (mar 29 sep 01:00 en Madrid) · Objetivo: **enviarla el dom 27 sep**
> Se trabaja en `homework.ipynb` (kernel "Python 3.12 (ml-zoomcamp-2026)"). Esta guía da pistas, no soluciones.

**Antes de empezar:** ver las lecciones 1.8 (álgebra lineal) y 1.9 (Pandas).

Columnas: `model_year, origin, fuel_type, drivetrain, num_doors, engine_displacement, num_cylinders, horsepower, vehicle_weight, acceleration, fuel_efficiency_mpg`

## Estado
- [x] Entorno, kernel, dataset y notebook base
- [x] Guía NumPy (1.7): `1.7-numpy-guia.ipynb`
- [ ] Lecciones 1.8 y 1.9
- [ ] Q1 · [ ] Q2 · [ ] Q3 · [ ] Q4 · [ ] Q5 · [ ] Q6 · [ ] Q7
- [ ] Restart + Run All sin errores
- [ ] Auditoría con Claude ("corrige")
- [ ] `git push` + envío en la plataforma

## Pistas por pregunta

| Pregunta | Qué hay que conseguir | Herramienta | ⚠️ Trampa |
|---|---|---|---|
| Q1 | Versión de pandas | `__version__` | — |
| Q2 | Número de filas | `len()`, `.shape`, `.info()` | Hazlo de 2 formas y compara |
| Q3 | Valores distintos de `fuel_type` | `.nunique()`, `.unique()`, `.value_counts()` | — |
| Q4 | Cuántas **columnas** tienen nulos | `df.isnull().sum()` | No es cuántos nulos hay, sino en cuántas columnas |
| Q5 | Máx. `fuel_efficiency_mpg` de Asia | Mira antes los valores de `origin` y luego `df[condición]` + `.max()` | Mayúsculas o espacios → DataFrame vacío |
| Q6 | Mediana → moda → `fillna` → mediana | `.median()`, `.mode()`, `.fillna()` | `.mode()` devuelve una Series; `fillna` no cambia el original si no asignas el resultado |
| Q7 | Regresión lineal "a mano" | ver la tabla de abajo | `*` ≠ `@`; el orden importa |

### Q7 paso a paso (comprueba `.shape` en cada paso)
| Paso | Qué haces | Herramienta | Forma |
|---|---|---|---|
| 1 | Filtrar Asia | como en Q5 | (n, 11) |
| 2 | 2 columnas: `vehicle_weight`, `model_year` | `df[['a', 'b']]` | (n, 2) |
| 3 | Primeras 7 filas | `.head()` / `.iloc[]` | (7, 2) |
| 4 | Pasar a NumPy → `X` | `.values` / `.to_numpy()` | (7, 2) |
| 5 | `XTX` = `X.T` por `X` | `@` o `.dot()` | (2, 2) |
| 6 | Invertir | `np.linalg.inv()` | (2, 2) |
| 7 | `y = [1100, 1300, 800, 900, 1000, 1100, 1200]` | `np.array()` | (7,) |
| 8 | `w` = inversa · `X.T` · `y` | `@` en ese orden | (2,) |
| 9 | Suma de `w` | `.sum()` | número |

Comprobación extra: `XTX @ inversa` ≈ matriz identidad.

## Cierre
1. Restart + Run All → sin errores
2. Pedir a Claude la auditoría
3. `git add . && git commit -m "Tarea 1" && git push`
4. Enviar en https://courses.datatalks.club/ml-zoomcamp-2026/homework/hw01 con la URL:
   `https://github.com/AldrickAAA/tareas-aldrick-zoomcamp/blob/main/01-intro/homework.ipynb`
