# Estimación del tamaño efectivo poblacional: desarrollo y evaluación de un algoritmo en R basado en Stairway Plot

Este algoritmo ha sido diseñado para el Trabajo de Fin de Máster titulado *"Estimación del tamaño efectivo poblacional: desarrollo y evaluación de un algoritmo en R basado en Stairway Plot"*.

## Descripción del proyecto

En este trabajo se desarrolla y evalúa un algoritmo de estimación del tamaño efectivo poblacional (Ne) y los correspondientes tiempos de coalescencia, basado en la implementación de la metodología de Stairway Plot en R. El objetivo principal es evaluar la precisión de las estimaciones de Ne y los tiempos de coalescencia en diferentes escenarios demográficos mediante simulaciones de espectros de frecuencias de sitio (SFS). La metodología incluye la simulación de SFS bajo diversos modelos demográficos, el remuestreo bootstrap para generar distribuciones aleatorias y la optimización de parámetros como theta, lo que permite obtener estimaciones más ajustadas de los parámetros poblacionales.

Los resultados muestran que el modelo neutro estándar (SNM) es adecuado para capturar la variabilidad genética en muestras pequeñas, aunque presenta discrepancias en las variantes raras, lo cual podría explicarse por un tamaño efectivo variable o una tasa de mutación elevada. Los modelos más complejos, como los de cuello de botella y migración, evidencian limitaciones en la estimación de Ne debido a la dificultad para modelar eventos demográficos complejos en muestras de pequeño tamaño.

En conclusión, el algoritmo propuesto realiza estimaciones suficientemente precisas de Ne en escenarios demográficos sencillos, pero señala la necesidad de enfoques más avanzados y robustos para abordar modelos más complejos y asegurar la precisión en las estimaciones.

Los pasos principales involucrados en el desarrollo e implementación del algoritmo son los siguientes:

1. **Implementación del algoritmo**:
    - Configuración inicial: Configuración de los parámetros y variables iniciales.
    - Definición de funciones clave: Desarrollo de las funciones principales necesarias para el análisis.
    - Optimización de theta: Optimización del tamaño efectivo poblacional (theta) mediante estimación de máxima verosimilitud.
    - Estimación de tiempos de coalescencia y tamaño efectivo poblacional: Estimación de los tiempos de coalescencia y el tamaño efectivo poblacional para diferentes modelos demográficos.

2. **Simulación de datos**:
    - Modelos demográficos: Definición de los modelos demográficos utilizados para simular los datos genómicos.
    - Simulación del SFS: Simulación del espectro de frecuencias de alelos (SFS) bajo cada modelo demográfico.
    - Remuestreo bootstrap: Aplicación de métodos de remuestreo bootstrap para evaluar la incertidumbre.
    - Estimación del tamaño efectivo poblacional y los tiempos de coalescencia para cada escenario demográfico.

## Requisitos

Para ejecutar este proyecto, asegúrate de tener instalados los siguientes paquetes:

- R (versión 4.0 o superior)
- Paquetes de R:
  - `ggplot2`
  - `optimx`
  - `msprime` (a través de reticulate en R)

Además, necesitas tener Python instalado junto con el paquete `msprime` a través de reticulate.

## Instalación

### Requisitos previos
- Instalar R y Python: Asegúrate de tener R y Python instalados en tu sistema.
- Instalar dependencias en R:
```r
install.packages(c("ggplot2", "optimx", "reticulate"))
```
- Instalar msprime en Python:
```bash
pip install msprime
```

## Uso

Ejemplo básico de uso:
```r
# Configuración de los parámetos iniciales
set.seed(123)
n <- 10  # Tamaño de la muestra
mu <- 1e-7  # Tasa de mutación
L <- 10000  # Longitud de la secuencia

# Generación de theta
theta_values <- 10^(runif(n - 1, -3, -1))
```
