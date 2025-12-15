
Open In Colab

# Matemáticas y Estadística en la Inteligencia Artificial

## Introducción
La inteligencia artificial (IA) combina matemáticas, estadística y programación para analizar datos y resolver problemas del mundo real.
Las matemáticas permiten modelar fenómenos, mientras que la estadística ayuda a interpretar la información y tomar decisiones bajo incertidumbre.

> La inteligencia artificial no existiría sin las matemáticas y la estadística.

---

## Relación entre Matemáticas, Estadística e IA

### Matemáticas
Las matemáticas constituyen la base teórica de la inteligencia artificial y se utilizan para:

- Representar datos mediante vectores y matrices
- Optimizar modelos
- Construir funciones de activación
- Ajustar parámetros de aprendizaje

Ejemplo de función matemática utilizada en inteligencia artificial:
~~~
\[
f(x) = \frac{1}{1 + e^{-x}}
\]
~~~
---

### Estadística
La estadística permite analizar datos reales, detectar patrones y medir la incertidumbre.
Algunos conceptos fundamentales son:

- Media
- Mediana
- Varianza
- Probabilidad
- Correlación

Estos conceptos son esenciales para entrenar y evaluar modelos de inteligencia artificial.

---

## Librerías de Python para Análisis de Datos

### Pandas
Pandas se utiliza para la manipulación y análisis de datos estructurados.

Usos principales:
- Lectura de archivos CSV y Excel
- Limpieza de datos
- Análisis estadístico descriptivo
~~~
python
import pandas as pd
df = pd.read_csv("datos.csv")
df.describe()
~~~
     

## NumPy
NumPy permite realizar cálculos matemáticos eficientes con arreglos numéricos.
Usos principales:

- Operaciones vectoriales
- Cálculo de estadísticas
- Manejo de matrices
~~~
import numpy as np
datos = np.array([10, 20, 30])
np.mean(datos)
~~~
## Matplotlib

Matplotlib se usa para crear visualizaciones básicas de datos.
Usos principales:

- Gráficos de líneas
- Gráficos de barras
- Histogramas
~~~
import matplotlib.pyplot as plt
plt.plot([1,2,3], [4,5,6])
plt.show()
~~~
## Seaborn

Seaborn facilita la creación de gráficos estadísticos avanzados.
Usos principales:

- Visualización de distribuciones
- Gráficos comparativos
- Análisis exploratorio de datos

~~~
import seaborn as sns
sns.histplot([1,2,2,3,3,3])
~~~
---

## Ejercicios de Lógica de Programación

---

## Ejercicio 1: Sistema de riego inteligente

---
~~~
HUMEDAD_OPTIMA = 60
MARGEN_SEGURIDAD = 5

humedad = [55, 62, 58, 45, 70, 50, 65]
lluvia = [False, True, False, False, True, False, False]

riegos = 0

for dia in range(7):
    if humedad[dia] < HUMEDAD_OPTIMA - MARGEN_SEGURIDAD and not lluvia[dia]:
        riegos += 1

print("Total de riegos realizados:", riegos)
print("Ahorro de agua estimado:", 7 - riegos)
~~~
## Ejercicio 2: Clasificación de calidad de cosecha
def peso_promedio(pesos):
    return sum(pesos) / len(pesos)
~~~
def porcentaje_defectos(defectuosas, total):
    return (defectuosas / total) * 100

lotes = int(input("Número de lotes: "))

for i in range(lotes):
    pesos = list(map(float, input("Pesos del lote: ").split()))
    defectuosas = int(input("Cantidad defectuosa: "))

    promedio = peso_promedio(pesos)
    defectos = porcentaje_defectos(defectuosas, len(pesos))

    if promedio >= 200 and defectos <= 5:
        categoria = "A"
    elif promedio >= 150 and defectos <= 10:
        categoria = "B"
    else:
        categoria = "Rechazo"

    print(f"Lote {i+1}: Categoría {categoria}")
~~~
---

## Ejercicio 3: Planificación de rotación de cultivos

---
~~~
CONSUMO_N = {
    "maíz": 30,
    "soya": 20,
    "trigo": 25,
    "descanso": 0
}

def consumo_total(cultivos):
    return sum(CONSUMO_N[c] for c in cultivos)

def verificar_rotacion(cultivos):
    consecutivos = 1
    for i in range(1, len(cultivos)):
        if cultivos[i] == cultivos[i-1]:
            consecutivos += 1
            if consecutivos > 3:
                return True
        else:
            consecutivos = 1
    return False

cultivos = ["maíz","maíz","maíz","maíz","soya","trigo","descanso"]

print("Consumo total de nitrógeno:", consumo_total(cultivos))

if verificar_rotacion(cultivos):
    print("Se recomienda alternar cultivos o dejar descanso")
---
~~~
## Ejercicio 4: Control de inventario

---
~~~
MINIMO = 10

inventario = {
    "fertilizantes": 50,
    "semillas": 40,
    "pesticidas": 30
}

precios = {
    "fertilizantes": 5,
    "semillas": 2,
    "pesticidas": 8
}

for producto in inventario:
    ventas = int(input(f"Ventas de {producto}: "))
    inventario[producto] -= ventas
    if inventario[producto] < MINIMO:
        print(f"Alerta: {producto} bajo stock")

def valor_total(inv, precios):
    return sum(inv[p] * precios[p] for p in inv)

print("Inventario final:", inventario)
print("Valor total del inventario:", valor_total(inventario, precios))
~~~
---

## Ejercicio 5: Evaluación de desempeño de maquinaria

---
~~~
EXCELENTE = 1.5
ACEPTABLE = 1.0

def rendimiento(superficie, horas):
    return superficie / horas

def consumo(litros, superficie):
    return litros / superficie

tractores = int(input("Cantidad de tractores: "))

for i in range(tractores):
    horas = float(input("Horas trabajadas: "))
    litros = float(input("Litros consumidos: "))
    superficie = float(input("Superficie cubierta: "))

    r = rendimiento(superficie, horas)
    c = consumo(litros, superficie)

    if r >= EXCELENTE and c <= 5:
        estado = "Excelente"
    elif r >= ACEPTABLE:
        estado = "Aceptable"
    else:
        estado = "Deficiente"

    print(f"Tractor {i+1}: Desempeño {estado}")
     ~~~
