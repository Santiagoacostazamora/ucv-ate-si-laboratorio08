# UCV - ADK - Laboratorio 08

Este repositorio contiene un pequeño proyecto de agente académico basado en Google ADK (Agent Development Kit). El objetivo principal es demostrar cómo definir un agente con una herramienta simple para explicar conceptos básicos en español.

## ¿Qué incluye este proyecto?

- Un agente principal llamado `agente_ucv`.
- Una herramienta personalizada `explicar_concepto(concepto)`.
- Integración con Gemini a través de la librería `google-adk`.
- Configuración básica con Poetry y una variable de entorno `GOOGLE_API_KEY`.

## Estructura del proyecto

```text
ucv-ate-si-laboratorio08/
├── .env
├── README.md
└── laboratorio-adk-ucv/
    ├── pyproject.toml
    ├── poetry.lock
    └── agente_ucv/
        ├── __init__.py
        └── agent.py
```

## Descripción técnica

### Agente principal
El archivo principal del agente está en:

- `laboratorio-adk-ucv/agente_ucv/agent.py`

Actualmente define:

- modelo: `gemini-flash-latest`
- nombre: `agente_ucv`
- descripción: `Agente académico UCV`
- una herramienta: `explicar_concepto`

La herramienta responde con definiciones simples para conceptos como:

- `api`
- `algoritmo`
- `base de datos`

## Requisitos

- Python 3.13 o superior
- Poetry
- Una clave válida de Google AI / Gemini en la variable `GOOGLE_API_KEY`

## Instalación

1. Entrar al directorio del proyecto:

   ```bash
   cd laboratorio-adk-ucv
   ```

2. Instalar dependencias con Poetry:

   ```bash
   poetry install
   ```

3. Configurar la variable de entorno de Google:

   El proyecto incluye un archivo `.env` en la raíz del repositorio. Asegúrate de tener una clave válida asignada a:

   ```env
   GOOGLE_API_KEY=tu_clave_aqui
   ```

## Validación rápida

Se verificó que el agente carga correctamente con la configuración actual usando:

```bash
poetry run python -c "from agente_ucv.agent import root_agent; print(root_agent.name); print(root_agent.model); print(len(root_agent.tools))"
```

Resultado esperado:

```text
NAME= agente_ucv
MODEL= gemini-flash-latest
TOOLS= 1
```

## Cómo usarlo

Puedes ejecutar el agente desde el directorio `laboratorio-adk-ucv` usando el entorno de Poetry.

Ejemplo de verificación rápida de importación:

```bash
poetry run python
```

Luego, dentro de Python:

```python
from agente_ucv.agent import root_agent
print(root_agent)
```

## Estado del proyecto

Este laboratorio está en una etapa inicial y sirve como base para:

- aprender Google ADK,
- crear agentes con herramientas personalizadas,
- integrar respuestas académicas simples con Gemini.

## Sugerencia de mejora

En una siguiente iteración se puede ampliar el agente con más herramientas, contexto académico UCV y respuestas más específicas sobre materias, horarios o servicios universitarios.
