# U2-Examen-Monitoreo del Estado de Ánimo

## Universidad Politécnica De Victoria
⮕ **Ingeniería en Tecnologías de la Información**  
⮕ **Materia¨**: Desarrollo de Aplicaciones Móviles  
⮕ **Asesor**: Ing. Luis Antonio González Castro
⮕ **Periodo**: Agosto – Diciembre 2025
⮕ Ciudad Victoria, Tamaulipas

## Integrantes:
```plaintext
- **Marcos García Vázquez**  
- **Jorge Luis Gerónimo Osorio**  
- **Ingrid Yamilee Ortega Castillo**  
```
---

## Descripción del Proyecto

Este examen tiene como objetivo desarrollar una aplicación móvil para el monitoreo del estado de ánimo. La aplicación permite a los usuarios calificar su estado de ánimo, registrar actividades y eventos, y generar análisis gráficos sobre los patrones de su estado emocional.

**Características:**
- Calificación del estado de ánimo diario.
- Registro de actividades, lugares y eventos que influyen en el ánimo.
- Gráficas interactivas de distribución del estado de ánimo.
- Notificaciones si no se registra el estado de ánimo en más de 18 horas.

---

### Aplicación Real

Este proyecto es útil para:
- Aplicaciones de bienestar emocional.
- Análisis de patrones de ánimo a largo plazo.
- Gestión de actividades que afectan el estado emocional.

## Explicación del Código

### `MainActivity.java` (Con ViewPager)

La actividad principal de la aplicación usa un **ViewPager2** para gestionar la navegación entre las dos pestañas: **Registrar** y **Análisis**. Esto permite a los usuarios navegar entre estas secciones de la aplicación sin necesidad de recargar la actividad. Cada pestaña está asociada a una clase y a una interfaz de usuario (UI) específica.

- **`ViewPager2`**: Un contenedor que permite la navegación entre fragmentos o actividades. En este caso, se utiliza para mostrar las secciones de "Registrar" y "Análisis".
- **`FragmentStateAdapter`**: Un adaptador que maneja los fragmentos dentro del `ViewPager2`. En este caso, gestiona los fragmentos correspondientes a las pestañas "Registrar" y "Análisis".

### `RegistrarActivity.java`
Permite al usuario calificar su estado de ánimo y registrar eventos o actividades que puedan influir en él.  
- Utiliza campos de entrada para los datos del usuario y los guarda en la base de datos.

### `AnalisisActivity.java`
Muestra gráficas interactivas basadas en los registros de estado de ánimo del usuario.  
- Utiliza **MPAndroidChart** para visualizar los datos en forma de gráficas de barras y de pastel.

### `Mood.java`
Clase modelo para representar un registro de estado de ánimo.  
- Contiene campos como fecha, estado de ánimo, actividad, y eventos.

### `MoodDbHelper.java`
Clase que maneja las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en la base de datos SQLite.

### `MoodNotification.java`
Clase encargada de gestionar las notificaciones que se envían al usuario si no ha registrado su estado de ánimo en más de 18 horas. La notificación recuerda al usuario que debe ingresar su estado para el día.

- **Método `showNotification()`**: Crea y muestra una notificación utilizando el sistema de notificaciones de Android.
- Utiliza `NotificationManager` para crear y mostrar la notificación en la barra de estado.
- Funciona con una notificación que contiene el mensaje: "¡Recuerda registrar tu estado de ánimo!".
- La notificación es disparada si el usuario no realiza un registro en el tiempo estimado.

---

## Estructuras de Datos Utilizadas

- `ArrayList` para almacenar los registros de estado de ánimo.
- `SQLiteDatabase` para la persistencia de los datos.
- `BarChart` y `PieChart` de MPAndroidChart para las visualizaciones gráficas.

---

## Librerías Usadas

- **MPAndroidChart**: Para la visualización de gráficos de barras y pastel.
- **SQLite**: Para la base de datos local donde se almacenan los registros de estado de ánimo.
- **Android SDK**: Para la creación de la interfaz y funcionalidades móviles.

---

##  Ejecución del Programa

### Requisitos

- Android Studio 4.0 o superior
- Dispositivo Android con Android 7.0 (API 24) o superior.

### ⚙️ Pasos para compilar y ejecutar

```bash
# 1. Clonar el repositorio
git clone https://github.com/usuario/monitoreo-estado-animo.git
cd monitoreo-estado-animo

# 2. Abrir el proyecto en Android Studio

# 3. Compilar y ejecutar el proyecto en un dispositivo o emulador Android

```
## Estructura del Proyecto
```plaintext
U2-Examen-Monitoreo-Estado-Animo/
├── README.md                  # Documentación del proyecto (este archivo)
├── app/                        # Código fuente de la aplicación Android
│   ├── MainActivity.java       # Actividad principal con la navegación
│   ├── RegisterFragment.java  # Fragmento para registrar el estado de ánimo
│   ├── AnalysisFragment.java  # Fragmento para mostrar el análisis gráfico
│   ├── MoodEntry.java         # Clase modelo para los registros de estado de ánimo
│   ├── DatabaseHelper.java    # Clase para manejar la base de datos
│   ├── NotificationReceiver.java # Clase para gestionar las notificaciones
│   └── ViewPagerAdapter.java  # Adaptador para la navegación entre fragmentos
├── res/                        # Recursos de la aplicación
│   ├── drawable/               # Archivos gráficos como imágenes o íconos
│   ├── layout/                 # Archivos XML para las vistas de la aplicación
│   │   ├── activity_main.xml   # Layout para la actividad principal
│   │   ├── fragment_analysis.xml # Layout para el fragmento de análisis
│   │   └── fragment_register.xml # Layout para el fragmento de registro
│   ├── mipmap/                 # Iconos de la aplicación
│   └── values/                 # Archivos de recursos como colores, dimensiones, cadenas de texto, etc.
├── Gradle Scripts/             # Archivos de configuración para construir el proyecto
│   ├── build.gradle.kts        # Configuración del proyecto y del módulo de la aplicación
│   ├── proguard-rules.pro      # Reglas de ProGuard para la optimización del código
│   └── Otros archivos de propiedades relacionados con la configuración de Gradle
├── .gitignore                 # Archivos ignorados por Git
├── LICENSE                    # Licencia del proyecto
└── resources/                 # Recursos estáticos (imágenes, íconos, etc.)
    └── logo.png               # Ejemplo de imagen
```
