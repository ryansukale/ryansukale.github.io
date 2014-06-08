**[ < - Back To Home](http://ryansukale.github.io)**

## Wanderings and learnings : May 2014

If you are trying to do something similar and are facing issues, reach out to me via my contact details available at **[ryansukale.com](http://ryansukale.com)**.

### May 22
1. In postgresql, User is a key word, so you cannot create a table by that name[Ref](http://www.postgresql.org/message-id/Pine.NEB.4.10.10008291649550.4357-100000@scimitar.caravan.com).

###May 21
1. Read up chapter 4 from Secrets of the Javascript ninja. Found it pretty cool actually. Plenty of brain twisters this time.
2. Refreshed my memory on the fact that all js objects have a constructor property. But I realized there is a really simple way to execute expressions when testing on the fly. For e.g. if you type `{}.constructor` on the console, you get an error. However, if you type `({}).constructor` it prints alright.
3. Also learnt that the Number class has a cool toString which lets you specify the radix. I had never actually had to use this before. E.g `(10).toString(16)`
4. Just as a note to self : Array.shift is the counterpart to Array.pop and Array.unshift is the counterpart of Array.push. They just work on the opposite ends of the array.
5. Revisiting Douglas Crockford's JS the good parts. That book never ceases to amuse me.


###May 20
1. Read Ch2, Ch3 on Secrets of the Javascript ninja. Didn't feel like they were a difficult read at all though. Looking forward to the next few chapters.

###May 19
1. Using PostgreSQL for the first time. Setup it up on a DigitalOcean vps and wrote a small blog post about it.


###May 18
1. Read about the Command Pattern, Facade Pattern, Factory Pattern and the Mixin pattern from [Addy's online book](http://addyosmani.com/resources/essentialjsdesignpatterns/book/).


# May 16
1. Learnt that there is a 'multiple' property the file input. It just never occured to me that this wasnt the default behaviour. [Learn more](http://davidwalsh.name/multiple-file-upload).
* The multiparty module is perhaps the simplest way to implement a file upload. You will need to regularly clean up your temp directory though when using multiparty. [Learn more](http://andrewkelley.me/post/do-not-use-bodyparser-with-express-js.html).
* Moved my personal website to digital ocean and converted it to a nodejs website.
* Learnt about the [forever command](http://blog.nodejitsu.com/keep-a-nodejs-server-up-with-forever/) to run if you need to run your node app continously, which is the case for me since I want my profile site to be running 24x7. Its not as if its is supposed to crash ever. It mainly just has some sugarcoated static content.
* If you need to environment parameters arguments for your program, you need to specify them before the forever command.


### May 15


### May 13
---
1. Found a good set of series on nodejs at [dailyjs](http://dailyjs.com/tags.html).
* Was trying to figure out how to send emails from your own server and domain using nodejs. There's a nodejs package called [nodemailer](http://documentup.com/andris9/nodemailer) that lets you do that..... well almost. You also got to install either of sendmail or postfix before you do that.
* SMPT servers listen on port 25. Your DO droplet does not come with an SMTP server installed. You can verify this by typing `telnet localhost 25`. If you get an error message saying that connection refused, you will need to install either sendmail or postfix.
* Lets say you installed sendmail using `sudo apt-get install sendmail`, and you then test it out using the command - 'telnet localhost 25', its will get you connected but the prompt never ends. You can end it by pressing `Ctrl+]`. That takes you to the telnet prompt. To get out fo that type `close` or `quit`. And thats how you come out of your telnet shell. [Telnet command reference](http://unixhelp.ed.ac.uk/tables/telnet_commands.html).
* [Here's](http://wiki2.dovecot.org/MailServerOverview) a niftly little overview of how email transfers take place and the roles of an MTA and and MUA.
* [Here's](https://www.digitalocean.com/community/articles/how-to-set-up-a-postfix-e-mail-server-with-dovecot) how you would set up a postfix email server with dovecot on an ubuntu droplet on digital ocean.
* If you just want to install postfix, just follow [these instructions](https://www.digitalocean.com/community/articles/how-to-install-and-setup-postfix-on-ubuntu-12-04).
* When you install sendmail, it automatically starts. To stop it, type the command - `sudo /etc/init.d/sendmail stop`. To restart it, use its counterpart - `sudo /etc/init.d/sendmail start`.
* Also read a bit about a powerful ORM solution for Nodejs - [Bookshelfjs](http://bookshelfjs.org/). I had used [sequelizejs](http://sequelizejs.com/) before but I wanted to explore something else this time. I had a use case where I needed to use a composite prmary key and Sequelize didnt do that for me so....
* Learnt a little bit about gruntjs for automating tasks. Yet to use it in a project, so I still need to face some real time hassles. The basic idea of grunt is pretty simple - create a grunt config file, specify certain tasks and their [configuration](http://gruntjs.com/configuring-tasks) and then run the grunt command. Here's a [sample grunt configuration](http://gruntjs.com/sample-gruntfile) file.
* Also found this cool [interactive explanation of package.json](http://package.json.nodejitsu.com/).
* Guess what, if you do `npm install --save modulename` it writes the module to your package.json dependencies along wit a version number. If you run `npm install --save-dev modulename` it add the module to your package.json in your devDependencies. Grunt and its plugins go inside devDependencies in your package.json
* Watched a simple video on nodejs [EventEmitters](http://nodetuts.com/03-event-emitter.html). Didnt find a major different from the the jQuery.on function. Its all the same so far. Nor sure if namespacing events is allowed though.
* Learnt about something called as a ** [screen session](http://nodeguide.com/beginner.html#quick-dirty-deployment). **
* Learnt about 3 critical grunt packages - * [grunt-contrib-uglify](https://github.com/gruntjs/grunt-contrib-uglify) * for minifying your js files, and * [grunt-config-cssmin](https://github.com/gruntjs/grunt-contrib-cssmin) * for minifying your CSS files and * [grunt-config-jshint](https://github.com/gruntjs/grunt-contrib-jshint) * for validating your javascript.
* Found a [nice cheatsheet](http://blog.nodejitsu.com/npm-cheatsheet/) on NPM.
* Came across [momentjs](http://momentjs.com/) . Found it to be pretty cool!.
* Watched the [breakpoint episode 4](https://www.youtube.com/watch?v=WpqZ0LjNU5A). So, it seems like the timeout for a jQuery animation does not sync up well with the browser refresh rate. And thats exactly you probably want to use the [jQuery-requestAnimationFrame plugin](https://github.com/gnarf/jquery-requestAnimationFrame) wherever applicable.



### May 12
---
1. Came across a neat [video on Marionettejs](http://vimeo.com/58797363) by Brian Mann on vimeo. It made me want to explore a bit more about the Marionettejs Views. The 3 different types of views- [ItemView](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.itemview.md), [CollectionView](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.collectionview.md) and the [CompositeView](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.compositeview.md) have a very specific purpose. They all inherit from the parent class [View](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.view.md).
* There also seems to be a [visual guide to Marionettejs](https://www.artandlogic.com/blog/2013/03/a-visual-guide-to-marionette-js-views/) although the visualization could use some help.
* Also learnt that Marionette provides a ui hash to quickly select sub-sections in your view. These can be used in two ways - as shown [here](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.itemview.md#organizing-ui-elements) in the onRender method and [here](https://github.com/marionettejs/backbone.marionette/blob/master/docs/marionette.view.md#viewevents) during event mapping.
* Also came across an interesting blog post comparing [angular vs ember vs marionettejs](http://www.keltdockins.com/2/post/2014/04/which-javascript-framework-to-use-angular-vs-ember-vs-marionette.html).


### May 09
----
1. Found a small but good [resource](http://www.jankoatwarpspeed.com/free-sketching-wireframing-kit/) with a few svg icons that can comein handy for wireframing.
* [A SO question](http://stackoverflow.com/questions/8484404/what-is-the-proper-way-to-use-the-node-js-postgresql-module) that basically talks about how one should use postgresql by the author of postgresql itself.

### May 08
----
1. Setup [node-inspector](https://www.npmjs.org/package/node-inspector) on my windows machine.
*  Installed mongodb on my windows machhine. Got it up and running.
*  Was reading a couple of tuts on using mongodb with expressjs. Came across this cool [mongoui](https://github.com/azat-co/mongoui) project which is a phpadmin like interface for mongodb. Also came across [monk](https://github.com/LearnBoost/monk).
*  Found [this article](http://webapplog.com/intro-to-express-js-simple-rest-api-app-with-monk-and-mongodb/) by the guy who wrote mongoui. [Here's](http://cwbuecheler.com/web/tutorials/2013/node-express-mongo/) another good tut on using expressjs with mongodb.
*  Learnt how to ~~strikethrough~~ text in markdown.


### May 07
----
1. Read up on the javascript mixin pattern and the javascript decorator pattern.

### May 06
----
1. Was reading about the promises from [this article](http://www.html5rocks.com/en/tutorials/es6/promises/). I remember doing similar stuff using jQuery deferreds a long long time ago, but did not really have a chance to look into the new implementation until now.
* There's a function called [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) on array objects in the ECMAScript 5 standard. Pretty cool.
* Read something about the revealing constructor pattern in [this blog post](http://domenic.me/2014/02/14/the-revealing-constructor-pattern/) by Domenic Denicola. Need to learn more about it.
* Came to know that there is something called as an [octopress](http://octopress.org/) blogging framework built upon jekyll. Also, this thing works with disqus and [here's and article](http://asaf.github.io/blog/2013/07/08/blogging-with-octopress-add-comments/) that tells you how to set it up.

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
