# Vision_Artificial_Deteccion_Clasificacion_Yolov5

Descripción del Proyecto
Este proyecto utiliza el modelo YOLOv5 preentrenado para realizar detección de objetos en un video. YOLOv5 es un modelo de vanguardia en la detección de objetos que permite identificar y localizar múltiples objetos en una imagen o video. En este ejemplo, el video se procesa frame por frame, y se detectan varios tipos de objetos, los cuales se etiquetan en español. Además, se crea un video de salida que incluye los cuadros delimitadores y las etiquetas para cada objeto detectado, así como un tablero de conteo de objetos visible en cada frame del video procesado.

Instalación
Para ejecutar este proyecto, es necesario instalar las siguientes dependencias:

bash
Copiar código
pip install opencv-python-headless
pip install yolov5
Uso
Carga del Modelo YOLOv5: El script utiliza la biblioteca torch para cargar el modelo YOLOv5 preentrenado. Este modelo es capaz de detectar múltiples objetos en un frame.

Carga y Procesamiento del Video: Se carga un video (video.mp4) utilizando OpenCV. El video se procesa frame por frame para detectar los objetos.

Detección y Conteo de Objetos:

Para cada frame, se realiza la detección de objetos utilizando YOLOv5.
Los objetos detectados se cuentan y se categorizan según el tipo: persona, gato, perro, auto, o "otros" si el objeto no pertenece a las categorías mencionadas.
Cada categoría tiene un color asignado para el cuadro delimitador y la etiqueta.
Generación del Video de Salida:

Se genera un nuevo video (output.mp4) que incluye los cuadros delimitadores y las etiquetas para cada objeto detectado.
Se agrega un tablero de conteo de objetos que se actualiza en tiempo real para cada frame.
Descarga del Video Procesado: Una vez finalizado el procesamiento, el video generado se puede descargar.

Ejecución
Para ejecutar el script, asegúrate de que tu entorno de desarrollo tiene acceso a un video llamado video.mp4 en la misma carpeta donde se encuentra el script.

python
Copiar código
!pip install opencv-python-headless
!pip install yolov5

import torch
import cv2
from google.colab.patches import cv2_imshow

# Cargar el modelo YOLOv5 pre-entrenado
model = torch.hub.load('ultralytics/yolov5', 'yolov5s')

# Asignar etiquetas en español
labels_es = {'person': 'persona', 'cat': 'gato', 'dog': 'perro', 'car': 'auto'}

# Cargar y procesar el video
# <código completo proporcionado arriba>
Este script es útil para quienes necesitan realizar detección de objetos en videos y crear salidas visuales con conteo en tiempo real. Es ideal para aplicaciones de vigilancia, análisis de tráfico, seguimiento de objetos en videos, entre otros.

Consideraciones
El script está diseñado para ejecutarse en Google Colab, donde puedes utilizar los recursos de GPU disponibles.
Asegúrate de adaptar las etiquetas y colores a tus necesidades específicas si trabajas con diferentes tipos de objetos.
