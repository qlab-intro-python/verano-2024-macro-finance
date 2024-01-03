# GitHub & Python
*   Instructor: Victor Fuentes Campos
*   Curso: Fundamentos de Programación en Python para Macroeconomía y Finanzas
*   Basado en las notas ["Getting started with GitHub"](https://dimewiki.worldbank.org/Getting_started_with_GitHub) del World Bank - DIME Analytics, ["Hello World"](https://docs.github.com/es/get-started/quickstart/hello-world) de GitHub, 
las clases previas de Carla Solís y Alexander Quispe.

## A. GitHub

### **Antes de empezar**
1. ¿Ya tienes una cuenta de GitHub? De no ser así, creálo ahora https://github.com/join. Ojo: al usar un correo de educación (@pucp), puedes acceder a una [cuenta GitHub Pro](https://education.github.com/students)
2. Añade tu usuario de GitHub al [archivo Excel compartido](https://docs.google.com/spreadsheets/d/13o35bMhi06RmSUP-nJ8mqBaJiKlQN-ngJspjB1lLp-E/edit?usp=sharing) (usa tu cuenta @pucp)
3. ¿Ya instalaste GitHub Desktop? De no ser así, descárgalo de https://desktop.github.com/ e instálalo
4. ¿Ya iniciaste sesión en GitHub Desktop? De no ser así, inicia sesión con tu cuenta creada
5. ¿Ya abriste el repo del curso https://github.com/qlab-intro-python/verano-2024-macro-finance?
6. ¿Ya tienes un editor de texto instalado? En mi caso uso [Visual Studio Code](https://code.visualstudio.com/), pero también está [Sublime](https://www.sublimetext.com/) y [Jupyter](https://jupyter.org/)

### **El problema**
<div> <img src="https://pbs.twimg.com/media/EiG-dwJVkAA-J0L?format=jpg&name=medium" width="300"/> </div>

- Múltiples versiones: *final*, *vf*, *este sí*, *finalfinal*, *para imprimir*
- ¿Cómo aplicamos el "control de cambios"? ¿O el historial de cambios?
- ¿Y si el trabajo fuera colaborativo (ie., Dropbox, Drive, OneDrive)?

### **Solución: Git & GitHub**

- Git: **Sistema de control de versiones** de código abierto creado en el año 2005 por Linus Torvalds (Linux), que puede gestionar el historial de código fuente de un proyecto de desarrollo. Beneficios:

  - Historial completo de cambios de cada archivo
  - Trabajo colaborativo: cualquiera puede editar y acceder a versiones anteriores y/o recientes
  - Documentación excelente de las versiones de tu proyecto
  - Rastreo de cada cambio realizado y el responsable

- GitHub: **Plataforma de alojamiento** de código para el control de versiones y la colaboración. Este permite que tú y otras personas trabajen juntos en proyectos desde donde sea. Beneficios:

  - Proyectos son visibles en Internet y se pueden compartir fácilmente
  - Seguimiento sencillo del desarrollo de cualquier proyecto
  - Todos los archivos del proyecto están en la nube. Todo estará bien.


### **Conceptos clave**

- Repo: Es más fácil imaginarlos como una carpeta del proyecto. Contiene todos los archivos del proyecto (incluida la documentación) y almacena el historial de revisión de cada archivo. Los repositorios pueden contar con múltiples colaboradores y pueden ser tanto públicos como privados

- Clone: Copia local de un repositorio que se encuentra en la nube. Al realiza un clon, puede editar los archivos y usar Git para realizar el seguimiento de los cambios sin necesidad de estar en línea. El repositorio que ha clonado sigue conectado a la versión remota para que pueda insertar los cambios locales en el repositorio remoto para mantenerlos sincronizados cuando esté en línea

- Branch: Una rama es una versión paralela de un repositorio. Se incluye en el repositorio, pero no afecta a la rama principal, lo que te permite trabajar libremente sin interrumpir la versión "activa". Una vez que haya realizado los cambios deseados, puede volver a combinar (merge) la rama en la rama principal para publicarlos

- Commit: Una confirmación (o "revisión") es una modificación individual de un archivo (o de un conjunto de archivos). Al realizar una confirmación para guardar el trabajo, Git crea un identificador único (también conocido como "SHA" o "hash") que le permite mantener el registro de los cambios específicos confirmados junto con quién los ha realizado y cuándo

- Pull request: Solicitudes de incorporación de cambios propuestas para un repositorio enviadas por un usuario y que los colaboradores del repositorio aceptan o rechazan. Las solicitudes de incorporación de cambios tienen su propio foro de debate

Adaptado del [glosario de GitHub](https://docs.github.com/en/get-started/quickstart/github-glossary)


### **Ejercicios de juguete**

#### **1. Crear un repo**

>  Un repo sirve para organizar un solo proyecto y pueden contener carpetas y archivos, imágenes, videos, hojas de cálculo, conjuntos de datos, etc. 

1. En la esquina superior derecha de cualquier página, haz clic en Nuevo repositorio. <div> <img src="https://docs.github.com/assets/cb-34248/mw-1440/images/help/repository/repo-create-global-nav-update.webp" width="300"/> </div>

1. En el cuadro "Nombre del repositorio", escriba `hello-world`

1. En el cuadro "Descripción", escriba una breve descripción

1. Seleccione si el repositorio será Público o Privado

1. Seleccione Agregar un archivo README<sup>[[1]](#myfootnote1)</sup>

1. Haga clic en `Create repository`

<a name="myfootnote1">[1]</a> Los archivos README se escriben en el lenguaje Markdown de texto sin formato. Para mayor información sobre la sintaxis de Markdown usa esta [hoja de referencia rápida](https://www.markdownguide.org/cheat-sheet/).

#### **2. Crear un branch**

>  Un branch permite tener una versión diferente de un proyecto en algún momento específico. Es útil cuando quieres jugar/probar/agregar características nuevas a un proyecto sin cambiar la fuente de código principal

Al crear un branch a partir del `main` branch, se realiza una copia, o instantánea, de `main` como estaba en ese momento en el tiempo.

En este diagrama se muestra:

- La rama `main`
- Una nueva rama denominada `feature`
- El recorrido que realiza `feature` antes de combinarse en `main`

<div> <img src="https://docs.github.com/assets/cb-23923/mw-1440/images/help/repository/branching.webp" width="500"/> </div>

Diagrama de las dos ramas. La rama "`feature`" se diferencia de la rama "`main`", pasa por fases para "Confirmar cambios", "Enviar solicitud de cambios" y "Analizar los cambios propuestos" y, a continuación, se combina de nuevo en "`main`".

¿Alguna vez has guardado versiones distintas de un archivo? Algo como:

- `tesis.docx`
- `tesis_vf.docx`
- `tesis_final.docx`

Los branches logran objetivos similares en los repositorios de GitHub.

En GitHub, nuestros desarrolladores, escritores y diseñadores utilizan ramas para mantener las correcciones de errores y el trabajo de las características separados de nuestra rama main (de producción). Cuando un cambio está listo, combinan su rama en main.

##### Crear un branch

1. Haga clic en la pestaña Código del repositorio `hello-world`.

1. Encima de la lista de archivos, haga clic en el menú desplegable que indica `main`. <div> <img src="https://docs.github.com/assets/cb-19635/mw-1440/images/help/branches/branch-selection-dropdown-global-nav-update.webp" width="500"/> </div>

1. Escriba un nombre, por ejemplo `readme-edits`, en el cuadro de texto.

1. Haga clic en **`Create branch`: `readme-edits`** from `main``. <div> <img src="https://docs.github.com/assets/cb-31026/mw-1440/images/help/repository/new-branch.webp" width="500"/> </div>

1. Ahora tiene dos branches, `main` y `readme-edits`. Ahora mismo, se ven idénticas. A continuación, agregarás cambios al nuevo branch

#### 3. Realizar y confirmar (commit) cambios

Al crear el nuevo branch en el paso previo, GitHub te lleva a la página de código del nuevo branch `readme-edits`, que es una copia de `main`.

Puedes modificar y guardar cambios a los archivos de tu repositorio. En GitHub, los cambios guardados se llaman confirmaciones o commits. Cada commit tiene un mensaje de confirmación asociado, el cual es una descripción que explica por qué se realizó algún cambio en particular. Los mensajes de confirmación capturan la historia de tus cambios para que otros contribuyentes puedan entender lo que hiciste y por qué.

1. En el branch `readme-edits` que ha creado, haga clic en el archivo README.md
2. Para editar el archivo, haz clic en <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-pencil" aria-label="Edit file" role="img"><path d="M11.013 1.427a1.75 1.75 0 0 1 2.474 0l1.086 1.086a1.75 1.75 0 0 1 0 2.474l-8.61 8.61c-.21.21-.47.364-.756.445l-3.251.93a.75.75 0 0 1-.927-.928l.929-3.25c.081-.286.235-.547.445-.758l8.61-8.61Zm.176 4.823L9.75 4.81l-6.286 6.287a.253.253 0 0 0-.064.108l-.558 1.953 1.953-.558a.253.253 0 0 0 .108-.064Zm1.238-3.763a.25.25 0 0 0-.354 0L10.811 3.75l1.439 1.44 1.263-1.263a.25.25 0 0 0 0-.354Z"></path></svg>
1. En el editor, escribe tu apellido y tu código PUCP
1. Haga clic en `Commit changes`
1. En el cuadro `Commit changes`, escribe un mensaje de confirmación que describa los cambios ("Info personal")
1. Haga clic en Confirmar cambios

Estos cambios solo se realizarán en el archivo README del branch `readme-edits`, por lo que ahora contiene contenido diferente al de `main`.

#### 4. Pull request

Ahora que tienes cambios en un branch derivado de `main`, puede abrir un pull request.

Los pull request son el núcleo de la colaboración en GitHub. Cuando abres una solicitud de cambios, estás proponiendo tus cambios y solicitando que alguien revise e integre tu contribución y la fusione (merge) en su branch. Los pull request muestran diffs o diferencias del contenido de ambos branches. Los cambios, adiciones y sustracciones se muestran en varios colores.

Tan pronto hagas un commit, puedes abrir un pull request y comenzar un debate (discussion), incluso antes de que se termine el código.

Con las menciones (`@mention`) de GitHub en el mensaje de solicitud de incorporación de cambios se puede solicitar comentarios de una persona o un equipo específico.

Incluso puedes abrir solicitudes de cambio en tu propio repositorio y fusionarlas tú mismo. Es una forma genial para aprenderse el flujo de GitHub antes de trabajar en proyectos más grandes.

1. Haga clic en la pestaña `Pull requests` del repositorio `hello-world`

1. Haga clic en `New pull request` 

1. En el cuadro `Example Comparisons`, seleccione el branch que ha creado (`readme-edits`), para compararla con `main` (la original)

1. Revisa tus cambios en los diffs en la página de `Compare`, asegúrate que son lo que quieres enviar. <div> <img src="https://docs.github.com/assets/cb-32937/mw-1440/images/help/repository/diffs.webp" width="500"/> </div>


1. Haga clic en `Create pull request`

1. Dale un título a tu solicitud de cambios y escribe una descripción breve de estos. Puedes incluir emojis y arrastrar y soltar imágenes y gifs

1. Opcionalmente, a la derecha del título y la descripción, haga clic en el  junto a `Reviewers`, `Assignees`, `Labels`, `Projects`, or `Milestone` para agregar cualquiera de estas opciones al pull request

1. Haga clic en `Create pull request` (Crear solicitud de incorporación de cambios)

Tus colaboradores ahora pueden revisar tus ediciones y hacer sugerencias.

#### 5. Merge

En este paso final, fusionará (merge) el branch `readme-edits` con el branch `main`, incoporando los cambios del branch `readme-edits` a `main`

1. En la parte inferior del pull request, haz clic en `Merge pull request` para combinar los cambios en `main`.

1. Haga clic en `Confirm merge`. Recibirás un mensaje indicando que la solicitud se fusionó con éxito y luego se cerró.

1. Haga clic en `Delete branch`. Ahora que la solicitud de incorporación de cambios se ha combinado y los cambios están en `main`, puede eliminar el branch `readme-edits` de forma segura. Si quieres hacer más cambios a tu proyecto, siempre puedes crear un nuevo branch y repetir este proceso.

#### 6. Clonar un repo<sup>[2](#myfootnote2)</sup>

Al clonar un repo, descargas el repo desde GitHub.com a tu máquina local. Esto facilita la corrección de conflictos de combinación, agregar o quitar archivos e insertar comentarios más grandes. 

Clonar un repo extrae una copia integral de todos los datos del repo que GitHub.com tiene en ese momento, incluidas **todas las versiones de cada archivo y carpeta del proyecto**. Puedes insertar los cambios (push) en el repo remoto o extraer los cambios de otras personas.

Puedes clonar tu repo existente o clonar el repo existente de alguien más para contribuir con un proyecto.

<a name="myfootnote2">[2]</a> Para mayor información sobre clonar un repo en diferentes OS (Mac, Windows, Linux), revisar la [documentación de GitHub](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)

#### 7. Probemos clonando el repo de una tarea ficticia de Intro a GitHub

- Al finalizar la clase de hoy estará disponible la Tarea Nº 1 en Canvas, la cual deberá ser entregada hasta las 11:59pm del jueves 4 de enero de 2024

- En Canvas, se activará el link para el repo de la tarea. Dicho link será parecido a este https://classroom.github.com/a/A1TvRWfw

- Le damos click, ubicamos nuestro nombre y luego vamos a "Accept this assignment"

- Se creará un repo con tu usuario de Github al final

- Usemos este repo para practicar! 


## B. Python

### 1. ¿Por qué Python?

Según el [índice TIOBE](https://www.tiobe.com/tiobe-index/) a julio de 2023, Python es el lenguaje más popular debido a su simplicidad, versatilidad y amplio espeectro de aplicaciones. Por ello, es un lenguaje preferido entre los científicos de datos, ya que permite dedicarle una mayor parte del tiempo a la interpretación que a las complejidades del lenguaje.

<div> <img src="https://images.datacamp.com/image/upload/v1688732584/image_bcd7581290.png" max-width="600"/> </div>

### 2. Instalar Python y Jupyter

#### miniconda

- Existen diversas alternativas para obtener Python. Para simplificar, se propone usar **miniconda**, que es un package manager y un environment manager. 

  - *Package manager* es una colección de herramientas que nos permite automatizar la instalación, configuración, actualización y desinstalación de programas de manera consistente(Wikipedia). En el día a día necesitaremos muchos paquetes externos cuya instalación puede generar conflicto con otros paquetes externos, o entre diferentes versiones. Conda nos solucionará ese problema!

  - *Environment manager*, o administrador de entornos, es una herramienta que permite la creación de entornos, que aislan los paquetes externos y versión de python usadas exclusivamente en ese entorno.  

- Ahora no necesitamos saber mucho sobre entornos, primero aprenderemos python y luego podemos hablar de cómo manejar entornos.

- Usaremos miniconda porque tiene los componentes mínimamente suficientes para trabajar en python. 

a. Ya tienes anaconda? 
  - Actualiza la versión utilizada.  

b. Quieres reemplazar anaconda por miniconda?
  - Sigue las instrucciones de desinstalación de https://docs.anaconda.com/anaconda/install/uninstall/ 

#### A instalar miniconda!
Descarga el instalador de https://docs.conda.io/en/latest/miniconda.html

- Selecciona este instalador según tu OS. **Tiene que ser Python 3.11**
- Al abrir instalador, selecciona la opción de *Install for just me*
- Usa la carpeta elegida por default para instalar miniconda
- Finalmente, por conveniencia, selecciona  *Register Anaconda as my default Python 3.x*


#### Listo! Ya tenemos miniconda y python instalado. 
- Esto también implica la instalación de Python, así como otros paquetes adicionales (pero no todos los necesarios aún).
- Para verificar que la instalación ha sido exitosa, abrimos el Anaconda Prompt y tipeamos

``` 
conda --version
``` 

- El resultado debería ser un número, que es la versión del conda instalado

#### ¿Cómo agregamos paquetes nuevos?

- Abrimos el Anaconda arompt y tipearemos lo siguiente

``` 
conda install numpy pandas jupyter altair
```

- Listo! Ya tenemos todos los paquetes que necesitamos

#### ¿Cómo abrir Jupyter?
- Abrimos el Anaconda Prompt y tipearemos lo siguiente

``` 
jupyter notebook
```

#### ¿Más preguntas?
Revisa este [post](https://www.codecademy.com/article/setting-up-jupyter-notebook) de CodeAcademy

### 3. Google Colab

- ¿Y si tenemos problemas con Python o con nuestra computadora? Podemos usar [Google Colab](https://research.google.com/colaboratory/) que pone a disposición de manera libre y gratuita (muy buenas) computadoras virtuales
- Además, al formar parte del entorno de Google, es fácilmente accesible desde su cuenta `@pucp`
- Incluso se puede aprovechar a Google Drive como almacenamiento en la nube. Para más información, revisar este [post](https://medium.com/analytics-vidhya/how-to-use-google-colab-with-github-via-google-drive-68efb23a42d) de Medium.


