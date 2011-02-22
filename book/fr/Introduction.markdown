Introduction
=============

Qu'est-ce que Sinatra ?
-----------------------

Sinatra est un langage dédié (un DSL ou Domain Specific Language
en anglais) pour créer rapidement des applications web avec Ruby.

La liste de ses fonctionnalités est volontairement limitée ce qui
laisse au développeur le choix d'utiliser les outils qui lui
conviennent en fonction de l'application à développer.

Il n'est pas exigeant quant à l'application que vous développez,
si ce n'est que :

* Son langage de programmation soit le Ruby
* Elle utilise des URLs

Avec Sinatra, il est aussi facile d'écrire de petits utilitaires spécifiques
que des applications de grosse envergure. (Reportez-vous à la section
"Quelques Applications dans la vraie vie" plus loin dans cette introduction.)

_TODO_
You can use the power of various Rubygems and other libraries available for
Ruby.

Sinatra est particulièrement efficace pour expérimenter et prototyper de
nouvelles applications ou pour créer rapidement une interface pour votre code.

Ce n'est pas un framework Model-View-Contrôleur à proprement parler, mais il
associe directement une URL à du code Ruby et renvoie le résultat de ce code
en tant que réponse. De plus, il vous permet d'écrire des applications propres
et correctement organisées : en particulier en permettant de séparer les vues
du code de votre application.

Installation
------------

La façon la plus simple pour installer Sinatra est de passer par Rubygems :

    $ gem install sinatra

### Dépendances

Sinatra dépend du gem _Rack_ (<http://rack.rubyforge.org>).

Sinatra accepte plusieurs systèmes de template différents (il utilise la
librairie Tilt en interne pour supporter théoriquement tous les systèmes
de template existants en Ruby). Pour un fonctionnement correct, vous devez
installer les systèmes de template que vous souhaitez utiliser. Comme
système de template de départ, l'équipe de développement de Sinatra
conseille d'utiliser ERB (qui fait déjà parti de Ruby) ou d'installer HAML.

    $ gem install haml

### Pour les aventuriers

La toute dernière version de Sinatra est disponible via le référentiel
GitHub : **<http://github.com/sinatra/sinatra/tree/master>**.

_TODO_

You can use the _edge_ version to try new functionality or to contribute to the
framework.  You need to have Git version control software installed
(<http://www.git-scm.com>).  You could use either
[rake](http://rake.rubyforge.org/) or [bundler](http://gembundler.com/). Follow
these steps:

**Rake**

    gem install rake

1. cd where/you/keep/your/projects
2. git clone git://github.com/sinatra/sinatra.git
3. cd sinatra
4. rake install

**Bundler**
Alternatively you can use bundler (http://gembundler.com/).

    gem install bundler

To use edge sinatra with bundler, you'll have to create a gemfile listing
sinatra's dependencies; and other dependencies for your application. In your
application's root create your 'Gemfile':

    gem 'sinatra', :git => 'git://github.com/sinatra/sinatra.git'
    source 'http://rubygems.org/'

Here we use the gemcutter source to specify where to get Sinatra's
dependencies; alternatively you can use the git version, but that is up to you.
So now we can install our bundle:

    bundle install


L'application Hello World
-------------------------

Sinatra étant installé, que diriez-vous que d'écrire votre première
application ?

    require 'rubygems'

    # Si vous utilisez bundler, vous devez ajouter ces 2 lignes
    require 'bundler'
    Bundler.setup
    
    require 'sinatra'
    
    get '/' do
      "Hello world, it's #{Time.now} at the server!"
    end

Sauvegardez ce code dans un fichier hello_world.rb puis lancez votre
application par `$ ruby hello_world.rb` avant d'ouvrir
l'URL http://localhost:4567 dans votre navigateur.

Comme vous pouvez le constater, Sinatra ne vous oblige pas à mettre en place
une trop grosse infrastructure : une simple requête sur une URL entraine
l'évaluation d'un peu de code Ruby et renvoie un morceau de texte en réponse.
Tout ce que le bloc de code retourne est envoyé au navigateur.


Quelques applications dans la vraie vie
---------------------------------------

### Github Services

Github, qui offre l'hébergement de référentiels Git, utilise Sinatra au niveau
des hooks "post-receive", pour appeler des URLs/services spécifiques d'un
utilisateur chaque fois que quelqu'un fait un push vers son référentiel :

* <http://github.com/blog/53-github-services-ipo>
* <http://github.com/guides/post-receive-hooks>
* <http://github.com/pjhyett/github-services>

### Git Wiki

Git Wiki est un système de Wiki très simple basé sur par Sinatra et Git. Il
existe différents forks avec des fonctionnalités supplémentaires :

* <http://github.com/sr/git-wiki>
* <http://github.com/sr/git-wiki/network>

### Integrity

Integrity est une petite application d'intégration continue utilisant Sinatra
pour contrôler que votre code compile et passe ses tests unitaires et vous
prévenir en cas de problème :

* <http://www.integrityapp.com/>
* <http://github.com/integrity/integrity>

### Seinfeld Calendar

Seinfeld Calendar est une petite application amusante pour suivre vos
contributions à des projets open-source et afficher vos "streaks", c'est-à-dire
la succession des commits que vous avez réalisés :

* <http://www.calendaraboutnothing.com>
* <http://github.com/entp/seinfeld>


A propos de ce livre
--------------------

Ce livre considère que vous avez déjà quelques notions du langage de script Ruby,
que vous avez installé Ruby et que vous disposez d'un interpréteur Ruby.

Pour plus d'informations au sujet du langage Ruby, vous pouvez visiter les sites
suivants :

* <http://www.ruby-lang.org>
* <http://www.ruby-lang.org/en/documentation/ruby-from-other-languages/>
* <http://www.ruby-doc.org>
* <http://www.ruby-doc.org/core-1.8.7/index.html>
* <http://www.ruby-doc.org/docs/ProgrammingRuby/>

Besoin d'aide ?
---------------

La bande à Sinatra est petite, mais extrêmement amicale. Rejoignez-nous sur
IRC à irc.freenode.org dans #sinatra si vous avez la moindre question. C'est
quelquefois un peu long, alors laissez-nous le temps de répondre à vos
questions.