# 🛠️ Predictive Maintenance: Vibration Analysis & Fault Diagnosis with FFT

### 📋 Descripción del Proyecto
Este proyecto es una implementación técnica de **Mantenimiento Predictivo (PdM)** utilizando Python. El objetivo principal es simular, procesar y diagnosticar fallas en equipos rotativos (como bombas, compresores o turbinas) mediante el **Análisis de Vibraciones**.

A diferencia del mantenimiento correctivo (esperar a que se rompa), este enfoque utiliza el procesamiento digital de señales (DSP) para identificar patrones de falla incipientes en el dominio de la frecuencia.

---

### 🏭 Contexto de Negocio: ¿Para qué sirve esto?
En industrias críticas como **Oil & Gas, Minería y Manufactura**, la parada no planificada de un motor puede costar miles de dólares por hora.

Este portafolio demuestra cómo utilizar herramientas de ciencia de datos para:
1.  **Digitalizar el diagnóstico:** Reemplazar la intuición por análisis espectral cuantificable.
2.  **Detectar fallas ocultas:** Identificar problemas como desalineación o desbalance que son invisibles al ojo humano o en la onda temporal cruda.
3.  **Automatizar la toma de decisiones:** Generar alertas basadas en la superación de umbrales en frecuencias específicas (1X, 2X, etc.).

---

### ⚙️ Flujo de Trabajo Técnico

El proyecto sigue el pipeline estándar de un analista de vibraciones CAT-II/III, pero implementado en código:

1.  **Adquisición/Simulación de Datos:**
    * Generación de señales sintéticas de vibración a 1800 RPM (30 Hz).
    * Inyección controlada de ruido y componentes armónicos para simular entornos industriales reales.

2.  **Procesamiento de Señal (DSP):**
    * Conversión del **Dominio del Tiempo** al **Dominio de la Frecuencia** utilizando la Transformada Rápida de Fourier (`numpy.fft.rfft`).
    * Normalización de amplitudes para obtener unidades físicas reales (g's, mm/s).

3.  **Diagnóstico Espectral:**
    * Detección automática de la velocidad de giro (RPM) mediante algoritmos de búsqueda de picos (`scipy.signal`).
    * Análisis de Tendencia: Comparación de una **Línea Base (Estado Saludable)** vs. **Condición Actual (Falla)**.

---

### 📊 Caso de Estudio y Resultados

Se simuló un escenario de falla compuesta en un motor de 4 polos.

#### 1. Señal en el Dominio del Tiempo
> *La onda cruda muestra un aumento de amplitud, pero es difícil distinguir la causa raíz debido al ruido.*
![Time Domain Signal](ruta/a/tu/imagen_tiempo.png)

#### 2. Diagnóstico FFT (Espectro de Frecuencia)
> *Al aplicar la FFT, la "firma" de la falla se vuelve evidente.*
![Frequency Spectrum](ruta/a/tu/imagen_fft.png)

**Conclusiones del Análisis:**
* **Pico 1X (30 Hz):** Aumento severo de amplitud. **Diagnóstico:** Desbalance del rotor.
* **Pico 2X (60 Hz):** Aparición de un nuevo pico armónico. **Diagnóstico:** Desalineación del acople.
* **Ausencia de 3X:** Se descarta holgura mecánica estructural.

---

### 💻 Stack Tecnológico

* **Lenguaje:** Python 3.x
* **Cálculo Numérico:** `NumPy` (Manejo de arrays y operaciones vectoriales).
* **Procesamiento de Señales:** `SciPy` (Detección de picos y filtrado).
* **Visualización:** `Matplotlib` (Gráficos de ingeniería y etiquetado de armónicos).

---

### 🚀 Cómo ejecutar este proyecto

1.  Clonar el repositorio.
2.  Instalar dependencias: `pip install numpy matplotlib scipy`
3.  Ejecutar el notebook principal: `Vibration_Analysis_FFT.ipynb`

---
*Autor: [Tu Nombre]*
*Enfoque: Data Science aplicado a Confiabilidad y Mantenimiento.*