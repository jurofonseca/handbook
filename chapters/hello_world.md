# Hello World: A Tutorial

In this tutorial, you will write a simple "hello world" web application in
Node.js, and then deploy it using `jitsu`, Nodejitsu's command line interface.

Before you get started, you should have both
[Node.js](http://nodejs.org/#download) and the
[Node Package Manager](http://npmjs.org/) (npm) installed.

<!--
A good idea would be to link to further resources on installing node and npm.
This may include the handbook appendices, nodedocs.org and/or particular pages
in the documentation for the projects.
-->

## Write A Server:

Let's start with a very basic node.js http server. Create a folder called
`myapp/` and then create a file inside the folder called `server.js` inside of
it with the following code:

     // requires node's http module
     var http = require('http');
     
     // creates a new httpServer instance
     http.createServer(function (req, res) {
       // this is the callback, or request handler for the httpServer
       
       // respond to the browser, write some headers so the 
       // browser knows what type of content we are sending
       res.writeHead(200, {'Content-Type': 'text/html'});
       
       // write some content to the browser that your user will see
       res.write('<h1>hello, i know nodejitsu.</h1>')
       
       // close the response
       res.end();
     }).listen(80); // the server will listen on port 80

That's all the code you'll need for starters.

## Deploy with `jitsu`:

There are three basic ways to deploy applications to Nodejitsu:

<!--Make sure that all these links point to the proper URLs-->
* `jitsu`, The Nodejitsu command line tool 
* The Nodejitsu [Web Application](http://develop.nodejitsu.com/), An easy to use
web interface for managing your applications
* The JSON [API](#Using_The_API)

[`jitsu`](http://github.com/nodejitsu/jitsu) is a
[Command Line Interface (CLI)](http://en.wikipedia.org/wiki/Command-line_interface)
for interacting with the Nodejitsu platform. It's open-source and easy to use.
We've designed Jitsu to be suitable for command line beginners, but still be
powerful and extensible enough for production usage. If you aren't a fan of the
command line or don't have terminal access you can still do everything `jitsu`
can do through the [Nodejitsu Web Application](http://nodejitsu.com).

In this tutorial, we use `jitsu` to deploy our "hello world" application. If
this is your first time deploying an application and you are eager to get
started, we recommend using `jitsu`; it has a one line installer, it's self-documenting, and with it you'll be able to deploy your app in seconds.

## Installation

In order to install `jitsu`, open a terminal and type:

     [sudo] npm install -g jitsu

<!-- Update this image!-->
![](https://github.com/nodejitsu/jitsu/raw/master/assets/jitsu.png)

This command will install `jitsu` on your system; the `-g` makes npm install it
globally.

After installation, run the `jitsu` command from your command line. Since it's
your first time using `jitsu`, you will be prompted to login with an existing
account or to create a new account.

<!-- Update this image?-->
<img src="https://github.com/nodejitsu/jitsu/raw/master/assets/login.png"/>

**Once you've logged in, you can deploy your app immediately.**

## One Line Deployment

Open a terminal:

<!-- Is /path/to/myapp the best way to say this? Probably. :( -->

    cd /path/to/myapp
    jitsu deploy

<!-- Expand! Run through the details of below, *assuming it's the first time*-->
This will create a new application snapshot, generate and or update project
metadata, and deploy the project in the current path to
[Nodejitsu](http://nodejitsu.com). If it's your first deployment, you'll be
prompted for some information such as *subdomain* and *start script* but it's
really easy and we promise it will only
take a few seconds.

<!--Consider this without the prior context of 'go here for support.'-->
Now just open up your favorite browser, and go to `yoursubdomain.nodejitsu.com`.
If everything has been set up correctly, then you, too, are on the path of
nodejitsu!
