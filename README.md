# Repo-Guardian - Herramienta de Auditoría y Reparación de Repositorios Git

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Repo-Guardian** es una herramienta avanzada diseñada para auditar, reparar y restaurar la integridad de los repositorios `.git`. Con una interfaz de línea de comandos (CLI) y una interfaz de usuario en terminal (TUI), Repo-Guardian permite verificar y restaurar objetos Git corruptos, ya sea en formato suelto o empaquetado en packfiles.

##  Motivación

Repo-Guardian surge para resolver problemas comunes en Git, como la corrupción de objetos o alteraciones en el historial del repositorio. Su objetivo es garantizar la integridad de los repositorios, facilitando su reparación y ofreciendo un análisis visual de los cambios mediante un grafo DAG.

##  Características Destacadas

- **Auditoría Criptográfica** de objetos Git usando SHA-1/SHA-256
- **Recuperación de Historiales Alterados** (force-push, rebase, filter-repo)
- **Generación de Grafo DAG** para análisis y visualización (GraphML/Graphviz)
- **Interfaz TUI** interactiva con soporte para seguimiento de progreso y reparación directa
- **Automatización completa en CI/CD** con pruebas BDD (Behave) y cobertura de código ≥80%

## Comandos Principales

| Comando            | Parámetros                  | Descripción                                                                       |
|--------------------|-----------------------------|-----------------------------------------------------------------------------------|
| `scan`             | `<ruta>`                    | Realiza la auditoría de objetos Git (loose/packed) usando SHA-1/SHA-256            |
| `repair`           | `<ruta>`                    | Reconstruye el historial utilizando `git rebase --onto` y genera scripts de reparación |
| `export-graph`     | `--out <archivo>` (obligatorio) | Exporta el grafo DAG a formato GraphML con metadatos (SHA, autor, timestamp, estado) |
| `tui`              | `<ruta>`                    | Inicia la interfaz interactiva de terminal con seguimiento de progreso y reparación |

### Ejemplos de Uso

```bash
# Realizar un escaneo básico del repositorio
guardian scan ./mi_repositorio

# Exportar el grafo DAG para análisis posterior
guardian export-graph --out grafo_recuperado.graphml

# Iniciar la interfaz TUI interactiva
guardian tui ./mi_repositorio
```

## Diagrama de contexto

<img src="docs/img/Diagrama de contexto.jpg" width="600">



