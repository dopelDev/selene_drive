### Selene Drive project 

**Descripción**:
Selene Drive project es una solución avanzada para el procesamiento de videos, enfocada en la utilización de algoritmos innovadores para la fragmentación de video. El objetivo principal del proyecto es explorar y aplicar técnicas eficientes para dividir videos en fragmentos, facilitando su distribución y transmisión. La fragmentación en segmentos de 10 segundos es solo un enfoque inicial que puede ser ajustado según las necesidades del usuario.

### Características Principales

1. **Fragmentación de Videos (Chunks)**
   - **Propósito**: Implementar un algoritmo avanzado para dividir videos en fragmentos de tamaño óptimo, mejorando la eficiencia en la transmisión y distribución.
   - **Entrada**: Soporte para múltiples formatos de video (MP4, AVI, MKV).
   - **Herramienta**: Utilización de FFmpeg para la división inicial en fragmentos de 10 segundos.
   - **Salida**: Fragmentos generados en formato DASH, listos para su posterior procesamiento y transmisión.
   - **Flexibilidad**: La longitud de los fragmentos puede ser ajustada según los requerimientos específicos del proyecto, permitiendo optimizaciones basadas en el contenido del video y las condiciones de la red.

2. **Transcodificación para Streaming**
   - **Propósito**: Facilitar la transmisión adaptativa de video mediante la transcodificación en DASH (Dynamic Adaptive Streaming over HTTP) que es un FOSS.
   - **Procesos Involucrados**: 
     - Generación de manifiestos y listas de reproducción necesarias para la transmisión adaptativa.
     - La creacion y manejo de metadatos de los Chunks de Videos.
     - Servir los endpoints para Manifiesto DASH y la lista de los Chunks con sus metadatos.
   - **Beneficios**: Garantiza una experiencia de visualización fluida y de alta calidad, adaptándose dinámicamente a las condiciones de la red del usuario.

3. **Backend en Rust**
   - **Frameworks Utilizados**: Actix Web para la creación de la API RESTful y Diesel para la gestión de la base de datos (PostgreSQL).
   - **Funciones Clave**:
     - **Creación y Gestión de Fragmentos**: Control sobre el proceso de fragmentación con el uso FFmpeg y almacenamiento de los metadatos correspondientes.
     - **API RESTful**: Proporciona endpoints para subir videos, acceder a fragmentos, y obtener logs de procesamiento en formato JSON.
   - **Seguridad y Escalabilidad**: Rust garantiza un rendimiento óptimo y seguridad en el manejo de memoria, cruciales para aplicaciones de procesamiento intensivo.

4. **Procesamiento en Paralelo**
   - **Tecnologías**: Uso de Tokio y Rayon para implementar procesamiento concurrente y paralelo.
   - **Ventajas**: Aumenta la eficiencia y reduce los tiempos de procesamiento, permitiendo manejar múltiples videos y tareas simultáneamente.

5. **Logging y Análisis**
   - **Propósito**: Proporcionar visibilidad y monitoreo del proceso de fragmentación y transcodificación.
   - **Servidor de Logging**: Implementado en Rust, los logs se almacenan y distribuyen mediante la API RESTful.
   - **Formato de Logs**: JSON, facilitando su análisis y procesamiento posterior.

