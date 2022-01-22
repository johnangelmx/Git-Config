# Github Comandos

## Configuraciones Iniciales

Creando el nombre de usuario: <br>
`git config --global user.name "Nombre de Usuario"`

Creando el Email: <br>
`git config --global user.email "Email del usuario" `

Confirmando u modificando informacion:<br>
`git config --global -e`

(OPCIONAL) Para poder cambiar el nombre de la rama principal es de la siguiente manera (OPCIONAL) <br>
Nota : las <> llaves no van incluidas <br>
`git config --global init.defaultBranch <name>`

<br>

# Inicializando el repositorio

Para Inicializar un repositorio es: <br>
`git init`

Para ver el estado del repositorio es:<br>
`git status`<br><br>

# Planteando la aderencia en el repositorio <br>

agregar archivos al repositorio es la accion antes de hacer la copia de seguridad<br>
para ello se usa el :<br>
`git add ` <br>
Se puede usar con un unico archivo , ejemplo:<br>
`git add index.html`<br>
Para poder añadir todo lo que hace falta en el estado es:<br>
`git add . `<br>
Para poder quitar un archivo ya añadido es con:<br>
Nota : las <> llaves no van incluidas <br>
`git reset <nombre del archivo>`

## Planteando la "fotografia" del repositorio <br>

una vez ya adquirido los archivos a respaldar la instruccion para proceder es: <br>
`git commit -m "nombre del commit"`

Otra forma de agregar al "escenario" y "tomar la fotografia",<br> en otras palabras hacer las acciones (git add .) y (git commit) en una sola accion es la siguiente:<br>
`git commit -am "nombre del comit"` <br>

## Visualizando el arbol (La linea de respaldos)

Para poder visualizar la linea de respaldo o el arbol es con: <br>
`git log `

# Uso de git

Para poder restaura el ultimo respaldo (commit) hecho en nuestro repositorio se usa: <br>
`git checkout -- .`<br>
Siendo asi se restaura por completo todos los archivos de la ultima copia de seguridad<br><br>

# Branch (Rama)

La analogía de la rama, dicta que la estructura del respaldo es como una rama, pero esta, esta <br>al pendiente en todo momento de la rama principal (master o el nombre que se le allá dado)<br>
Pero con la peculiaridad que puedes respaldar en una rama, y unir la misma en la rama principal <br>
Con sus diferente características y modificaciones que se explican más adelante en este documento<br><br>
Para poder visualizar la rama en la que se esta trabajando se utiliza el <br>
`git branch`
<br>
Otra forma de cambiar el nombre de la rama principal sin afectar globalmente seria la siguiente:<br>
Esto es altamente RECOMENDADO <br>
`git branch -m master main`
<br>Esto cambia la rama principal llamada master en el nombre de main que ahora es llamada asi la rama principal
<br><br>

# Entendiendo excepciones de git

Una de las forma en la cual git agrega carpetas al repositorio es cuando las mismas tienen <br>archivos , de lo contrario no contara para ser relpadado en caso de tener carpetas importantes <br> y que no tengan un archivo en el , o proximo ser añadido , se utiliza el : <br>
`.gitkeep`
<br>como nombre de un archivo oculto que podra ser identificado y respaldado por git
<br><br>

# Alias en Git

Una forma de visualizar de mejor manera los comandos permitiendo la utilidad de ver la informacion
<br> Ejemplos Recomdables<br>
git status:<br>
`git config --global alias.s "status -sb"`
<br> git log: <br> 
`git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"`

# Diferencias y modificaciones en el escritorio 
Parte de git es visualizar diferencia en cuanto a diferentes commits , es decir modificacion que talves por si no recordamos parte de la ultima modificacion , o intercambiamos lineas que tal vez creemos que no tienen repercucion , la herramienta de diferenciacion nos sirve para ello , con el siguiente comando: <br>
`git diff` <br>
Unicamente con archivos que esten fuera del stage, fuera del escenario , es decir que aun no se aplicaron el "git add" , para visualizar la diferencia que haya pasado y este en el escenario se ultiliza lo siguiente: <br>
`git diff --staged`<br>

# Actualizar el mensaje del commit y revetir commits
Una de las formas de manipular el mensaje del ultimo commit se hace con el amend (enmendar) <br>
`git commit --amend -m 'Mensaje correcto'`
<br><br>
Para hacer modificacines dentro del ultimo commit sin la necesidad de borra o crear uno nuevo seria :  <br>
`git reset --soft HEAD^` <br>
cuando se hace un git reset se ha visto que se utiliza para regresarlo del stage , siempre y cuando el archivo se le da seguimiento ,  pero en este caso el HEAD^ apunta al ultimo commit: Es decir no hace la modificacion , sino que que te regresa un commit antes del ultimo commit que hiciste para que puedas modificarlo sin problemas 
