# Modulo2-Actividad-didactica2-m3 - Simulación Estocástica y Análisis de Colas - Banco de Colombia

Este repositorio contiene la implementación de un modelo de Simulación de Eventos Discretos (DES) diseñado para evaluar y optimizar la arquitectura de servicio en una sucursal del Banco de Colombia. 

El proyecto analiza el flujo estocástico de usuarios (retiros y pagos) con múltiples perfiles de velocidad de atención. A través de la ejecución masiva de réplicas, se evalúa la eficiencia operativa de una **Fila Única Mixta** frente a modelos de **Cajas Especializadas**, demostrando matemáticamente y de forma empírica fenómenos críticos de encolamiento como el *Loss of Pooling* y los bloqueos *Head-of-Line*.

---

## 🚀 Ejecutar en la Nube (Google Colab)

Puedes interactuar con la simulación completa, visualizar las métricas de estado estacionario y generar las gráficas comparativas directamente desde tu navegador:

👉 **[Abrir Simulación en Google Colab](https://colab.research.google.com/drive/1bN8SjNywIDZAWFPQ8lyUW2ZZHSEZcYsj?usp=sharing)**

---

## 🛠️ Tecnologías y Librerías Utilizadas

El entorno de Google Colab ya incluye la mayoría de estas librerías por defecto. Para la ejecución de este modelo se utilizó:
* **SimPy:** Motor principal para la Simulación de Eventos Discretos (DES) y la gestión del reloj de simulación y contenedores (`simpy.Store`).
* **NumPy:** Para el modelado matemático del ruido estocástico, generando tiempos de llegada y servicio mediante distribuciones exponenciales.
* **Pandas:** Para la estructuración ágil de los logs de eventos, recolección de métricas y creación de las matrices de convergencia.
* **Matplotlib y Seaborn:** Para el renderizado de gráficos de balanceo de servidores, volumetría y degradación de los tiempos de espera.

---

## 📊 Componentes del Notebook
1. **Configuración del Sistema:** Parametrización de las probabilidades teóricas y medias de tiempo ($\lambda$ y $\mu$) para los distintos perfiles transaccionales.
2. **Definición de Arquitecturas:** Construcción orientada a objetos de los entornos de simulación, aislando el comportamiento de un Banco Mixto frente a variaciones de Bancos Especializados.
3. **Simulación a Gran Escala:** Ejecución automatizada de múltiples réplicas (jornadas de 8 horas) para asegurar la convergencia del Teorema del Límite Central y anular el sesgo de la varianza.
4. **Análisis de Capacidad:** Extracción de métricas de desempeño, cálculo del Factor de Utilización ($\rho$) y del Tiempo Promedio de Espera ($W_q$).
5. **Reporte y Visualización:** Renderizado dinámico de la comparativa de arquitecturas, justificando técnicamente el rechazo a la segmentación de canales.
