🌍 Sistema de Gestión y Estadísticas de Países

Proyecto Integrador desarrollado para la Universidad Tecnológica Nacional (UTN). Se trata de una aplicación de consola (CLI) que permite administrar de forma eficiente los datos demográficos y geográficos de diferentes países, manejando registros de población, superficie y continente, utilizando persistencia de datos en archivos locales.

👨‍💻 Autor

Maximiliano Dacrema

---------------------------------------------------------------------------------------------

🚀 Características Principales

El sistema integra todas sus funcionalidades en un menú interactivo y amigable para el usuario:

🔄 Carga Automática: Lee el archivo CSV al iniciar y carga los datos en memoria. Cuenta con protección ante archivos inexistentes o formatos corruptos.

📖 Visualización Completa: Muestra el listado de todos los países cargados con sus respectivos habitantes, superficie y ubicación geográfica.

➕ Altas de Registros: Permite añadir nuevos países con validación estricta (evita campos vacíos y exige formatos numéricos correctos).

🔍 Búsqueda y Actualización: Localiza países mediante coincidencias parciales de nombre (case-insensitive) y permite modificar en caliente los valores de superficie y población.

🌍 Filtrado Geográfico: Agrupa y muestra en pantalla únicamente los países pertenecientes a un continente específico.

📊 Ordenamiento Eficiente: Ordena el listado de países de menor a mayor según su población utilizando un algoritmo propio.

📈 Estadísticas Generales: Calcula e informa automáticamente los países con mayor/menor cantidad de habitantes y los promedios globales.

💾 Persistencia Garantizada: Guarda los datos manual o automáticamente al salir, asegurando que no se pierda la información.

---------------------------------------------------------------------------------------------

🛠️ Aspectos Técnicos Destacados

Estructuras de Datos: Se implementó una lista de diccionarios para la base de datos en memoria, garantizando que la información de cada registro se mantenga unificada y estructurada.

Algoritmia Propia: Para el ordenamiento se desarrolló manualmente el método de la Burbuja (Bubble Sort), cumpliendo con los requerimientos académicos de no utilizar funciones nativas (.sort()).

Robustez y Control de Errores: Uso intensivo de bloques try-except para interceptar FileNotFoundError (archivos faltantes) o ValueError (datos numéricos corruptos/mal ingresados).

Seguridad de Datos: En los ordenamientos se emplea el método .copy() para operar sobre una réplica de la lista, evitando alterar el estado original de la base de datos a menos que el usuario lo guarde.

Cero Dependencias: Desarrollado 100% con bibliotecas estándar de Python.

---------------------------------------------------------------------------------------------

📂 Estructura del Proyecto

El código fuente está diseñado bajo un enfoque modular, separando la interfaz de la lógica de negocio:

📁 proyecto-paises/
├── 📄 main.py          # Bucle principal, interfaz de usuario (menú) y control de flujo.
├── 📄 funciones.py     # Lógica de negocio, CRUD, algoritmos y manejo de archivos.
├── 📁 img/             # Directorio con imágenes para la documentación.
└── 📁 datos/
    └── 📄 paises.csv   # Base de datos local (archivo de texto plano).

---------------------------------------------------------------------------------------------

💻 Instalación y Uso

Para ejecutar este proyecto en tu entorno local, solo necesitas tener instalado Python 3.x.

Clona este repositorio o descarga el código fuente:

git clone [https://github.com/tu-usuario/tu-repositorio.git](https://github.com/tu-usuario/tu-repositorio.git)


Navega al directorio del proyecto:

cd tu-repositorio


Asegúrate de mantener la carpeta datos y el archivo paises.csv en la misma ruta.

Ejecuta el archivo principal desde tu terminal:

python main.py

---------------------------------------------------------------------------------------------

📸 Ejemplos de Uso

A continuación se detalla el comportamiento del sistema para cada una de las opciones del menú principal. Al iniciar el programa, la consola recibe al usuario con el siguiente menú:

img/menu.png

La elección es: 


1️⃣ Mostrar países

Lista todos los registros cargados actualmente en memoria con un formato de fácil lectura.

=== PAÍSES ===
Argentina - 45808747 hab - 2780400 km² - america
Brasil - 214326223 hab - 8515767 km² - america
España - 47426683 hab - 505990 km² - europa
...


2️⃣ Agregar país

Guía al usuario paso a paso para añadir un nuevo registro. Cuenta con validación para evitar que ingreses letras en campos numéricos (como la población).

Nombre: Italia
Poblacion: 59000000
Superficie: 301340
Continente: europa
País agregado correctamente


3️⃣ Buscar y Actualizar país

Permite buscar un país ingresando solo una parte de su nombre. Si lo encuentra, ofrece la opción interactiva de modificar sus datos de población y superficie.

Ingresa el nombre del país que deseas buscar: Argen

Encontrado: Argentina - Población: 45808747 - Superficie: 2780400 - Continente: america
¿Deseas actualizar los datos de Argentina? (s/n): s
Nueva población (deja en blanco para mantener la actual): 46000000
Nueva superficie (deja en blanco para mantener la actual): 
Datos de Argentina actualizados correctamente.


4️⃣ Filtrar por continente

Muestra de forma exclusiva los países que pertenecen al continente tipeado por el usuario.

Ingresa el continente que deseas filtrar: europa

=== RESULTADOS ===
España - 47426683 - europa
Italia - 59000000 - europa
Francia - 67750000 - europa


5️⃣ Ordenar por población (Burbuja)

Implementación algorítmica propia que reordena temporalmente el listado mostrando primero los países con menor cantidad de habitantes y por último los más poblados.

=== ORDENADO POR POBLACIÓN ===
Uruguay - 3426260
Chile - 19493184
Argentina - 46000000
...


6️⃣ Estadísticas de población

Ejecuta cálculos en tiempo real sobre la base de datos entera, arrojando métricas de interés geográfico y demográfico.

ESTADÍSTICAS
País con mayor población: China (1412360000 hab)
País con menor población: Uruguay (3426260 hab)
Promedio de población global: 154238541.20 hab
Promedio de superficie global: 3120500.50 km²

Cantidad de países por continente:
 - america: 8 países
 - europa: 15 países
 - asia: 12 países


7️⃣ y 0️⃣ Guardar los cambios / Salir

El sistema permite un guardado manual de seguridad en el archivo paises.csv. Asimismo, si el usuario elige salir con el "0", el sistema guardará todo de forma automática para prevenir cualquier pérdida de datos accidental.

La elección es: 0
Datos guardados correctamente
Hasta luego. Gracias por utilizar esta biblioteca de países.
