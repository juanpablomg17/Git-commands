# GIT :)
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


### FORKS - HERRAMIENTA FUNDAMENTAL PARA CONTRUBUIR AL OPEN SOURCE

Forks o Bifurcaciones
-Es una característica única de GitHub en la que se crea una copia exacta del estado actual de un repositorio directamente en GitHub, éste repositorio podrá servir como otro origen y se podrá clonar (como cualquier otro repositorio), en pocas palabras, lo podremos utilizar como un git cualquiera.
Un fork es como una bifurcación del repositorio completo, tiene una historia en común, pero de repente se bifurca y pueden variar los cambios, ya que ambos proyectos podrán ser modificados en paralelo y para estar al día un colaborador tendrá que estar actualizando su fork con la información del original.

-Al hacer un fork de un poryecto en GitHub, te conviertes en dueñ@ del repositorio fork, puedes trabajar en éste con todos los permisos, pero es un repositorio completamente diferente que el original, teniendo alguna historia en común.

-Los forks son importantes porque es la manera en la que funciona el open source, ya que, una persona puede no ser colaborador de un proyecto, pero puede contribuír al mismo, haciendo mejor software que pueda ser utilizado por cualquiera.
.
Al hacer un fork, GitHub sabe que se hizo el fork del proyecto, por lo que se le permite al colaborador hacer pull request desde su repositorio propio.

Trabajando con más de 1 repositorio remoto
Cuando trabajas en un proyecto que existe en diferentes repositorios remotos (normalmente a causa de un fork) es muy probable que desees poder trabajar con ambos repositorios, para ésto puedes crear un remoto adicional desde consola.


## Stashed:

El stashed nos sirve para guardar cambios para después, Es una lista de estados que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama sin perder el trabajo que todavía no guardamos en un commit

Ésto es especialmente útil porque hay veces que no se permite cambiar de rama, ésto porque porque tenemos cambios sin guardar, no siempre es un cambio lo suficientemente bueno como para hacer un commit, pero no queremos perder ese código en el que estuvimos trabajando.

El stashed nos permite cambiar de ramas, hacer cambios, trabajar en otras cosas y, más adelante, retomar el trabajo con los archivos que teníamos en Staging pero que podemos recuperar ya que los guardamos en el Stash.

### git stash
El comando git stash guarda el trabajo actual del Staging en una lista diseñada para ser temporal llamada Stash, para que pueda ser recuperado en el futuro.

Para agregar los cambios al stash se utiliza el comando: git stash

Podemos poner un mensaje en el stash, para asi diferenciarlos en git stash list por si tenemos varios elementos en el stash. Ésto con:

git stash save "mensaje identificador del elemento del stashed"

### Obtener elelmentos del stash
El stashed se comporta como una Stack de datos comportándose de manera tipo LIFO (del inglés Last In, First Out, «último en entrar, primero en salir»), así podemos acceder al método pop.

El método pop recuperará y sacará de la lista el último estado del stashed y lo insertará en el staging area, por lo que es importante saber en qué branch te encuentras para poder recuperarlo, ya que el stash será agnóstico a la rama o estado en el que te encuentres, siempre recuperará los cambios que hiciste en el lugar que lo llamas.

Para recuperar los últimos cambios desde el stash a tu staging area utiliza el comando: git stash pop

Para aplicar los cambios de un stash específico y eliminarlo del stash: git stash pop stash@{<num_stash>}


Para retomar los cambios de una posición específica del Stash puedes utilizar el comando:
git stash apply stash@{<num_stash>}

Donde el <num_stash> lo obtienes desden el git stash list

### Listado de elementos en el stash
Para ver la lista de cambios guardados en Stash y así poder recuperarlos o hacer algo con ellos podemos utilizar el comando: git stash list 

### Crear una rama con el stash
Para crear una rama y aplicar el stash mas reciente podemos utilizar el comando
git stash branch <nombre_de_la_rama>

Si deseas crear una rama y aplicar un stash específico (obtenido desde git stash list) puedes utilizar el comando: git stash branch nombre_de_rama stash@{<num_stash>}

Al utilizar estos comandos crearás una rama con el nombre <nombre_de_la_rama>, te pasarás a ella y tendrás el stash especificado en tu staging area.

### Eliminar elementos del stash
Para eliminar los cambios más recientes dentro del stash (el elemento 0), podemos utilizar el comando: git stash drop

Pero si en cambio conoces el índice del stash que quieres borrar (mediante git stash list) puedes utilizar el comando: git stash drop stash@{<num_stash>}
Donde el <num_stash> es el índice del cambio guardado.

Si en cambio deseas eliminar todos los elementos del stash, puedes utilizar: git stash clear











