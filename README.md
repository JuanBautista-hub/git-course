# Comandos basicos
### **Ver archivos ocultos**
 *ls -al*

### **Ver el estado**
*git status*

### **Agregar todas los archivos e individuales**
*git add .*
*git add  namearchive.txt*

### **Agregar commit**
*git commit -m"mi comentario"*

# Configuracion de usuario de git

### **Configurar git**
*git config*
### **Para ver archivos de configuración donde esta guardado**
*git config --list --show-origin*

### **Cambiar configuracion del usuario**
*git config --global user.name "Juan"*

### **Cambiar configuracion del email**
*git config --global user.email "gomezperezjuanbautista@gmail.com"*
# Cambios e historial de modificaciones en  archivos
### **Ver el contenido de un archivo**
*cat readme.md*

### **Para ver el historial de modificaciones o los tags**
*git log readme.md*

### **Ver ultimo cambio que se hizo**
*git show*

### **Comparar las versiones del commit de un archivo**
*git log readme.md*

*git diff 055331234k4324jk2jk 9203i442nkk3n42421j3*
# Regresar a una version anterior
### **Duro**
Este comando  regresa todo al estado anterior, elimina todo los que se ha hecho anteriormente

*git reset 055331234k4324jk2jk --hard*
### **Suave**
*git checkout -055331234k4324jk2jk archivo.txt*

una vez que estemos en la version modificamos el archivo
luego o añadimos  con *git add* 

luego  realizamos el 
*git commit -m"reempleazo de la ultima versiona una version antigua"*

### **git rm diferencia entre git reset**
*git rm*

Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

git rm --cached: Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de trackear el historial de cambios de estos archivos, por lo que pasaran a un estado untracked.

git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

*git reset*

Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es muy peligroso y debemos emplearlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de utilizar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la 
información de los commits y del área de staging se borra del historial.

Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es muy peligroso y debemos emplearlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de utilizar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
# Ramas
La rama principal master
### - **master**: *commit1--commit2--commit3* --**commit4**-- HEAD


Podemos crear una nueva rama  por ejemplo **devolopement**

en el **commit4** unimos la rama **devolopement** a master
### - **devolopement**: *commit1--commit2*

### **Unir cambios entre una rama a otra**
*git merge*

# Cómo funcionan las ramas en GIT
Las ramas son la manera de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.

**git branch -nombre de la rama-**: Con este comando se genera una nueva rama.

**git checkout -nombre de la rama-**: Con este comando puedes saltar de una rama a otra.

**git checkout -b rama**: Genera una rama y nos mueve a ella automáticamente, Es decir, es la combinación de git brach y git checkout al mismo tiempo.

**git reset id-commit**: Nos lleva a cualquier commit no importa la rama, ya que identificamos el id del tag., eliminando el historial de los commit posteriores al tag seleccionado.

**git checkout rama-o-id-commit:** Nos lleva a cualquier commit sin borrar los commit posteriores al tag seleccionado
# Fusion de ramas

git checkout master
git merge cabecera

# Conflicto  entre ramas


Los archivos con conflictos por el comando git merge entran en un nuevo estado que conocemos como Unmerged. Funcionan muy parecido a los archivos en estado Unstaged, algo así como un estado intermedio entre Untracked y Unstaged. Solo debemos ejecutar git add para pasarlos al área de staging y git commit para aplicar los cambios en el repositorio.

# Revertir merge
Si nos hemos equivocado y queremos cancelar el merge, debemos usar el siguiente comando:
git merge --abort

# Comando para ver la linea de tiempo del proyecto
 *git log --all --graph --decorate --oneline*

 simplificado: *alias arbolgit = "git log --all --graph --decorate --oneline"*

 se guardara el comando en la terminal entonces cuando necesitas ejecutar de nuevo bastaría escribir el comando

 *arbolgit*

 # Crear tags (o versiones)

*$ git tag -a v0.1 -m "Primera version de mi aplicación" 88f86f7*

### **Ver los tags**
*git show-ref --tags*
### **Enviar tags remoto**
*git push origin --tags*

### **borrar tags en remoto**
*git push origin :refs/tags/nombredeltag*

# Flujo de trabajo

Para poder desarrollar software de manera óptima y ordenada, necesitamos tener un flujo de trabajo profesional, que nos permita trabajar en conjunto sin interrumpir el trabajo de otros desarrolladores. Una buena práctica de flujo de trabajo sería la siguiente:

* Crear ramas
* Asignar una rama a cada programador
* El programador baja el repositorio con git pull origin master
* El programador cambia de rama
* El programador trabaja en esa rama y hace commits
* El programador sube su trabajo con git push origin #nombre_rama
* El encargado de organizar el proyecto baja, revisa y unifica todos los cambios

*Aporte creado por: Alejandro Dubon.*

# Pull request
En un entorno profesional normalmente se bloquea la rama master, y para enviar código a dicha rama pasa por un code review y luego de su aprobación se unen códigos con los llamados merge request.

Para realizar pruebas enviamos el código a servidores que normalmente los llamamos staging develop (servidores de pruebas) luego de que se realizan las pruebas pertinentes tanto de código como de la aplicación estos pasan al servidor de producción con el ya antes mencionado merge request.

Los PR (pull requests) son la base de la colaboración a proyectos Open Source, si tienen pensando colaborar en alguno es muy importante entender esto y ver cómo se hace en las próximas clases. Por lo general es forkear el proyecto, implementar el cambio en una nueva rama, hacer el PR y esperar que los administradores del proyecto hagan el merge o pidan algún cambio en el código o commits que hiciste.

Proceso de un pull request para trabajo en producción:
Un pull request es un estado intermedio antes de enviar el merge.
El pull request permite que otros miembros del equipo revisen el código y así aprobar el merge a la rama.
Permite a las personas que no forman el equipo, trabajar y colaborar con una rama.
La persona que tiene la responsabilidad de aceptar los pull request y hacer los merge tienen un perfil especial y son llamados DevOps

*Aporte creado por: Kevin Morales.*