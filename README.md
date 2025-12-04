# Sistema de Búsqueda y Resumen de Documentos

Un sistema para cargar documentos (PDF, DOCX, TXT), buscar información específica y generar resúmenes automáticos utilizando **LangChain**, **NLP**, **FAISS** y modelos de **Hugging Face**.

---

## **Características**
- Carga documentos en formatos PDF, DOCX y TXT.
- Indexación de documentos para búsquedas rápidas.
- Búsqueda de información por palabras clave.
- Generación de resúmenes automáticos.
- Interfaz gráfica con **Gradio** para facilitar la interacción.

---

## **Tecnologías y Características Principales**
1. FAISS (Facebook AI Similarity Search)
¿Qué es?
FAISS es una biblioteca para realizar búsquedas eficientes de similitud en grandes conjuntos de datos vectoriales. Es especialmente útil para tareas de recuperación de información, donde se necesita encontrar los elementos más similares a una consulta en un espacio de alta dimensión.
Características clave:

Búsqueda por similitud: Encuentra los vectores más cercanos a un vector de consulta.
Optimización para grandes conjuntos de datos: Utiliza técnicas como cuantización y clustering para acelerar las búsquedas.
Soporte para GPU y CPU: Puede ejecutarse en hardware estándar o acelerarse con GPU.
¿Por qué se usa en el proyecto?

Permite buscar información relevante en los documentos de manera eficiente.
Los embeddings generados por sentence-transformers se indexan en FAISS para realizar búsquedas semánticas.

2. Hugging Face
¿Qué es?
Hugging Face es una plataforma y biblioteca que proporciona miles de modelos preentrenados para tareas de NLP. También ofrece herramientas para entrenar, evaluar e implementar modelos de lenguaje.
Características clave:

Modelos preentrenados: Acceso a modelos estado-del-arte para diversas tareas de NLP.
Pipelines: Interfaz sencilla para utilizar modelos sin necesidad de escribir código complejo.
Integración con otras bibliotecas: Funciona bien con transformers, sentence-transformers, y langchain.
¿Por qué se usa en el proyecto?

Proporciona el modelo facebook/bart-large-cnn para generar resúmenes.
Facilita el uso de modelos de embeddings como all-mpnet-base-v2.

3. Gradio
¿Qué es?
Gradio es una biblioteca para crear interfaces de usuario interactivas en Python. Es especialmente útil para demostrar modelos de machine learning y compartir aplicaciones con otros.
Características clave:

Interfaz sencilla: Permite crear interfaces con solo unas pocas líneas de código.
Soporte para múltiples tipos de entrada/salida: Texto, imágenes, archivos, audio, etc.
Compartir aplicaciones: Genera enlaces públicos para compartir la aplicación.
¿Por qué se usa en el proyecto?

Proporciona una interfaz amigable para que los usuarios suban documentos y realicen consultas sin necesidad de interactuar con el código directamente.

## **Uso de Modelos de Lenguaje (LLMs) y Procesamiento de Lenguaje Natural (NLP)**
1. Modelos de Lenguaje (LLMs)
En este proyecto, los LLMs se utilizan principalmente para generar resúmenes. El modelo facebook/bart-large-cnn es un ejemplo de LLM especializado en esta tarea.
¿Qué es un LLM?
Un LLM (Large Language Model) es un modelo de lenguaje entrenado con grandes cantidades de texto. Estos modelos son capaces de entender y generar texto coherente y contextualmente relevante.
¿Cómo se usan en el proyecto?

Generación de resúmenes: El modelo BART toma un fragmento de texto y genera un resumen que captura las ideas principales.
Comprensión del contexto: BART entiende la estructura y el significado del texto, lo que le permite generar resúmenes precisos.

2. Procesamiento de Lenguaje Natural (NLP)
El NLP es una rama de la inteligencia artificial que se enfoca en la interacción entre computadoras y el lenguaje humano. En este proyecto, el NLP se utiliza en varias etapas:
a) Generación de Embeddings:

Los modelos de sentence-transformers convierten el texto en vectores que capturan su significado semántico. Esto es esencial para la búsqueda de información relevante.
b) Búsqueda Semántica:

FAISS utiliza los embeddings para encontrar fragmentos de texto que son semánticamente similares a la consulta, incluso si no comparten palabras clave exactas.
c) Generación de Texto:

El modelo BART utiliza técnicas de NLP avanzadas para generar resúmenes coherentes y relevantes.

## **Conclusión**
Este proyecto integra varias bibliotecas y tecnologías de vanguardia para crear un sistema potente de búsqueda y resumen de documentos. Aquí hay un resumen de lo que hace cada parte:

LangChain: Facilita la carga y procesamiento de documentos.
FAISS: Permite realizar búsquedas semánticas eficientes.
Hugging Face: Proporciona modelos preentrenados para generar embeddings y resúmenes.
Gradio: Ofrece una interfaz de usuario amigable.
LLMs y NLP: Habilitan la comprensión del lenguaje y la generación de texto coherente.

