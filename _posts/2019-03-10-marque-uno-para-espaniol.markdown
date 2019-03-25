---
layout: post
title:  "\"Marque uno para español\""
date:   2019-03-10 15:20:00 -0300
categories: es
---

Hace rato que quería escribir algunos posts en castellano.

Por más que quiera, escribir en inglés me requiere muchísimo más esfuerzo y eso hace que (a veces) termine sin escribir nada.

En el pasado había investigado para soportar múltiples idiomas en [Jekyll](https://github.com/jekyll/jekyll) y lo había encontrado _complejo_[^1].

Hoy estaba convencido en crear un blog nuevo _solamente_ en español y de la nada se me ocurrió usar las categorías que hay en los posts. Por ejemplo:


__un_blog_post.markdown__
```
---
layout: post
title:  "Marque uno para español"
date:   2019-03-10 15:20:00 -0300
categories: es jekyll
---
```

Lo único que hay que hacer ahora es encontrar una forma sencilla de filtrar los posts por categorías:

__index.html__
{% raw %}
```html
<ul class="post-list">
    {% for post in site.categories.en %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
</ul>
```
{% endraw %}

Con eso tenemos filtrados los posts en inglés que ya tenía escrito hace un tiempo.
Podemos hacer lo mismo para los posts en español creando un file `es.html` en el root muy parecido a `index.html`.

Lo bueno es que ese `es.html` va a ser interpretado por Jekyll como [http://betzerra.github.io/es](betzerra.github.io/es) 👌🏽

[^1]: [REPO: jekyll-multiple-languages-plugin](https://github.com/Anthony-Gaudino/jekyll-multiple-languages-plugin), [POST: Creating a Multilingual Blog With Jekyll](https://forestry.io/blog/creating-a-multilingual-blog-with-jekyll/)
