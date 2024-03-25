# Chuleta Git

- **git init nombre-repositorio** crea un repositorio nuevo con el nombre indicado.
- **git status** muestra el estado de los cambios en el repositorio desde la última versión guardada.
- **git add fichero** añade/actualiza los cambios en el fichero <fichero> del directorio de trabajo a la zona de intercambio temporal.
- **git add carpeta** añade/actualiza los cambios en todos los ficheros de la carpeta <carpeta> del directorio de trabajo a la zona de intercambio temporal.
- **git add** añade/actualiza todos los cambios de todos los archivos en la zona de intercambio temporal.
- **git rm fichero** elimina el fichero de la zona de trabajo
- **git rm --cached fichero** elimina el fichero de la zona de intercambio temporal.
- **git mv fichero nuevo-fichero** renombra el fichero o lo mueve de un path a otro. Cambiar el nombre se entiende como un movimiento.
- **git commit -m “mensaje”** confirma todos los cambios de la zona de intercambio temporal añadiéndolos al repositorio y creando una nueva versión del proyecto. “mensaje” es una breve descripción de los cambios realizados que se asociará a la nueva versión del proyecto.
- **git commit --amend -m “mensaje”** cambia el mensaje del último commit por el nuevo “mensaje”
- **git dif** muestra las diferencias entre el directorio de trabajo y la zona de intercambio temporal.
- **git diff --cached** muestra las diferencias entre la zona de intercambio temporal y el último commit.
- **git diff HEAD** muestra la diferencias entre el directorio de trabajo y el último commit.
- **git show**  muestra el usuario, el día, la hora y el mensaje del último commit, así como las diferencias con el anterior.
- **git show <commit>** muestra el usuario, el día, la hora y el mensaje del commit indicado, así como las diferencias con el anterior.
- **git show HEAD~X** muestra el commit X anterior al último.
- **git log** muestra el historial de commits de un repositorio ordenado cronológicamente. Para cada commit muestra su código hash, el autor, la fecha, la hora y el mensaje asociado. .
    - Este comando es muy versátil y muestra la historia del repositorio en distintos
    formatos dependiendo de los parámetros que se le den. Los más comunes son:
        - **--oneline**: muestra cada commit en una línea produciendo una salida más compacta.
        - **--graph**: muestra la historia en forma de grafo.
        - **--pretty**: muestra la salida en formato más legible
        - **--n** X: muestra los X ultimos commits
        - **--stat**: muestra información sobre los archivos que se han cambiado y las líenas afectadas
        - **--author** =”XX”: muestra los commits que ha realizado XX
- **git annotate fichero o git blame fichero:** muestra el contenido de un fichero anotando cada línea con información del commit en el que se introdujo.
- **git restore fichero**. Elimina los cambios realizados en el fichero en tu directorio de trabajo
- **git restore --staged fichero**. Elimina los cambios realizados en el fichero de la zona de  lmacenamiento
    - **OJO: Nos puede servir para recuperar ficheros eliminados por error**
- **git reset <fichero>** elimina los cambios del fichero <fichero> de la zona de intercambio temporal, pero preserva los cambios en el directorio de trabajo.

[]()

- **git reset <commit>** actualiza el HEAD al commit <commit>, es decir, elimina todos los commits posteriores a este commit, pero no elimina los cambios del directorio de trabajo.
    - Modifica el índice (el llamado "área de preparación"). O bien, los cambios a los que está comprometido un encabezado de rama están apuntando actualmente. Este comando puede alterar el historial existente (cambiando la confirmación que hace referencia una rama).
- **git reset --soft <commit>** no toca el archivo de índice ni el árbol de trabajo en absoluto (pero restablece la cabeza a <commit>). Esto deja todos sus archivos modificados "Cambios para ser
comprometidos", como diría git status.
- **git reset --hard <commit>** elimina todos los cambios desde el commit <commit> y actualiza el HEAD este commit.
- **git branch <rama>** crea una nueva rama con el nombre <rama> en el repositorio a partir del último commit, es decir, donde apunte HEAD.
- **git branch** muestra las ramas activas de un repositorio indicando con * la rama activa en ese momento.
- **git log --graph --oneline** muestra la historia del repositorio en forma de grafo. Si queremos que incluya todas las ramas le añadimos un --all en lugar de un --oneline
- **git checkout <rama>** actualiza los ficheros del directorio de trabajo a la última versión del repositorio correspondiente a la rama <rama>, y la activa, es decir, HEAD pasa a apuntar al último commit de esta rama.
- **git checkout -b <rama>** crea una nueva rama con el nombre <rama> y la activa, es decir, HEAD pasa a apuntar al último commit de esta rama. Es equivalente alos comandos git branch <rama> y después git checkout <rama>
    - Saltar entre ramas cambia archivos en tu directorio de trabajo. Si saltas a una rama antigua, tu directorio de trabajo retrocederá para verse como lo hacía la última vez que confirmaste un cambio en dicha rama.
- **git merge <rama>** integra los cambios de la rama <rama> en la rama actual a la que apunta HEAD.
- **git branch -d <rama>** elimina la rama de nombre <rama> siempre y cuando haya sido fusionada previamente.
- **git branch -D <rama>** elimina la rama de nombre <rama>incluso si no ha sido fusionada. Si la rama no ha sido fusionada previamente se perderán todos los cambios.
- **git rebase <rama-1> <rama-2>** replica los cambios de la rama <rama-1> en la rama <rama-2> partiendo del ancestro común de ambas ramas.
    - El resultado es el mismo que la fusión de las dos ramas pero la bifurcación de la <rama-1> desaparece ya que sus commits pasan a estar en la <rama-2>.
- **git clone <url-repositorio>** crea una copia local del repositorio ubicado en la dirección <url-repositorio>.
- **git remote add <repo-remoto> <url>** crea un enlace con el nombre <repo-remoto> a un repositorio remoto ubicado en la dirección <url>.
- **git pull <repo-remoto> <rama>** descarga los cambios de la rama <rama> del repositorio remoto <remoto> y los integra en la última versión del repositorio local, es decir, en el HEAD.
- **git fetch <remoto>**descarga los cambios del repositorio remoto <remoto> pero no los integra en la última versión del repositorio local.
- **git push <remoto> <rama>** sube al repositorio remoto <remoto> los cambios de la rama <rama> en el repositorio local.