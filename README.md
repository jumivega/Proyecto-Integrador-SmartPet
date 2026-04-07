# 🐾 SmartPet: Edge AI para la Convivencia en Propiedad Horizontal

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python)
![YOLOv11](https://img.shields.io/badge/Model-YOLOv11_Nano-orange?style=flat-square)
![Google Colab](https://img.shields.io/badge/Environment-Google_Colab-F9AB00?style=flat-square&logo=googlecolab)
![Status](https://img.shields.io/badge/Status-PoC_en_Desarrollo-success?style=flat-square)
![Academic](https://img.shields.io/badge/Context-Tesis_de_Maestr%C3%ADa-8A2BE2?style=flat-square)

**Proyecto Integrador - Maestría en Inteligencia Artificial** **Universidad de Especialidades Espíritu Santo (UEES)** **Autores:** Oscar Mauricio Parra Folleco y Juan Miguel Velandia García  

---

## 📋 1. Descripción del Proyecto

**SmartPet** es una Prueba de Concepto (PoC) enfocada en aplicar el estado del arte en Visión por Computadora para resolver un problema crítico de convivencia en conjuntos residenciales de estratos 4,5 y 6 en Bogotá, Colombia: la disposición inadecuada de desechos de mascotas en áreas comunes.

El proyecto transforma la infraestructura pasiva de videovigilancia (CCTV) en un sistema activo, preventivo y autónomo. Mediante el despliegue de una arquitectura *Edge Computing* y el uso de técnicas de *Transfer Learning* sobre el modelo **YOLOv11n**, el sistema detecta de forma concurrente el comportamiento anómalo (postura de la mascota excretando heces), integrando lógica espacial heurística para disparar alertas vía mail a la administración para detonar las acciones pertinentes.

## 🏛 2. Arquitectura de la Solución

La solución se enmarca en un flujo de procesamiento optimizado para hardware de bajo costo, garantizando viabilidad operativa:

1. **Ingesta de Datos:** Extracción de fotogramas a baja latencia (1-5 FPS) desde CCTV en entornos interiores.
2. **Procesamiento (Edge AI):** Inferencia local utilizando YOLOv11 Nano, un modelo de una sola etapa optimizado para alta precisión y bajo consumo de recursos.
3. **Lógica de Decisión (Post-procesamiento):** Evaluación espacial (cálculo de centroides y *bounding boxes*) para verificar si el evento ocurre fuera de las zonas permitidas (ej. periódicos o tapetes absorbentes).
4. **Notificación:** Integración para el envío de notificaciones pedagógicas y preventivas al personal de administración.

## 📂 3. Estructura del Repositorio

El repositorio sigue las mejores prácticas de organización para proyectos de Ciencia de Datos y Machine Learning académico:

```text
📦 Proyecto-Integrador-SmartPet
 ┣ 📂 Datasets/           # Conjuntos de datos, imágenes y etiquetas para entrenamiento
 ┣ 📂 Documents/          # Entregables académicos y documentación formal
 ┃ ┣ 📂 Semana1/
 ┃ ┃ ┗ 📜 Rubrica Presentación Proyecto.pdf
 ┃ ┗ 📂 Semana2/
 ┃   ┣ 📜 Análisis Comparativo de Algoritmos para SmartPet 4abril2026_Vs2.pdf
 ┃   ┗ 📜 Análisis exploratorio de datos (EDA) 4abril2026_Vs2.pdf
 ┣ 📂 Notebooks/          # Código fuente, experimentación y pipelines en Colab
 ┃ ┣ 📜 EDA_Smartpet_V04abril2026 (1).ipynb
 ┃ ┗ 📜 SmartPetDetection_03Abril_DS_DogAndDogDef (2).ipynb
 ┗ 📜 README.md           # Documentación principal del proyecto

## 4. Tecnologías y Herramientas Utilizadas
Framework de IA: PyTorch / Ultralytics (YOLOv11n)

Gestión de Datos y Anotación: Roboflow Universe

Aumento de Datos con Roboflow Universe: Transformaciones morfológicas, escala de grises y desenfoque simulado para mitigación de overfitting y adaptación de dominio (Domain Shift).

Entorno de Entrenamiento: Google Colab (Aceleración GPU T4)

Almacenamiento de Datasets: Google Drive

## 5. Reproducibilidad y Ejecución
Para replicar los experimentos o ejecutar el modelo base, siga los siguientes pasos: 

	5.1. git clone [https://github.com/jumivega/Proyecto-Integrador-SmartPet.git](https://github.com/jumivega/Proyecto-Integrador-SmartPet.git)
cd Proyecto-Integrador-SmartPet

	5.2. Análisis Exploratorio de Datos (EDA):
Navegar a la carpeta /Notebooks y abrir EDA_Smartpet_V04abril2026 (1).ipynb para visualizar la distribución de clases y el balance del dataset.

	5.3. Entrenamiento (Google Colab):
Abrir SmartPetDetection_03Abril_DS_DogAndDogDef (2).ipynb. Ejecutar las celdas asegurando que el entorno tenga asignado un acelerador por hardware (GPU).

	5.4. Variables de Entorno (.env):
Para la futura ejecución del módulo de notificaciones, será necesario configurar las variables TELEGRAM_BOT_TOKEN y TELEGRAM_CHAT_ID. (Nota: Por políticas de seguridad, el archivo .env no se incluye en el control de versiones).

## 6. Consideraciones Éticas, Legales y Privacidad
El desarrollo de este algoritmo se adhiere estrictamente a la Ley 1581 de 2012 (Protección de Datos Personales en Colombia). El modelo de visión por computadora está entrenado exclusivamente para detectar la anatomía canina, la acción específica y el desecho. No incluye capacidades de reconocimiento facial humano, biometría ni trazabilidad de individuos, garantizando que el sistema opere como una herramienta pedagógica y no como un sistema de vigilancia invasiva.

## 7. Referencias Bibliográficas Destacadas
La documentación formal alojada en /Documents sigue el formato APA 7ma Edición. Las bases algorítmicas de este repositorio se fundamentan en:

Jocher, G., Chaurasia, A., & Qiu, J. (2023). YOLO by Ultralytics (Version 8.0.0) [Software]. Ultralytics.

Howard, A. G., et al. (2017). MobileNets: Efficient convolutional neural networks for mobile vision applications. arXiv preprint arXiv:1704.04861




