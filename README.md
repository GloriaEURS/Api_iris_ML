# Api_iris_ML
Esta actividad es una implementación de una API REST construida con Python, Flask y un modelo de Machine Learning entrenado con el famoso dataset de Iris. La API permite realizar predicciones de la especie de flor en función de las características de entrada (longitud y ancho del sépalo y del pétalo).

Vamos a implmentarlo y ejecutarlo usando Docker, lo que permite una fácil portabilidad y ejecución del entorno completo.

# Tecnologias a usar: 
  * Python 3, Flask, scikit-learn, Pandas / NumPy, Docker.

# Estrucutra del repositorio
¿Qué contiene cada archivo o carpeta del proyecto?

`Api_iris_ML/
├── app.py                 # Código principal de la API con Flask
├── iris_models.py         # Script con funciones para cargar y usar modelos
├── Dockerfile             # Instrucciones para construir la imagen Docker
├── docker-compose.yml     # Ejecutar con un solo comando usando Docker Compose
├── requirements.txt       # Librerías necesarias para ejecutar el proyecto
├── README.md              # Esta guía :)
└── models/                # Carpeta con los modelos entrenados
    ├── model_forest.h5    # Modelo de Random Forest
    ├── model_logistic.h5  # Modelo de Regresión Logística
    ├── model_svm.h5       # Modelo de Máquina de Vectores de Soporte
    ├── model_tree.h5      # Modelo de Árbol de Decisión
    └── requirements.txt   # Requisitos específicos para los modelos (opcional)
`

# ¿Qué hace esta API?
Recibe como entrada las siguientes características de una flor:
  * sepal_length (longitud del sépalo)
  * sepal_width (ancho del sépalo)
  * petal_length (longitud del pétalo)
  * petal_width (ancho del pétalo)

Y retorna la especie predicha (setosa, versicolor, o virginica) gracias a un modelo de Machine Learning entrenado con `scikit-learn`.

# ¿Cómo ejecutar la API con Docker?
1. Clonar este repositorio, descargando todos los archivos en tu computadora almacenandolos en una carpeta que identifiques, por ejemlo "machine__learning_api".

2. Si quieres generar diferentes parámetros puedes entrenar y guardar los modelos (una vez):
   * En el archivo "iris_models.py" se entrenan los modelos y se guardan en la carpeta "models".
   * Abre tu consola y ejecuta "python iris_models.py
   * El resultado debe ser algo como "`Accuracy logistic regression: 0.97, Accuracy SVM: 1.00 ...`

4. Vamos a crear la API con Flask 
  * Aqui revisaremos el archivo "app.py" que implementa los endpoints que cargan los modelos y hacen predicciones.
  * Abriendo tu consola ejecuta "`python app.py`" para probarlo localmente.
  * El resultado debe ser " `* Running on http://127.0.0.1:5001/ ...`" algo así.
  * Abre el navegador copiando o accediendo a la url directamente en la consola para comprobar que la API está en línea.

5. Ahora probaremos la API con Postman
  * Descarga Postman en tu computadora: https://www.postman.com/downloads/
  * Una vez instalado Postamn podras pedir peticiones con el indicador "POST" ya que estamos enviando una "carga útil" (payload) con los 4 valores de iris.
  * Una vez seleccionado lo anterior, podremos hacer peticiones a las rutas como "/predict/logistic", "/predict/randomforest", "/predict/svm" o "/predict/randomforest".

  * Ejemplo de JSON:
`    {
  "sepal_length": 5.1,
  "sepal_width": 3.5,
  "petal_length": 1.4,
  "petal_width": 0.2
}`

# API en Docker
6. Descargar Dovcker Desktop:
  * Windows/macOS: https://www.docker.com/products/docker-desktop/
  * Linux: https://docs.docker.com/engine/install/
Una vez instalado, asegurate de que esté corriendo.

7. Ejecuta de nuevo la API
  * Abre tu consola y ejecuta: `docker-compose up --build`
    para construir y ejecutar con docker (recuerda estar dentro de la carpeta base) 

8. Te va a ejecutar varias lineas, en las finales sule aparecer las url de la API que puedes copiar o acceder directamente desde la consola. 

¡Lo lograste! :D
