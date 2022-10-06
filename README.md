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





