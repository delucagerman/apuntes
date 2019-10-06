# Lista de comandos más usados
## Conceptos
- PROMPT: Donde se encuentra el cursor, un lugar en el árbol de nodos que es la
representación del disco duro en el sistema operativo
## Comandos (y algunas banderas)
- ls: lista los contenidos de un directorio
- ls -l: lista los archivos con datos de cada nodo, ordenados alfabéticamente
- ls -lS: lista los contenidos ordenados por tamaño
- ls -lh: lista los contenidos mostrando los datos legibles fácilmente (tamaño)
- ls -r: lista los archivos ordenados de forma inversa (sirve con las banderas S y `t`)
- ls -a: lista los contenidos de un directorio incluyendo los archivos ocultos
- tree lista recursivamente la estructura de árbol de un directorio incluyendo tanto archivos
como directorios (**NOTA:** No viene pre-instalado así que hay que instalarlo primero con su
administrador de paquetes preferido: para RHEL/CentOS/Fedora yum install tree para
Debian/Mint/Ubuntu apt-get install tree, para OS X `brew install tree`)
- tree -L 1: muestra recursivamente la estructura de árbol de un directorio pero sólo hasta el
primer subnivel de directorios
- tree -a: muestra recursivamente la estructura de árbol de un directorio incluyendo tanto
archivos como directorio ocultos
- tree -d: muestra recursivamente la estructura de árbol de un directorio tomando en cuenta
sólo los directorios
- tree -dL 1: muestra recursivamente la estructura de árbol de un directorio tomando en cuenta
sólo los directorios y hasta el primer subnivel
- rm [FILE]: elimina un archivo
- rm -rf [DIRECTORY]: elimina un directorio recursivamente sin preguntar
- mv [FILE] [DIRECTORY]: mueve FILE a DIRECTORY
- mv [FILE] [NAME]: renombra FILE a NAME
- cd [DIRECTORY]: lleva el PROMPT a DIRECTORY
- touch [FILE]: si FILE existe, modifica la hora de última modificación al momento de la
ejecución del comando, si FILE no existe, lo crea
- ln -s [DIRECTORY] [NAME]: crea un _link_ simbólico llamado NAME hacia DIRECTORY,
NAME se comporatará como DIRECTORY
- tail [FILE]: muestra las últimas 10 lineas de un archivo de texto
- tail -f [FILE]: tail _forever_, en principio muestra las últimas 10 líneas de FILE, pero mantiene
abierto el archivo e imprime los cambios que se vayan escribiendo (secuencialmente) en éste,
muy útil para _logs_.
- more [FILE]: muestra el contenido de un archivo de texto de forma páginada
- cat [FILE]: imprime todo el contenido de un archivo en pantalla- clear:limpia la terminal
- pwd: imprime o muestra la ruta actual donde nos encontramos ubicados
- man [COMANDO]: muestra la documentacion de todos los comandos
- mkdir [DIRECTORY]: crea un directorio en la ubicación actual
- mkdir -p [RUTA]: crea un árbol de directorios completo que no existe
- cp [archivo/directorio origen] [archivo/directorio destino]: copia un archivo o directorio desde
un origen a un destino
- cp -r [directorio origen] [directorio destino]: copia un directorio y todos sus directorios hijos de
forma recursiva
- xdg-open [-a APP] [ FILE | DIRECTORY ]: abre el (archivo o directorio) con la aplicación por
defecto en el sistema operativo, si se manda la bandera -a usará la APP para abrirlo
### Operadores para STDIN, STDOUT/STDERR
`
#### operador | (pipe):
command_1 | command_2
Manda el STDOUT de command_1 al STDIN de command_2
#### operador >
command_1 > FILE
Manda el STDOUT de command_1 al inicio de FILE. Si FILE no existe lo crea, si existe lo
sobreescribe.
#### operador >>
command_1 >> FILEManda el STDOUT de command_1 al inicio de FILE. Si FILE no existe lo crea, si existe lo
concatena al fina (tras u
n _newline_).
#### operador <
command_1 < FILE
Manda al STDIN de command_1 el contenido de FILE.
#### redirección de salidas
1. command > FILE - manda el STDOUT a FILE
1. command 1> FILE 2>FILE_ERROR - manda el STDOUT a FILE y el STDERR a
FILE_ERROR
1. command > FILE 2>&1 - manda, tanto el STDOUT como el STDERR a FILE
1. command >> FILE 2>&1 - manda a concatenar las salidas de STDOUT y STDERR a FILE
### Combinación de teclas como comandos
1. [ctrl]-C - este comando termina el proceso que se esté ejecutando en la terminal, haya o no
acabado de ejecutarse.
2. [ctrl]-D - el sistema lo interpreta como _EOF_ (End Of File) y cierra el _stream_ de entrada
(STDIN) para un archivo en donde se esté escribiendo desde la terminal.
## Editor VI
### Cómo salir de VI/VIM
Ejecutar la siguiente combinación de teclas para
1. salir guardando los cambios: [ESC] : w q ![ENTER]
2. salir sin guardar cambios: [ESC] : q ! [ENTER]
### Moverse un espacio a la derecha
tecla l
### Copiar linea
yy
### Borrar linea
dd
### Borrar carácter
tecla x
### Pegar linea
[SHIFT] + p### Insertar Texto
tecla i
### Pegar portapapeles
[SHIFT] + Insert