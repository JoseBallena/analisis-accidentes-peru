
# Análisis de Accidentes de Tránsito en Perú (2022-2023)

Este proyecto realiza un análisis exploratorio de datos sobre accidentes de tránsito en algunas regiones del Perú, utilizando Python y pandas.

## 1. Carga de datos

```python
import pandas as pd

data = {
    "Año": [2022, 2022, 2022, 2023, 2023, 2023],
    "Departamento": ["Lima", "Arequipa", "Cusco", "Lima", "Arequipa", "Cusco"],
    "Tipo_Accidente": ["Colisión", "Atropello", "Volcadura", "Colisión", "Atropello", "Volcadura"],
    "Heridos": [5, 2, 3, 6, 1, 4],
    "Fallecidos": [1, 0, 0, 2, 1, 1]
}

df = pd.DataFrame(data)
df
```

## 2. Estadísticas generales

```python
df.describe()
```

## 3. Análisis por tipo de accidente

```python
df.groupby('Tipo_Accidente')[['Heridos', 'Fallecidos']].sum()
```

## 4. Visualización

```python
import matplotlib.pyplot as plt

df.groupby('Tipo_Accidente')[['Heridos', 'Fallecidos']].sum().plot(kind='bar', figsize=(8,5))
plt.title('Heridos y Fallecidos por Tipo de Accidente')
plt.ylabel('Cantidad')
plt.xticks(rotation=45)
plt.grid(axis='y')
plt.tight_layout()
plt.show()
```

## 5. Conclusiones

- Las colisiones son los accidentes más frecuentes con mayor cantidad de heridos.
- Atropellos, aunque menos frecuentes, tienen una tasa de fallecidos relativamente alta.
- La región de Lima registra mayor número de víctimas.

---

Este análisis es un ejemplo básico. En una versión futura se puede escalar con datasets abiertos de INEI o MTC.
