¿Qué ventaja tiene registrar las dependencias del proyecto en requirements.txt en lugar de compartir la carpeta .venv? 
R: Registrar las dependencias en requirements.txt en lugar de compartir la carpeta .venv es mucho más práctico porque el archivo es ligero (unos KB vs cientos de MB), funciona en cualquier sistema operativo, y le permite a cualquier persona recrear el mismo entorno con pip install -r requirements.txt, mientras que .venv está atado a la máquina donde se creó y normalmente ni siquiera funciona si lo mueves a otra computadora. 

Pregunta (Sección 12): ¿Por qué el repositorio que tienes ahora en tu computadora no es el mismo concepto que el fork creado en GitHub?

Respuesta: El fork es una copia remota hospedada en los servidores de GitHub vinculada a tu cuenta personal, mientras que el repositorio local es el conjunto de archivos y el historial de Git descargados directamente en el almacenamiento de tu computadora física. El fork sirve como puente de sincronización en la nube para proponer cambios (Pull Request), mientras que la copia local es el entorno donde realmente se edita y ejecuta el código.
# Fabricio
# Respuestas a las Preguntas Individuales

### 79. ¿Cómo identificaste el comando necesario cuando la práctica no lo proporcionó?
Se identificó analizando el objetivo de cada acción descrita en las instrucciones[cite: 1] y consultando la documentación oficial de Git/Python, las guías integradas en la terminal (`git --help`, `python --help`) o la autocomprobación del estado del repositorio[cite: 1].

### 80. ¿Qué diferencia existe entre preparar un archivo para un commit y crear el commit?
Preparar un archivo (`git add`) lo coloca en el área de preparación (*staging area*), seleccionando cuáles cambios formarán parte del siguiente registro[cite: 1]. Crear el commit (`git commit`) confirma esa selección y guarda una captura permanente del estado de esos archivos en el historial de Git[cite: 1].

### 81. ¿Cómo puedes comprobar en qué rama estás trabajando?
Se puede comprobar ejecutando el comando `git branch` (la rama activa aparecerá destacada con un asterisco) o revisando el encabezado que muestra `git status`[cite: 1].

### 82. ¿Cómo puedes determinar qué archivos fueron modificados antes de registrarlos?
Utilizando el comando `git status`, el cual despliega el listado de archivos que han sufrido modificaciones, eliminaciones o que aún no están rastreados por Git (*untracked*)[cite: 1].

### 83. ¿Cómo puedes observar exactamente qué cambió dentro de un archivo?
Mediante el comando `git diff`, el cual muestra en detalle las líneas agregadas o eliminadas línea por línea en los archivos modificados[cite: 1].

### 84. ¿Por qué debe reconstruirse .venv después de obtener un repositorio?
Porque la carpeta `.venv` no se sube al repositorio al estar excluida por el `.gitignore`[cite: 1]. Además, contiene binarios y rutas absolutas vinculadas al sistema operativo del desarrollador original[cite: 1], por lo que cada colaborador debe generarlo localmente[cite: 1].

### 85. ¿Qué relación existe entre requirements.txt y .gitignore?
El archivo `.gitignore` indica a Git que no debe rastrear la carpeta `.venv` para no saturar el repositorio con archivos pesados e innecesarios[cite: 1]. A su vez, `requirements.txt` reemplaza esa carpeta compartiendo únicamente la lista ligera de librerías para que cualquier desarrollador pueda instalar exactamente las mismas dependencias[cite: 1].

### 86. ¿Por qué la colaboración se realiza desde una rama y no directamente desde main?
Para proteger la estabilidad del código principal (`main`), trabajar en un entorno aislado sin interferir con el código de otros colaboradores y permitir una revisión previa mediante Pull Request antes de integrar los cambios[cite: 1].

### 87. ¿Por qué una solicitud de cambios no requiere crear un Pull Request nuevo?
Porque un Pull Request vincula dos ramas completas y no un commit individual[cite: 1]. Cuando se envían nuevos cambios (`git push`) a la misma rama de origen, el Pull Request abierto en GitHub se actualiza automáticamente incorporando los nuevos commits[cite: 1].

### 88. Después de realizar el merge en GitHub, ¿por qué todavía es necesario actualizar el repositorio local?
Porque la fusión (*merge*) ocurre únicamente en los servidores remotos de GitHub[cite: 1]. Para tener la versión más reciente en la máquina local, es obligatorio descargar y fusionar esos cambios mediante un `git pull`[cite: 1].