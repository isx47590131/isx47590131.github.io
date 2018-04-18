# Web portafolios Arnau Esteban Contraras - isx47590131.github.io

**Autor:** Arnau Esteban Contreras

**Id alumno:** isx47590131

**Correo:** arnauesteban@hotmail.com

**Descripción:** El proyecto consiste en la creación de una página web en la que te presentes como persona, y sirva como 
curriculum. Esta web esta constituida  por github pages, jekyll y Markdown principalmente, que conjuntamente, formaran plantillas de documentos html para ser visitados por los usuarios. 

Una de las principales ventajas es la facilidad/comodidad que esto supone a la hora de crear páginas web. 
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

|     Pasos      | Temas         |
| ------------- |-------------- |
|[Paso 1](#paso-1) | Creación repositiorio  |
| [Paso 2](#paso-2) | Instalar Jekill |
| [Paso 3](#paso-3) | Readme y gitignore |
| [Paso 4](#paso-4) | Adaptar el entorno de trabajo |
| [Paso 5](#paso-5) | Readme y gitignore |
| [Paso 6](#paso-6) | Readme y gitignore |


-----


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

Ahora toca crear el `README`, que han de tener todos los repositorios *git*, el cual debe contener un poco de que trata el repositiorio (como mínimo), informacion de contacto, etc. Debe ser así ya que es "la presentación" de nuestro repositorio.

Tambien es recomendable crear un fichero `.gitignore` donde se incluye el nombre de todos los ficheros y directorios que no queremos que se tengan en cuenta a la hora de commitear, ni que se suban al repositorio web de *git*. Por defecto al crear el repositorio usando *jekyll* nos ha creado uno, que contiene lo siguiente:

```
_site
.sass-cache
.jekyll-metadata
_config

```


### **Paso 4**

En este paso adaptaremos la estructura creada por defecto a nuestras necesidades. En mi caso no usare un blog, pero usare las funciones para poner en cada entrada una experiencia laboral. Además tendrá un inicio, acerca de mí, conocimientos y una página para contactarme. 
Todo esto se puede hacer tanto desde la web como desde terminal.

```
#creamos directorio de plantillas, css e imagenes
mkdir _layouts
mkdir css
mkdir img

#Renombramos el directorio de los blogs
mv blog experiencia

#Además creamos los directorios que no hagan falta...
mkdir contact
mkdir cv
```

Una vez tengas la estructura de directorios debes editar/mirar el fichero `_layouts/default.html` que contiene la estructura por defecto de las páginas web que hagamos. Si queremos podemos crear más de una. Indicaremos al principio de cada documento que *layout* usamos en cada página.

Esto es un ejemplo de como indicar que *layout* y *title*  usamos:
``` 
---
layout: default
title: Acerca de Arnau Esteban
---
```

### **Paso 5**

Redactar nuestro `_layouts/default.html` y dejarlo a nuestro gusto. 
En mi caso le pongo la barra de navegación y en *footer* las imagenes con los links para ponerse en contacto conmigo. Una web muy recomendable para buscar [iconos](https://www.iconfinder.com/ "web de iconos").
Por ejemplo:
![alt text](isx47590131.github.io/img/insta.png "logo insta")



```
<!DOCTYPE html>
	<html>
		<head>
			<title>{{ page.title }}</title>
			<link rel="icon" href="/img/github_lite.png" type="image/x-icon">

			<!-- link to main stylesheet -->
			<link rel="stylesheet" type="text/css" href="/css/main.css">
		</head>
		<body>
			<div class="navbar">
	    		<ul class="nav">
	        		<li class="nav"><a href="/">Inicio</a></li>
		        	<li class="nav"><a href="/about">Acerca de mí</a></li>
	        		<li class="nav"><a href="/cv">Conocimientos</a></li>
	        		<li class="nav"><a href="/experiencia">Experiencia</a></li>
	    		</ul>
			</div>
			<div class="container">
			
			{{ content }}
			
			</div><!-- /.container  https://fadado.github.io/ASIX/MP9/-->
			<footer>
	    		<ul>
	        		<li><a href="/contact" target="_blank" title="Envíame un correo"><img class="icon" alt="gmail" src="/img/gmail.png"></a></li>
	        		<li><a href="https://github.com/isx47590131" target="_blank" title="Mi repositorio de github"><img class="icon" alt="github" src="/img/github.png"></a></li>
	        		<li><a href="https://www.instagram.com/mixaritos/"target="_blank" title="Mi instagram"><img class="icon" alt="instagram" src="/img/instagram.png"></a></li>
	        		<li><a href="https://www.linkedin.com/in/arnau-esteban-b2b194131/"target="_blank" title="Mi linkedin"><img class="icon" alt="linkedin" src="/img/linkedin.png"></a></li>
				</ul>
			</footer>
		</body>
	</html>

```

Como podemos observar disponemos de varias funciones como `{{ page.title }}`, las quales resultan muy utiles para ahorrar tiempo y simplificar el codigo. Os dejo un enlace donde explican la mayoría de [FUNCIONES](https://learn.cloudcannon.com/jekyll-cheat-sheet/ "libreria funciones")

### **Paso 6**

Ahora en cada directorio creado en el paso anterior (que queramos mostrar página web) debemos editar/crear por los menos el *index.html*, en el qual indicamos en la cabezera el *layout* y *title* y a continuación editamos el *body* del documento en html y nos despreocupamos del *head* y el *footer* ya que esta por defecto en `_layouts/default`.

Aqui dejo el código mi página de inicio como ejemplo simple:

```
---
layout: default
title: Arnau Esteban Contreras
---
<div class="blurb">
	<h1>Arnau Esteban Contreras</h1>
	<p>I'm best known as the horrible cop from <em>A Touch of Evil</em> Don't trust me.
		<a href="/about">Read more about my life...</a></p>
</div>
```


