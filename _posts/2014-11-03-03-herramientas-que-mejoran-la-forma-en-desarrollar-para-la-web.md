---
layout: post
title: "4 Herramientas para desarrolladores web que te cambiarán la vida"
author: gian_paima
modified:
categories: 
excerpt: "Con el paso de los años pasamos de crear web estáticas a crear web dinámicas y ahora es el momento de las aplicaciones web."
tags: []
comments: false
image:
  feature:
date: 2014-11-03T23:36:30-05:00
---
<figure>
	<img src="https://lh4.googleusercontent.com/QPRBDEGMNKUrJkSpHjIt7wBwCblHsTiGMU0wSrpn70g=s0">
	<figcaption>grunt, bower, yeoman, stylus, chrome developer tools, angularjs, karma, bootstrap, icomoon, code academy.</figcaption>
</figure>

Con el paso de los años pasamos de crear web estáticas a crear web dinámicas y ahora es el momento de las aplicaciones web. Así como las tecnologías para el desarrollo web han avanzado y se podría decir que es un poco más difícil desarrollar en este universo de muchas alternativas, pero para eso también han evolucionado las herramientas para crearlas.
Ahora les traigo una lista que les cambiará la manera en que estaban desarrollando para la web. A mi me sirvieron y no lo dudo que a ti también.

## [Grunt](http://gruntjs.com/)

Grunt es una librería hecha en Javascript que su principal función es administrar las tareas de nuestro proyecto. Por ejemplo, cada vez que escribimos código del lado del cliente ya sea HTML o CSS tenemos que refrescar la página para ver los cambios que hemos realizado, esto se puede tornar un poco aburrido y fastidioso cuando se trata de proyectos donde se tiene que ver la compatibilidad con un gran grupo de dispositivos. Grunt viene a solucionar este problema por que nos permite predefinir una o un conjunto de tareas que son repetitivas.

#### **Instalación de Grunt:**
Para instalar Grunt previamente tenemos que instalar Node.js.
{% highlight javascript %}
	$ npm install -g grunt-cli
{% endhighlight %}
##### Ejemplo de un archivo Gruntfile
En el siguiente `Gruntfile`, metadatos del proyecto son importados dentro de un archivo llamado `package.json`de la configuración del proyecto y un plugin [grunt-contrib-uglify](http://github.com/gruntjs/grunt-contrib-uglify). `uglify`es un tarea que esta configurada para minificar los archivos fuente y generar comentarios usando metadata. Cuando `grunt` se ejecuta en la linea de comandos, la tarea `uglify`se ejecutará por defecto.
	
{% highlight javascript %}
module.exports = function(grunt) {
  // Configuración del proyecto.
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    uglify: {
      options: {
        banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n'
      },
      build: {
        src: 'src/<%= pkg.name %>.js',
        dest: 'build/<%= pkg.name %>.min.js'
      }
    }
  });
  // Cargar el plugin que ejecutará la tarea de "uglify".
  grunt.loadNpmTasks('grunt-contrib-uglify');
  // Tareas por defecto.
  grunt.registerTask('default', ['uglify']);
};
{% endhighlight %}

## [Bower](http://bower.io/)

Bower es un gestor de paquetes para desarrolladores web. Hoy en día las páginas web están hechas de muchas cosas — frameworks, librerías, assets y más. Bower hace fácil administrar todas estas cosas.

La forma de trabajar de Bower es buscar e instalar todos los paquetes que necesite tu sistema, encargándose de buscar, descargar y guardar todos los paquetes que estes buscando. Bower se encarga de hacer un seguimiento a los paquetes que tengas instalado en tu archivo manifiesto, `bower.json`.

Lo mas interesante de Bower es la forma de usarlo ya que depende completamente de nosotros. Bower nos provee las herramientas necesarias para poder utilizarlo en nuestros flujos de trabajo.

#### **Instalación de Bower:**
Para instalar Bower previamente tenemos que instalar Node.js.
{% highlight javascript %}
  $ npm install -g bower
{% endhighlight %}

##### Ejemplo: instalar un paquete mediante Bower.
{% highlight python %}
  // Un paquete registrado en Bower
  bower install jquery
  // Una URL de Github
  bower install desandro/masonry
  // Reporsitorio Git
  bower install git://github.com/user/package.git
  // URL
  bower install http://ejemplo.com/script.js
{% endhighlight %}

## [Yeoman](http://yeoman.io/)

Yeoman es una herramienta esencial a la hora de comenzar nuevos proyectos. Yeoman nos provee de herramientas y de las mejores prácticas para pre-establecer una organización para los archivos de nuestro proyecto, esto nos permite ser más productivos a la hora de empezar el proyecto.

Yeoman para hacer todo esto posible usa algo llamado generador. Un generador básicamente es un plugin que se genera mediante el comando `yo`, el cual nos permite generar una jerarquía para nuestro proyecto.

#### **Instalación de Yeoman:**
Para instalar Yeoman previamente tenemos que instalar Node.js.
{% highlight python %}
  $ npm install -g yo
{% endhighlight %}

## [Stylus](http://learnboost.github.io/stylus/)
Stylus es un pre-procesador de CSS. Stylus nos cambia la forma de escribir CSS proporcionando una manera eficiente, dinámica y
natural de escribir CSS.

####**Instalación de Stylus:**
Para instalar Stylus previamente tenemos que instalar Node.js.
{% highlight python %}
  $ npm install stylus -g
{% endhighlight %}

##### Ejemplo
{% highlight css %}
  border-radius()
  -webkit-border-radius: arguments
  -moz-border-radius: arguments
  border-radius: arguments

body a
  font: 12px/1.4 "Lucida Grande", Arial, sans-serif
  background: black
  color: #ccc

form input
  padding: 5px
  border: 1px solid
  border-radius: 5px
{% endhighlight %}