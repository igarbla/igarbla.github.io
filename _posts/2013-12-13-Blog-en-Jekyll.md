---
layout: post
title: "Blog en Jekyll"
date: "2013-12-13 15:56:15"
categories:
 - jekyll
 - drupal
---

Me he decidido a migrar el blog que tenía con [Drupal 7][drupal] a [Jekyll][jekyll] librándome de esta manera de tener que lidiar con una base de datos y consiguiendo una mejora importante en el redimiento de la página.

Primero he tenido que importar el contenido que tenía ya publicado sigiendo las instrucciones de [Jekyll import][jekyll_import], muy sencillo. Tras repasar los post y realizar alguna pequeña modificación, me he conectado al servidor y he creado un repositorio git. Ya instalé [jekyll en el server][jserver], solo falta preparar un hook de git para cuando quiera publicar los post jekyll regenere el sitio. Está, quizas, ha sido la parte que más me ha costado, pero al final, como casi siempre, la solución es más sencilla de lo que parece. El fichero es el mismo que figura en [Jekyll deployment methods][jdeploy], salvo el [shebang][wikipedia], que producía en un error de comando no encontrado; por lo que lo he cambiado por:

{% highlight bash %}#!/home/user/.rvm/bin/rvm-shell 2.0.0-p247{% endhighlight %}

Ahora en local añado como remoto el repositorio recien creado en el server,

{% highlight bash %}git remote add deploy deployer@example.com:~/myrepo.git{% endhighlight %}

y con hacer

{% highlight bash %}git push deploy master{% endhighlight %}

el blog queda actualizado.


[drupal]: https://drupal.org
[jekyll]: https://jekyllrb.com
[jekyll_import]: https://import.jekyllrb.com/docs/home/
[jserver]: https://www.txorua.com/blog/instalar-ruby-con-rvm-sin-privelegios-de-root
[jdeploy]: https://jekyllrb.com/docs/deployment-methods/
[wikipedia]: https://es.wikipedia.org/wiki/Shebang
{% comment %}
Broken link
[kristian]: https://kristianfreeman.com/deploying_a_static_site/
{% endcomment %}
