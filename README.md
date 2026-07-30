# RetailMax Data Platform
### End-to-End Data Engineering Challenge

> Proyecto desarrollado como solución a la Prueba Técnica para Ingeniero de Datos.

---

# Autor

**José Haminton Quiñones**

Tecnólogo en Desarrollo de Software | Data Engineering Trainee

Colombia

---

# Objetivo del proyecto

Construir un pipeline de datos End-to-End siguiendo una arquitectura Medallion (Bronze, Silver y Gold) que permita transformar datos operacionales del negocio RetailMax en información analítica para la toma de decisiones.

Este proyecto busca simular un entorno empresarial real aplicando buenas prácticas de Ingeniería de Datos:

- Generación de datos sintéticos
- Infraestructura como código
- Lakehouse
- ETL/ELT
- Calidad de datos
- Gobierno de datos
- Orquestación
- Analítica empresarial

---

# Escenario seleccionado

## Escenario B — Retail y Comercio Electrónico

Seleccioné este escenario porque es el que más se relaciona con mi experiencia profesional.

Durante mi experiencia laboral he trabajado con:

- inventarios
- productos
- clientes
- procesos comerciales
- indicadores
- gestión de información

Esto me permite comprender mejor las reglas de negocio y diseñar un modelo de datos más cercano a una implementación real.

---

# Filosofía de desarrollo

Este proyecto no fue desarrollado únicamente para cumplir una prueba técnica.

Mi objetivo fue utilizarlo como laboratorio de aprendizaje para fortalecer mis conocimientos como Ingeniero de Datos.

Siempre intento responder tres preguntas antes de escribir código:

- ¿Qué problema resuelve?
- ¿Por qué esta es la mejor alternativa?
- ¿Qué ocurriría si el volumen de datos creciera diez veces?

Considero que comprender el motivo de una implementación es más importante que memorizar código.

---

# Arquitectura General

Fuente de datos

↓

Generación de datos sintéticos

↓

Base de datos SQL

↓

Bronze

↓

Silver

↓

Gold

↓

KPIs

↓

Dashboard

---

# Tecnologías utilizadas

| Tecnología | Propósito |
|------------|-----------|
| Python | Generación y procesamiento de datos |
| PySpark | Transformaciones distribuidas |
| Databricks | Desarrollo del pipeline |
| YAML | Configuración del proyecto |
| DBLDatagen | Generación de datos sintéticos estructurados y reproducibles para Spark|
| Faker | Datos sintéticos |
| Pandas | Validaciones y pruebas |
| Delta Lake | Almacenamiento |
| SQL | Consultas |
| Git | Versionamiento |
| Power BI | Visualización |

---

# ¿Por qué elegí estas tecnologías?

## Python

Porque permite construir soluciones de ingeniería de datos de manera sencilla, modular y ampliamente compatible con el ecosistema de Big Data.

---

## PySpark

Permite escalar el procesamiento de datos cuando el volumen aumenta sin modificar la lógica principal del proyecto.

---

## YAML

Toda la configuración del proyecto se encuentra desacoplada del código.

Esto permite modificar:

- volumen de registros
- fechas
- catálogos
- distribución de datos
- parámetros

sin necesidad de editar el código fuente.

---

## DBLDatagen

Genera millones de registros distribuidos en Spark y es Escala para Big Data

---
## Faker

Se utiliza para generar información realista y reproducible.

No se busca únicamente generar datos aleatorios, sino construir datos con comportamiento cercano al negocio.

---

## Databricks

Permite trabajar bajo arquitectura Lakehouse y facilita el procesamiento distribuido utilizando Spark.

---

# Organización del proyecto

```
RetailMax/

│

├── config/

│ └── config.yaml

│

├── data/

│ ├── raw/

│ ├── bronze/

│ ├── silver/

│ └── gold/

│

├── notebooks/

│ ├── 01_generacion_datos

│ ├── 02_bronze

│ ├── 03_silver

│ ├── 04_gold

│ └── 05_validaciones

│

├── src/

│ ├── generators/

│ ├── transformations/

│ ├── utils/

│ └── validations/

│

├── docs/

│ ├── arquitectura.png

│ ├── modelo_er.png

│ └── evidencias/

│

├── infra/

│

├── orchestration/

│

└── README.md
```

---

# Metodología utilizada

Cada notebook tiene una estructura común.

## 1. Objetivo

Describe el propósito de la etapa.

---

## 2. Justificación técnica

Explica por qué se implementó esa solución.

---

## 3. Desarrollo

Implementación.

---

## 4. Validaciones

Verificación de resultados.

---

## 5. Conclusiones

Lecciones aprendidas.

---

# Arquitectura Medallion

## Bronze

Objetivo:

Conservar los datos exactamente como llegan desde la fuente.

Características:

- Sin reglas de negocio
- Con metadatos
- Datos históricos
- Auditoría

---

## Silver

Objetivo:

Transformar los datos para garantizar calidad.

Procesos:

- limpieza
- tipificación
- eliminación de duplicados
- tratamiento de nulos
- validaciones
- enmascaramiento
- enriquecimiento

---

## Gold

Objetivo:

Construir modelos analíticos.

Incluye:

- dimensiones
- hechos
- KPIs
- indicadores
- tablas para Power BI

---

# Calidad de datos

Cada ejecución genera validaciones sobre:

- registros nulos
- duplicados
- integridad referencial
- tipos de datos
- reglas de negocio

Los errores son enviados a tablas de auditoría para su análisis.

---

# Principios utilizados

Durante el desarrollo se siguieron los siguientes principios:

✔ Código reutilizable

✔ Código modular

✔ Configuración desacoplada

✔ Separación de responsabilidades

✔ Documentación continua

✔ Escalabilidad

✔ Reproducibilidad

✔ Versionamiento

✔ Trazabilidad

---

# Aprendizajes obtenidos

Este proyecto me permitió fortalecer conocimientos en:

- Modelado dimensional
- Arquitectura Medallion
- Ingeniería de Datos
- Spark
- Databricks
- Generación de datos sintéticos
- ETL
- Gobierno de datos
- Calidad de datos
- Automatización

---

# Próximas mejoras

- Implementar Delta Live Tables
- Unity Catalog
- Great Expectations
- CI/CD
- Terraform
- Monitoreo
- Data Quality Dashboard
- Machine Learning para predicción de demanda

---

# Reflexión personal

Más que desarrollar una prueba técnica, este proyecto representa mi proceso de formación como Ingeniero de Datos.

Cada módulo fue construido intentando comprender el porqué de las decisiones técnicas y no únicamente su implementación.

Mi objetivo es continuar evolucionando este proyecto hasta convertirlo en un ejemplo de arquitectura de datos cercana a un entorno productivo.
