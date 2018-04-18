# Web portafolios Arnau Esteban Contraras - isx47590131.github.io

**Autor:** Arnau Esteban Contreras

**Id alumno:** isx47590131

**Correo:** arnauesteban@hotmail.com

**Descripción:** El proyecto consiste en la creación de una página web en la que te presentes como persona, y sirva como 
curriculum. Esta web esta constituida  por github pages, jekyll y Markdown principalmente, que conjuntamente, formaran plantillas de documentos html para ser visitados por los usuarios. 

Una de las principales ventajas es la facilidad/comodidad que esto supone a la hora de crear paginas web. 
Una desventaja es la poca flexibilidad que te permite, ya que las funciones usadas por jekyll son limitadas.


## Tecnologias que contiene:

- GitHub pages
- HTML
- css
- Jekyll
- Markdown


-----

# Documentación realización de la web

## Indice

|     Paso      | Tema          |
| ------------- |-------------- |
|[Paso 1](#Paso_1) | Creación repositiorio  |
| [Paso 2](#Paso_2) | Instalar Jekill       |
| [Paso 3](#Paso_3) | Readme y gitignore     |



### **Paso 1**

Para empezar debes registrarte en GitHub y crear un repositorio, ya sea privado o publico, aunque recomiendan publico (al ser visitado por cualquiera). El nombre del repositorio debe ser del siguiente  estilo: *nombre.github.io* 

### **Paso 2**

Para continuar hay que instalar Jekyll en nuestro ordenador:

```
sudo dnf install rubygems rubygems-devel ruby-devel
sudo dnf install redhat-rpm-config
sudo dnf install gcc-c++
sudo gem install bundler
sudo gem install jekyll
```

Seguidamente escojemos el directorio de trabajo (o lo creamos) y con jekyll creamos el directorio, que debe llamarse igual que el repositorio.

```
cd directorio/de/trabajo
jekyll new nombre.github.io

```

Una vez creado entramos y lo inicializamos en Git y lo configuramos con nuestra cuenta de GitHub.
Si miramos en el directorio que hemos creado con *Jekyll* vamos que ya tenemos algunos archivos, los cuales nos serviran de base.

```
cd nombre.github.io
git init
```

Aqui puedes hacerlo de dos modos, uno por http y otro por ssh (es recomendable hacerlo por ssh, ya que es mas comodo y seguro)

```
#http:
git remote add NombreRemote https://github.com/usuario/nombre.github.io.git

#ssh (primero se deben crear las claves):
ssh-keygen -t rsa -C "correo@gmail.com" -b 4096
cat ~/.ssh/id_rsa.pub | clip
#Y lo copiamos en: Usuario > Settings > SSH and GPG keys > New SSH key
git remote add NombreRemote git@github.com:usuario/nombre.github.io.git

```


### **Paso 3**

Ahora toca crear el `README`, que han de tener todos los repositorios *git*, el cual debe contener un poco de que trata el repositiorio (como mínimo), informacion de contacto, etc.

Tambien es recomendable crear un fichero `.gitignore` donde se incluye el nombre de todos los ficheros y directorios que no queremos que se tengan en cuenta a la hora de commitear, ni que se suban al repositorio web de *git*.

