---
layout: post
title:  "Novo layout do Jekyll para o blog"
date:   2016-09-05 12:00:00 -0300
tags:
  - Jekyll update
  - GitHub
  - Bundler
author: ffelix
lang: pt-br
ref:
---

Depois de migrar meu blog para o [GitHub Pages](https://pages.github.com){% include github_pages.html %}, usando [Jekyll](https://jekyllrb.com), resolvi alterar o layout da página. Busquei temas para Jekyll, encontrando uma [lista](http://jekyllthemes.org) grande. Depois de muita indecisão, escolhi o tema [Tufte-Jekyll](http://jekyllthemes.org/themes/tufte-jekyll/), de Clay Harmon, baseado no [CSS](https://github.com/edwardtufte/tufte-css) criado por Dave Liepmann e Edward Tufte{% include tufte.html %}.
<!--more-->


A instalação do tema foi relativamente tranquila, exceto pelo fato de que o autor criou algumas tags customizadas de [Liquid](https://shopify.github.io/liquid/){% include liquid.html %}, as quais, infelizmente, não são suportadas pelo GitHub Pages. Apenas troquei estas tags pelos códigos de exemplo da biblioteca tufte-CSS, em [HTML](https://github.com/edwardtufte/tufte-css/blob/gh-pages/index.html) e o resultado pode ser visto nesta postagem.

Consegui importar as postagens do blog [antigo](http://pharmak.blogspot.com) com um _script_ do Jekyll, o [jekyll-import](https://github.com/jekyll/jekyll-import/tree/v0.10.0), instalado como uma gem que adicionei no meu Gemfile. Devo dizer que essa foi a primeira vez que a documentação do Jekyll me deixou confuso, pois a utilização do importador de blogs não está atualizada nela. No repositório do GitHub existe um novo conjunto de instruções para as versões mais recentes do Jekyll.

Procurei, então, um código que me permitisse gerar uma página de marcadores (_tags_). Muitas soluções tinham problemas (tags Liquid customizadas!), e aquela que se adaptou em meu sistema foi a descrita nesta [postagem](http://pavdmyt.com/how-to-implement-tags-at-jekyll-website/). Com os códigos de Pavel Dmytrenko, consegui criar páginas temáticas específicas para um determinado marcador. Porém, para que minha página de marcadores fosse funcional, faltava uma coisa: filtrar os marcadores. Depois da importação do Blogger, eu tinha centenas de marcadores, a maioria com apenas 1 ocorrência. Para evitar que a página de marcadores ficasse lotada demais e impraticável, eu tinha que filtrar apenas os marcadores com um número ```n```de ocorrências. Depois de muitas tentativas, consegui resolver com Liquid:

```ruby
{% raw %}
{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign tag_words = site_tags | split:',' | sort %}

{% include taglist.html %}

<!-- Posts by Tag -->
<div style="max-width: 1200px;">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] }}{% endcapture %}
    {% if site.tags[this_word].size>9 %}<h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>{% endif %}
    {% for post in site.tags[this_word] %}{% if site.tags[this_word].size>9 %}{% if post.title != null %}
      <div>
        <span style="float: left;">
          <a href="{{ post.url }}">{{ post.title }}</a>
        </span>
        <span style="float: right;">
          {{ post.date | date_to_string }}
        </span>
      </div>
      <div style="clear: both;"></div>
    {% endif %}{% endif %}{% endfor %}
  {% endunless %}{% endfor %}
</div>  
{% endraw %}
```

Onde a introdução do filtro Liquid ```size``` permitiu escolher apenas os marcadores com 10 ou mais ocorrências no blog:

```ruby
{% raw %}
{% if site.tags[this_word].size>9 %} ... {% endif %}
{% endraw %}
```

Só queria mais uma coisa, marcadores em cada postagem! Novamente, peguei a sugestão de Pavel Dmytrenko e usei o [estilo de marcadores de Wouter Beeftink](http://codepen.io/wbeeftink/pen/dIaDH). Para isso, tive que cometer a ousadia de _retocar_ o arquivo ```tufte.css```. Copiei o código de CSS dos marcadores de Beeftink (exceto o referente ao body, pois queria manter a tipografia de Tufte) e colei no tufte.css (são pouco mais de 50 linhas).

```css
.tags {
  list-style: none;
  margin: 0;
  overflow: hidden;
  padding: 0;
}

.tags li {
  float: left;
}

.tag {
  background: #eee;
  border-radius: 3px 0 0 3px;
  color: #999;
  display: inline-block;
  height: 26px;
  line-height: 26px;
  padding: 0 20px 0 23px;
  position: relative;
  margin: 0 10px 10px 0;
  text-decoration: none;
  -webkit-transition: color 0.2s;
}

.tag::before {
  background: #fff;
  border-radius: 10px;
  box-shadow: inset 0 1px rgba(0, 0, 0, 0.25);
  content: '';
  height: 6px;
  left: 10px;
  position: absolute;
  width: 6px;
  top: 10px;
}

.tag::after {
  background: #fff;
  border-bottom: 13px solid transparent;
  border-left: 10px solid #eee;
  border-top: 13px solid transparent;
  content: '';
  position: absolute;
  right: 0;
  top: 0;
}

.tag:hover {
  background-color: crimson;
  color: white;
}

.tag:hover::after {
   border-left-color: crimson;
}
```

Uma pequena modificação aqui e acolá até ficar como eu queria, mas o básico foi esse. Por último, mudei o nome do blog de Pharmakon para Ciência médica e não médica (que era o subtítulo do velho blog). O interessante é que o velho blog recusou-se a se extinguir, pois caiu-me nas mãos um CLI para o Blogger e resolvi experimentá-lo. Mas isso é outra estória.
