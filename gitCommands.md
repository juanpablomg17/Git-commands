GIT :)
•	git show: muestra todo el histórico que se ha hecho

•	git log filename.txt: muestra la historia entera de una archivo

•	git pull: traer info desde reporsitorio remoto

•	git init: crea o inicializa el repositorio

•	git add: agregar un archivo en el repositorio

•	git commit: guarda los cambios del staying en el repositorio local:

•	git commit –am: guarda los cambios en el staying y al mismo tiempo el repositorio local.

•	git rm filename: sacar un archivo del repositorio

•	git rm --cached: Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de trackear el historial de cambios de estos archivos, por lo que pasaran a un estado untracked.

•	git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

•	git config: listar todas las configuraciones de git

•	git config --list: configuración por defecto de tu git

•	git config --global user.name: cambiar el usuario global

•	git config --global user.password: cambiar la contraseña global

•	git config --global user.email: cambiar el email global

•	scape + i: para insertar texto en el editor de git

•	git diff: ver la diferencia entre un commit y otro (funciona con los identificadores de los commits, tener el cuenta el orden).

•	git reset --hard: Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás. Hay dos formas de usar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

•	git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.


•	git reset HEAD: Este es el comando para sacar archivos del área de staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.

•	git checkout commitID: este comando se usa para ver cómo era el archivo antes en el commit  específico.

•	git merge [branchName]: estando en la rama a la que quieres hacer el merge, invocas la otra rama en la se hicieron los cambios. (mege se usa para fusionar el contenido de dos ramas y que sólo quede en una)

•	git remote add origin: se usa para agregar un origen (repositorios remotos)

•	git remote: muestra el origen que configuraste, ejemplo “origin”

•	git remote –v: muestra el valor del origen que configuraste, ejemplo https://github.com/juanpablomg17/repoName.git (fetch). https://github.com/juanpablomg17/repoName.git (push)

•	git pull origin [branchMain] --allow-unrelated-histories = trae los cambios del repositorio remoto y los coloca en tu rama main que tienes el local, o en su defecto

•	git push origin [branchName]: envía últimos cambios de tu rama main al repositorio remoto.


// FORKS - HERRAMIENTA FUNDAMENTAL PARA CONTRUBUIR AL OPEN SOURCE

Forks o Bifurcaciones
-Es una característica única de GitHub en la que se crea una copia exacta del estado actual de un repositorio directamente en GitHub, éste repositorio podrá servir como otro origen y se podrá clonar (como cualquier otro repositorio), en pocas palabras, lo podremos utilizar como un git cualquiera.
Un fork es como una bifurcación del repositorio completo, tiene una historia en común, pero de repente se bifurca y pueden variar los cambios, ya que ambos proyectos podrán ser modificados en paralelo y para estar al día un colaborador tendrá que estar actualizando su fork con la información del original.

-Al hacer un fork de un poryecto en GitHub, te conviertes en dueñ@ del repositorio fork, puedes trabajar en éste con todos los permisos, pero es un repositorio completamente diferente que el original, teniendo alguna historia en común.

-Los forks son importantes porque es la manera en la que funciona el open source, ya que, una persona puede no ser colaborador de un proyecto, pero puede contribuír al mismo, haciendo mejor software que pueda ser utilizado por cualquiera.

-Al hacer un fork, GitHub sabe que se hizo el fork del proyecto, por lo que se le permite al colaborador hacer pull request desde su repositorio propio.

-Trabajando con más de 1 repositorio remoto
Cuando trabajas en un proyecto que existe en diferentes repositorios remotos (normalmente a causa de un fork) es muy probable que desees poder trabajar con ambos repositorios, para ésto puedes crear un remoto adicional desde consola.

git remote add <nombre_del_remoto> <url_del_remoto>
git remote upstream https://github.com/freddier/hyperblog 

Al crear un remoto adicional podremos, hacer pull desde el nuevo origen (en caso de tener permisos podremos hacer fetch y push)

git pull <remoto> <rama>
git pull upstream master

Éste pull nos traerá los cambios del remoto, por lo que se estará al día en el proyecto, el flujo de trabajo cambia, en adelante se estará trabajando haciendo pull desde el upstream y push al origin para pasar a hacer pull request.

git pull upstream master
git push origin master





