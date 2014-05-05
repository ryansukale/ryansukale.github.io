**[ < - Back To Home](http://ryansukale.github.io)**

## Wanderings and learnings : May 2014

If you are trying to do something similar and are facing issues, reach out to me via my contact details available at **[ryansukale.com](http://ryansukale.com)**.


### May 04
----
1. Had been busy writing my final project report and paper the past two days. Got back on track today and did some experimenting with marionettejs for bootnette. Turns out, the hash urls that backbone history listens to only get triggered if you run your application from a server. i.e. trying to test it by opening the file from your local hard drive does not work.
* I created visualization for nginx configuration and [here's the raw svg file](http://ryansukale.com/viz/nginx-multi-site-config.svg). When I finished it and opened it in the browser, none of the text was being rendered. Turns out that any text that you create by using a flow, i.e. dragging and dropping a block does not effectively render due to [some pending changes in the SVG spec](http://wiki.inkscape.org/wiki/index.php/FAQ#What_about_flowed_text.3F).

### May 01
----
1. Experimented integrating dustjs with Marionettejs. You need to use [this plugin](https://github.com/simonblee/marionette-dust). The [AMD version](https://github.com/simonblee/marionette-dust/blob/master/src/amd/backbone.marionette.dust.js). After integrating, you not only need to compile but also loadSource before you can actually use the template. And moreover, you use the template by name. This strategy makes you want to precompile and load all of your dust templates before usage. Still debating whether I should drop handlebars in bottnette. Most likely I will.
* Learnt that there is something called as [Duster.js](https://github.com/dmix/dusterjs) for managing dust templates. Gotta see what it does whatever it claims to do.
* Apparently you can easily associate a language with a file extension in sublime text by View->Syntax->Open all with current extension as.. Check [this SO question](http://stackoverflow.com/questions/8088475/how-to-customise-file-type-to-syntax-associations-in-sublime-2).
* Seems like someone else too was workign on creating [a starter kit](https://github.com/coombsj/RequireJS-BackboneJs-MarionetteJS-Bootstrap_Starter) similar to the one I made in bootnette. Glad to realize that I am doing it the right way!
* In backbone.router, I kept wondering, what the hell was controller.someMethod. [This slide](http://dmytroyarmak.github.io/codeangels-marionette-introduction/#/25) cleared it up for me. So you dont really need a Marionette controller. It works fine with a normal object with function exactly the way the mediator pattern works.
