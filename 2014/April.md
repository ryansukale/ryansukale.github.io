**[ < - Back To Home](http://ryansukale.github.io)**

## Wanderings and learnings : April 2014
### Apr 25
----
1. Setup my first user github pages for publishing this journal at [ryansukale.github.io](http://ryansukale.github.io/)

### Apr 24
----
1. Building [bootcamp](https://github.com/ryansukale/bootcamp) is gradually becoming more and more interesting. After reading a couple of posts here, here and here, I figured a way to setup Marionettejs modules such that they can be initialized in an requirejs style.
* You can get the [current module's name](https://github.com/jrburke/requirejs/issues/352) from within the module in requirejs by `module.id` 
* Faced a cool error `Module name has not been loaded yet for context:_`. This happens when you `require('moduleName')` a module that was not already loaded as part of the dependencies. As a solution, you use the `require([],function(){})` syntax instead. [Here's](http://stackoverflow.com/questions/21420449/requirejs-module-name-has-not-been-loaded-yet-for-context-but-only-for-some) an SO question that talks more about this problem.
* You dont need to require 'require' as a module. If you are using requirejs, you already have access to require from inside your module functions. When in doubt you can stil do it [this way](https://groups.google.com/d/msg/backbone-marionette/FCertEfVzxc/UClsKsSlb58J).
* Marionette application does not have a before:start event. Only modules have that. Damn it, i wasted so much time wondering what I was doing wrong.
* Was setting up the [enode](https://github.com/ryansukale/enode) project. And thats when I realized that many of the utilities like methodOverride, json etc now need to be imported as independent packages.

### Apr 23
----
1. Spent some time working on [bootcamp-dev](https://github.com/ryansukale/bootcamp/tree/dev) creating its first Marionette app module.
* The design is being heavily influenced by the [bbclonemail](https://github.com/davidsulc/structuring-backbone-with-requirejs-and-marionette)
* They have a cool submodule initializer in [bbclonemail.js](https://github.com/marionettejs/bbclonemail/blob/master/public/javascripts/bbclonemail/bbclonemail.js), the use of which I am yet to discover.
* That you can initialize a marionette aplication directly by using new `Marionette.Application()` instead of writing var MyApp = new `Backbone.Marionette.Application()`. Its so obvious. Why didn't I think of that!
* Found a cool slideshow on [structuring marionette with modules](http://www.slideshare.net/matt-briggs/marionette-structure-with-modules). Need to read up on this one while I continue designing.
* [Structuring scalable client side applications](http://johndavidmathis.wordpress.com/2013/04/23/structuring-scalable-client-side-applications/) - This is probably something that I will have to read while organizing the templates of my code. Alhtough its not intended for large scale apps, one might never know!
* I will probably have to perform some sort of [event aggregation within modules](http://lostechies.com/derickbailey/2012/04/03/revisiting-the-backbone-event-aggregator-lessons-learned/) after I figure out how to divide my code into moduled the Marionette way.
* The companion [speakerdeck slides](https://speakerdeck.com/backbonerails/little-opinions-big-possibilities-the-tools-and-patterns-for-building-large-scale-backbone-applications) for [Brian Mann's talk](https://www.youtube.com/watch?v=qWr7x9wk6_c) at [backboneconf 2013](http://backboneconf.com/). He shared a pretty interesting and sensible application structure.
* I always forget how to add a blank value at the top of a select field. [This SO](http://stackoverflow.com/a/18490908/226953) answer nails it. Another reason to create bootcamp components. Data and HTML tags need to be loosely bound, decoupled and configurable.



### Apr 22
----
1. Resumed reading [Addy Osmani's book on javascript patterns.](http://addyosmani.com/resources/essentialjsdesignpatterns/book/). 
* YUI has a cool feature that lets you define a hierarchy of namespaces even if the object tree in the namespace does not exist. e.g. by declaring an namespace as `YUI.namespace('level1.level2.level3');`, you can use it by writing `YUI.level1.leve2.level3` even if level1 and level2 were not defined before usage.
* Learnt and applied [markdown syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#lists) for creating ordered lists,headings.
* The number in markdown's ordered list's [does not really matter.](http://www.macdrifter.com/2012/04/writing-in-markdown-lists.html) But as a cool shortcut, if you replace the first item with a number, it automatically figures out that the remaining items are parts of the ordered list.
* There is a file permission like [rwxrwsrwx](http://arstechnica.com/civis/viewtopic.php?f=16&t=224137) in unix
    

### Apr 21
----
1. Read up a little bit on git rebase from [here](http://marklodato.github.io/visual-git-guide/index-en.html#rebase)
* When you generate ssh keys, if you dont use sudo, the keys are created for the current user. If you use sudo, the keys are created for the root user.
* This is an important thing to know because when you do git clone via ssh, you need to be using the correct user.
If you get a permission denied error on git clone, thats probably the reason why.[ref](https://help.github.com/articles/error-permission-denied-publickey)
* When you are [generating ssh keys using github](https://help.github.com/articles/generating-ssh-keys), and you run the command `sudo ssh-add ~/.ssh/id_rsa` and you get the error - 'Could not open a connection to your authentication agent.', you need to run the command  `` eval `ssh-agent -s` `` [ref](http://stackoverflow.com/questions/6565357/git-push-requires-username-and-password/18348125#18348125). You might also need to run `eval "$(ssh-agent)"` and maybe [this](https://coderwall.com/p/rdi_wq) too in case ssh-add is not recognized.
* Wrote my first piece of inline code in markdown.
* [How to sync a fork!](https://help.github.com/articles/syncing-a-fork) I haven't had to do it yet, but will probably have to do it quite often once I use my ghostblog over a long term and will need to integrate fixes from the core ghost project into my fork.
* Learnt [how to escape backticks in markdown](http://meta.stackexchange.com/questions/82718/how-do-i-escape-a-backtick-in-markdown)