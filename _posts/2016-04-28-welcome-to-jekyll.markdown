---
layout: post
title:  "Welcome to Jekyll! - como instalei Jekyll no Mac OS X El Capitan"
date:   2016-04-28 16:02:51 -0300
categories:
  - jekyll update
  - Mac OS X El Capitan
  - Ruby
  - Bundler
---

>You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.
<!--more-->
To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

>Jekyll also offers powerful support for code snippets:

>{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

>Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].


Esta é a postagem de exemplo que vem no pacote do Jekyll. Ela dá informações sobre o local das postagens no sistema de diretórios, o _script_ do Jekyll para servir a página localmente, como adicionar novas postagens, como incluir _snippets_ de código, e direciona para a documentação.

Jekyll foi fácil de instalar, uma vez superado o problema de instalar uma cópia de [Ruby](https://www.ruby-lang.org/pt/) que possa ser usada para desenvolvimento no Mac OS X El Capitan. O sistema da Apple vem com uma cópia de Ruby pré-instalada que não pode ser usada facilmente. A sua pasta de instalação padrão é ```/usr/bin```, a qual, juntamente com outras pastas do sistema, são protegidas pelo _System Integrity Protection_. Ele não permite a modificação destas pastas, nem mesmo por usuários logados como _root_. A melhor maneira é instalar **outra cópia** do Ruby, funcional. Para esse fim, usei um gerenciador de pacotes, o [rbenv](https://github.com/rbenv/rbenv#readme), o qual permite escolher a versão a ser instalada. Isso é importante, pois o Jekyll 3 depende do Ruby v2. Particularmente, no meu sistema, obtive melhores resultados com Ruby 2.2. Então, a instalação procedeu assim:

> ATENÇÃO! Antes é necessário ter instalado [XCode](https://itunes.apple.com/br/app/xcode/id497799835?mt=12) e [Command Line Tools](https://developer.apple.com/opensource/) para Xcode.

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

para instalar [Homebrew](http://brew.sh) um gerenciador de pacotes para Mac OS X que administra muito bem o problema das instalações e SIP.
```bash
$ brew update # faz o update do Homebrew
$ brew install rbenv # instala rbenv
$ rbenv init # inicializa
```

para instalar rbenv (e [ruby-build](https://github.com/rbenv/ruby-build#readme), o _script_ que permite a instalação de Ruby) e iniciá-lo.
```bash
$ rbenv install -l # lista versões disponíveis de Ruby
$ rbenv install 2.2.3 # instala a versão escolhida
```

para listar as versões disponíveis de Ruby e instalar a versão escolhida.

Ta da! Você pode checar sua nova instalação de Ruby:
```bash
$ which Ruby # local onde Ruby está instalado
$ Ruby -v # versão do Ruby
```

que, no meu sistema retorna:
```bash
/Users/Helder/.rbenv/shims/ruby
ruby 2.2.3p173 (2015-08-18 revision 51636) [x86_64-darwin15]
```

Assim, tenho uma cópia funcional de Ruby que me permite desenvolver e não necessitei mexer na instalação padrão do sistema! O próximo passo foi instalar o Jekyll. Como ele é uma _gem_ de Ruby, o ideal é usar o Bundler, um gerenciador de dependências de gems que permite instalações modulares, com configurações personalizadas para cada pasta-alvo.
```ruby
$ gem install bundler # instala Bundler
```

instala o Bundler. Depois, é necessário ir para o diretório desejado e criar um arquivo de configuração _Gemfile_. Como usei o [GitHub Pages](https://pages.github.com) para hospedar e servir o site, precisei antes criar um repositório do [Git](https://git-scm.com) e um _branch_ gh-pages (vide [instruções](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)).
```bash
$ git init /pasta/onde/vc/quer/seu/blog # cria a pasta com o repositório
$ cd /pasta/onde/vc/quer/seu/blog
$ git checkout -b gh-pages # cria o branch gh-pages e muda para ele
$ echo "source 'https://rubygems.org'
$ gem 'github-pages', group: :jekyll_plugins" >> Gemfile # cria o arquivo de configuração
$ bundle install # instala a gem com suas dependências
```

Note que a única gem que mandei o Bundler instalar foi [github-pages](https://github.com/github/pages-gem), que, ao ser configurada, vai pedir todas as dependências necessárias para manter um ambiente do Jekyll em sincronia com o GitHub Pages. Após a instalação, um arquivo ```Gemfile.lock``` é criado, contendo a configuração local. Na minha pasta ```/jekyll/ciencia-medica``` ficou assim:
```ruby
GEM
  remote: https://rubygems.org/
  specs:
    colorator (1.1.0)
    ffi (1.9.14)
    forwardable-extended (2.6.0)
    jekyll (3.2.1)
      colorator (~> 1.0)
      jekyll-sass-converter (~> 1.0)
      jekyll-watch (~> 1.1)
      kramdown (~> 1.3)
      liquid (~> 3.0)
      mercenary (~> 0.3.3)
      pathutil (~> 0.9)
      rouge (~> 1.7)
      safe_yaml (~> 1.0)
    jekyll-sass-converter (1.4.0)
      sass (~> 3.4)
    jekyll-watch (1.5.0)
      listen (~> 3.0, < 3.1)
    kramdown (1.12.0)
    liquid (3.0.6)
    listen (3.0.8)
      rb-fsevent (~> 0.9, >= 0.9.4)
      rb-inotify (~> 0.9, >= 0.9.7)
    mercenary (0.3.6)
    pathutil (0.14.0)
      forwardable-extended (~> 2.6)
    rb-fsevent (0.9.7)
    rb-inotify (0.9.7)
      ffi (>= 0.5.0)
    rouge (1.11.1)
    safe_yaml (1.0.4)
    sass (3.4.22)

PLATFORMS
  ruby

DEPENDENCIES
  jekyll
  rouge

BUNDLED WITH
  1.12.5
```

mostrando que o Bundler instalou o Jekyll e todas as outras gems necessárias. Por fim:
```ruby
$ bundle exec jekyll new # cria um novo template do Jekyll
```

E para servir localmente seu site e verificar pendências:
```ruby
$ bundle exec jekyll serve
```

Ao fim do processo, fiz um commit e um push para o repositório remoto do GitHub, o que automaticamente publicou a página na internet.

```bash
$ git add . # adiciona arquivos à monitoração do Git
$ git commit -am "publica página" # faz o commit dos arquivos adicionados
$ git remote add gh-pages https://github.com/usuario/meu_repo.git # adiciona um remote para fazer o push
$ git push gh-pages gh-pages
```



[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
