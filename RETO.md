# 🚀 Sideproject — De scripts a paquete

**Repositorio:** `sideproject-limpiador` · **Tipo:** paquete instalable de Python · **Tiempo:** 5–6 h · **Después de:** lecciones 1 a 4 de esta carpeta

> Reglas, README y lista de cierre: [`SIDEPROJECTS.md`](docs/REGLAS.md). **No hay solución: el diseño es tuyo.**

## El caso

Tus reglas de limpieza funcionan en tu máquina. Mañana entra otra persona al equipo y otros tres pipelines quieren reutilizarlas. Hay que convertirlas en un paquete que se instala, se entiende y se cambia sin romper nada.

## Qué practicas

| Lección | Dónde aparece |
|---|---|
| Git básico / ramas y remotos | Todo el trabajo va por ramas y pull requests |
| Paquetes y estilo | `pyproject.toml`, `ruff`, docstrings, type hints |
| Testing con pytest | Un test por regla, fixtures y parametrize |

## Hitos

**Hito 1 — El esqueleto.** Repositorio con `pyproject.toml`, `src/limpiador/` y `tests/`. Una sola regla dentro.
*Comprueba:* desde otra carpeta, `pip install -e .` y `python -c "import limpiador"` funcionan.

**Hito 2 — Las reglas, cada una en su PR.** Trae tus reglas del sideproject de calidad de datos. Nada directo a `main`: mínimo 4 pull requests.
*Comprueba:* `git log --oneline --graph` muestra las ramas fusionadas.

**Hito 3 — Tests.** Al menos 12: uno por regla, `parametrize` en dos y un fixture con datos pequeños y sucios.
*Comprueba:* rompe una regla a propósito y algún test falla.

**Hito 4 — Calidad.** `ruff` sin avisos, docstrings y type hints en lo público, configuración en un `dataclass`.
*Comprueba:* `help(limpiador.<tu_regla>)` se entiende sin abrir el código.

**Hito 5 — Revisión.** Abre uno de tus PR y deja 5 comentarios como si el código fuera de otra persona. Corrige al menos 3.
*Comprueba:* los comentarios y las correcciones se ven en GitHub.

**Hito 6 — Comando.** `limpiar entrada.csv salida.parquet` disponible al instalar.
*Comprueba:* funciona en un entorno virtual recién creado.

## Preguntas para defenderlo

- ¿Qué función te costó más probar? ¿Qué te dijo eso de cómo estaba escrita?
- ¿Qué va en `.gitignore` y por qué los datos no se suben?
- ¿Qué pasa con quien usa tu paquete si cambias el nombre de una función?

## Súbelo de nivel

- GitHub Actions con `ruff` y `pytest` en cada PR (mira `.github/workflows/ci.yml` de este repositorio).
- Cobertura con `pytest-cov` y la insignia en el README.
