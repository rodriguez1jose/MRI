# MRI
Codigo de la pagina de MRI - Imagenologia
Simulador de Resonancia Magnética (MRI) - Libro Electrónico Interactivo
Descripción
Esta aplicación educativa está diseñada para estudiantes y profesionales de Ingeniería Biomédica que desean comprender los fundamentos de la Resonancia Magnética (MRI). Combina un libro electrónico interactivo con explicaciones visuales, un simulador biomédico en tiempo real para experimentar con parámetros de MRI, actividades y cuestionarios generados por IA (Gemini) para reforzar el aprendizaje, y un sistema de subida de tareas para entornos educativos.

Características principales
Libro Electrónico: Páginas educativas sobre Física de MRI, Relajación T1/T2, Contraste, Espacio-k y Secuencias de Pulso.

Simulador: Ajusta parámetros como TR, TE, Flip Angle, filtros y observa el efecto en señales y reconstrucción de imágenes.

Actividades: Genera preguntas de opción múltiple con IA (Gemini) y guarda los resultados.

Tareas: Permite a los estudiantes subir archivos de tareas (PDF, Word, imágenes) que se guardan localmente.

Requisitos previos
- Python 3.9 o superior
- Pip (gestor de paquetes de Python)
- Conexión a Internet (para la generación de preguntas con Gemini)

Crear un entorno virtual (recomendado)en Windows
Comandos: 
1. python -m venv venv
2. venv\Scripts\activate
3. pip install dash plotly numpy scipy scikit-image google-generativeai


Configura tu API KEY
Para usar la generación de preguntas con IA, necesitas una API Key de Google Gemini:
Ve a Google AI Studio (https://aistudio.google.com/)
Inicia sesión con tu cuenta de Google
Haz clic en "Get API key"
Crea una nueva clave y cópiala
En el archivo appSimuMRI.py, reemplaza:

GEMINI_API_KEY = "Aqui ponen el APY KEY de su cuenta"
Nota: Si no tienes API key, la aplicación usará un banco de preguntas predefinido.


ESTRUCUTRA/ARQUITECTURA NECESARIA
SimuMRI/ #carpeta general
├── appSimu3.py                  # Código principal de la aplicación
├── assets/                      # Archivos estáticos (imágenes, videos)
│   ├── mri.png                  # Imagen del escáner
│   ├── espines.png              # Imagen de espines
│   ├── dLarmor.png              # Diagrama de Larmor
│   ├── contraste.png            # Comparativa de contrastes
│   ├── kspace.png               # Trayectorias de espacio-k
│   ├── kspaceMRI.png            # Parámetros físicos desde espacio-k
│   ├── secuencia.png            # Diagrama de secuencia PRESS
│   └── MRI.mp4                  # Video explicativo de bobinas
├── tareas_subidas/              # Carpeta donde se guardan las tareas subidas
├── resultados_estudiantes.csv   # Registro de resultados de actividades
└── tareas_estudiantes.txt       # Registro de tareas enviadas
├── archive/ #dataset del MRI

LINK DE DESCARGA PARA EL DATASET
https://drive.google.com/file/d/1zZU-pbUkpqfbOPCdbCfb_sC6Dm6GBebs/view?usp=sharing

Ejecutar la aplicación con el siguiente comando:
python appSimuMRI.py

Luego abre tu navegador y ve a: http://127.0.0.1:8050

Usando Cloudflare Tunnel (para compartir en línea)
cloudflared tunnel --url http://localhost:8050

Cómo usar la aplicación
Navegación
Inicio: Presentación general y acceso a todas las secciones.
Fisica de la MRI: Espin, campo B0, frecuencia de Larmor y precesion.
Senal y Relajacion: Procesos T1 y T2, FID y curvas de relajacion.
Contraste en MRI: Ponderaciones T1, T2 y Densidad Protonica (PD).
Espacio-k: Centro vs. Periferia, trayectorias de adquisicion.
Secuencias de Pulso: Spin-Echo, PRESS y linea de tiempo.
Simulacion: Ajusta parametros en tiempo real y observa los cambios en las senales.
Actividades: Genera preguntas, responde y obtén tu calificación.

Simulacion
En la pestaña "Simulacion" puedes:
Seleccionar una patologia y un paciente del dataset.
Ajustar parametros como:
Ponderacion (T1, T2, PD)
Filtrado del espacio-k (Centro, Periferia, Completo)
Factor de aceleracion R (1, 2, 4)
Ruido termico y filtros espaciales
Ver los resultados en tiempo real en los graficos de pipeline.


Actividades
Ingresa tu nombre y correo.
Haz clic en "Generar Nuevas Preguntas".
Selecciona una opcion para cada pregunta.
Haz clic en "Verificar Respuestas" para ver tu calificacion.
Usa "Enviar Resultados" para guardar tu puntaje.
