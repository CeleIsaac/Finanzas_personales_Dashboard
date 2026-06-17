# 💰 Dashboard de Finanzas Personales — Power BI

> ⚠️ Los datos presentados en este proyecto son **ficticios** y fueron generados únicamente con fines demostrativos, preservando la estructura y lógica real del proyecto original.

## 📋 Descripción

Dashboard desarrollado en Power BI que permite monitorear y analizar los movimientos bancarios de dos cuentas de forma consolidada. Cubre el seguimiento mensual de ingresos, gastos y ahorro, el control de gastos variables contra un presupuesto definido, y la comparación del gasto total contra un objetivo mensual máximo.

Inicialmente el seguimiento se realizaba manualmente en Excel. La migración a Power BI permitió automatizar la consolidación de archivos bancarios mensuales, aplicar categorización automática por palabras clave, y visualizar la información de forma interactiva.

**Problema que resuelve:** la falta de visibilidad sobre los hábitos de gasto, sin un sistema de seguimiento es difícil saber en qué categorías se gasta más, si se cumple el presupuesto, o cuánto se ahorra realmente cada mes.

## 🛠️ Herramientas utilizadas

**Power BI Desktop** — modelado de datos, DAX, visualización

**Power Query (M)** — transformación y limpieza de datos

**Excel** — fuente de datos origen

## 🗂️ Estructura del proyecto

```
├── docs/
│   └── Informe_Finanzas_Personales.pdf   # Documentación técnica completa
├── screenshots/
│   ├── resumen.png
│   ├── gastos.png
│   └── detalle.png
└── README.md
```

## 📊 Páginas del dashboard

### 1. Resumen
Vista general del estado financiero mensual — ingresos, gastos, saldo y tasa de ahorro — con comparación contra el mes anterior y detección de movimientos sin categorizar.

<img width="866" height="486" alt="image" src="https://github.com/user-attachments/assets/30b6f35d-14b6-4c46-ae9f-1dd7b7e5acac" />


### 2. Gastos
Análisis detallado del gasto mensual por categoría, control de gastos variables contra presupuesto ((Alimentación, Agua, Electricidad, Ocio, Ropa), evolución temporal del gasto total y comparación de gasto mensual contra objetivo.


<img width="874" height="484" alt="image" src="https://github.com/user-attachments/assets/84122be7-bc60-4097-9d3a-ac8df30d5158" />


### 3. Detalle
Exploración detallada de todos los movimientos del período, permitiendo auditar el gasto por categoría, mes y fecha, e identificar movimientos específicos.

<img width="851" height="475" alt="image" src="https://github.com/user-attachments/assets/811e7f5d-6105-4351-81c3-d15de0cb8c23" />


## 🧠 Aspectos técnicos destacados

- **Combinación automática de archivos** — Power Query lee y consolida automáticamente todos los Excel mensuales de una carpeta, sin intervención manual.
- **Categorización automática por palabras clave** — lógica en Power Query (M) que asigna categoría a cada movimiento buscando coincidencias entre el concepto bancario y una tabla de palabras clave.
- **Prevención de duplicados** — clave única por movimiento para evitar que archivos solapados generen registros repetidos al actualizar.
- **Modelo semántico con tablas de planificación** — `Presupuesto` y `Objetivos` se relacionan con el modelo evitando relaciones muchos a muchos mediante tablas dimensión intermedias (`DimMes`, `DimCategoria`).
- **Inteligencia de tiempo en DAX** — comparativas mes a mes (`DATEADD`) y promedios mensuales (`AVERAGEX`) sobre tabla de calendario oficial.

## 📈 Algunos insights del análisis

- Durante el período los gastos superaron el objetivo, principalmente en abril y mayo.
- En promedio el % de ahorro mensual es de 38%, es decir, de los ingresos más de la tercera parte se destina a ahorro
- En marzo, si bien el saldo es positivo como en el resto de los meses, es significativamente menor que los demás. En este mes, los Ingresos descendieron, pero los Gastos no acompañaron ese descenso
- Abril fue el mes con mayor desvío en Alimentación, dado que el gasto superó el presupuesto en un 26%.

## 📄 Documentación completa

La documentación técnica detallada — modelo semántico, relaciones, medidas DAX, transformaciones de Power Query, decisiones de diseño y mejoras futuras — está disponible en [`docs/Informe_Finanzas_Personales.pdf`](docs/Informe_Finanzas_Personales.pdf).


---

📧 ¿Preguntas sobre el proyecto? Contactame en [tu LinkedIn] o [tu email]

