**[ < - Back To Home](http://ryansukale.github.io)**

## Wanderings and learnings : April 2014

If you are trying to do something similar and are facing issues, reach out to me via my contact details available at **[ryansukale.com](http://ryansukale.com)**.

### Apr 30
----
1. Working on bootnette, created a Marionette controller. Its still not a controller in its true sense. I still need to figure out an optimum strategy to create and initialize views, be it file structure or initialization.
* Used handlebars templates with Marionettejs views based upon [this SO](http://stackoverflow.com/questions/15703896/use-handlebars-js-with-backbone-marionette) question.
* David Sulc seems to have written a [nice companion project](https://github.com/davidsulc/marionette-gentle-introduction/) to his [book](https://leanpub.com/marionette-gentle-introduction). But the [index.html](https://github.com/davidsulc/marionette-gentle-introduction/blob/master/index.html) looks really ugly due to all of the script tags. At the moment, I am not entirely convinced that this is the best way to organize modules.
* Realized that the App is like the godfather object. Thats the reason why you define regions on the App. These regions are then used by the other modules to carry out their work.
* A backbone view does not work with an arbitrary JSON object as a model. You need to pass in a Backbone model, else the render function is not defined.
* [Marionette.View](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.view.md) is not supposed to be used directly. You gotta use the other subclasses like [Marionette.ItemView](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.itemview.md#marionetteitemview).
* Came across this [nifty little series](http://dailyjs.com/2012/11/29/backbone-tutorial-1/) from dailyjs for backbonejs.
* Read up a little bit on the [Marionette.AppRouter](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.approuter.md) object. Its one of the opcoming things to do in bootnette.
* There are two ways [1](http://www.php.net/manual/en/language.variables.scope.php) [2](http://www.php.net/manual/en/reserved.variables.globals.php) to declare globals in php. You will need to do this if you want to access global variables within your functions.

### Apr 29
----
1. After getting a feeling that I was simply overloading the simplicity of [bootcamp](https://github.com/ryansukale/bootcamp) by adding marionettejs to it, I decided to shift the marionettejs branch to a whole new repository. Marionettejs is really good for building large scale SPA and if you are simply creating a moderately sized application, you should not have to use all of the default setup of marionette objects. Hence is born - [bootnette](https://github.com/ryansukale/bootnette). A spin off from bootcamp which draws upon bootcamp and extends it for integration with marionettejs. I am not sure what this project will finally evolve into, but I hope it at least turns into a good chunk of reusable code and patterns that can be used in many marionettjs/bootstrap based SPA's.
2. The App in marionettjs is analogous to a globa object. Its all knowing, and is the place where you need to identify "regions". These regions are then passed around to controllers who are aware of what to display in those regions. However, as per [Brian Mann's](https://www.youtube.com/watch?v=qWr7x9wk6_c) brilliant video, it seems that the controller is meant to live within an app module and is the place where you would end up writing most of your code.
3. Integrated [handlebars](http://handlebarsjs.com/) into bootnette. Best practices guide that you should not emebed script like code in your markup. That makes underscore templating a big no no.
* MySQL does not have full outer join? huh!
* Had some trouble getting out an apostrophe from mysql. Apparently you gotta run the query `SET NAMES utf8` on your mysql database[ref](http://stackoverflow.com/questions/15097518/escaping-json-apostrophe-before-phps-json-encode-truncates). Now once you get the data out, you can use php json_encode to convert it to json and make sure that your client HTML character set is UTF-8. Only then will an apostrophe appear as an apostrophe.

### Apr 28
----
1. Attempted to [visualize OAUTH 2](http://ryansukale.com/viz/oauth.svg) . I found the articles [here](http://hueniverse.com/oauth/guide/workflow/) and [here](http://goo.gl/3kDzeZ) pretty useful.
* Switched from using Filezilla for connecting to Godaddy to WinSCP.
* Revised the [Mediator pattern](http://addyosmani.com/resources/essentialjsdesignpatterns/book/#mediatorpatternjavascript) since it was mentioned in the [Marionette Controller](https://github.com/marionettejs/backbone.marionette/wiki/Using-a-controller-to-change-content-in-a-marionette.layout) example.
* Also read about the [differences between a Region and a Layout](https://github.com/marionettejs/backbone.marionette/wiki/The-relationship-between-regions-and-layouts) and what they are intended for.
* I really love the way Marionette forces you to think modular.


### Apr 27
----
1. Continued work on [xnode](https://github.com/ryansukale/xnode). Realized that the new version of expressjs does quite a few things differently. E.g. as per [this blog post](http://andrewkelley.me/post/do-not-use-bodyparser-with-express-js.html), you are not supposed to use [bodyParser](https://github.com/expressjs/body-parser) middleware directly and suggests to use json and urlEncoded instead. These were old recommendations. The new bodyparser uses just json and urlencoded and therfore it is safe to use bodyParser again.
2. [This link](http://scotch.io/bar-talk/expressjs-4-0-new-features-and-upgrading-from-3-0#removed-bundled-middleware) has a neat table of all the middleware that you will now need to explicitly require for your application since express no longer depends on connect.
3. [Express router](http://expressjs.com/4x/api.html#router) seems to be much more neat.
4. When you test your REST API in Postman, just **remember** to use the xxx-form-urlencoded instead of form-data, or your POST data will not show up in req.body in express.
5. Expressjs has a pretty cool [History.md](https://github.com/visionmedia/express/blob/master/History.md) file. I added the same to [xnode](https://github.com/ryansukale/xnode).
6. An express router can take multiple callbacks as arguments before the actual handler function is executed. This is quite similar to middlware execution, except for the fact that it can be made more route specific. Within each callback, invoking next() calls the next callback, and calling next('router') skips the subsequent callbacks and directy calls the final handler.

### Apr 25
----
1. Setup my first user github pages for publishing this journal at [ryansukale.github.io](http://ryansukale.github.io/)
2. Said hi to markdown tables :)

### Apr 24
----
1. Building [bootcamp](https://github.com/ryansukale/bootcamp) is gradually becoming more and more interesting. After reading a couple of posts here, here and here, I figured a way to setup Marionettejs modules such that they can be initialized in an requirejs style.
* You can get the [current module's name](https://github.com/jrburke/requirejs/issues/352) from within the module in requirejs by `module.id` 
* Faced a cool error `Module name has not been loaded yet for context:_`. This happens when you `require('moduleName')` a module that was not already loaded as part of the dependencies. As a solution, you use the `require([],function(){})` syntax instead. [Here's](http://stackoverflow.com/questions/21420449/requirejs-module-name-has-not-been-loaded-yet-for-context-but-only-for-some) an SO question that talks more about this problem.
* You dont need to require 'require' as a module. If you are using requirejs, you already have access to require from inside your module functions. When in doubt you can stil do it [this way](https://groups.google.com/d/msg/backbone-marionette/FCertEfVzxc/UClsKsSlb58J).
* Marionette application does not have a before:start event. Only modules have that. Damn it, i wasted so much time wondering what I was doing wrong.
* Was setting up the [xnode](https://github.com/ryansukale/xnode) project. And thats when I realized that many of the utilities like methodOverride, json etc now need to be imported as independent packages.

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