## Prior Requirements
 - [Web Fundamentals Track](http://www.codecademy.com/tracks/web)
 - [Python](http://www.codecademy.com/tracks/python)
 - [Website Hosting - Your Needs and Your Free Choices](http://www.codecademy.com/groups/html-projects/discussions/5167394881c2702060000d1f)
 - [What do I need to learn how to build a website?](http://www.codecademy.com/groups/html-projects/discussions/51e69fe27c82ca29510040c3#)

## 1. Introduction

Before reading this tutorial, it is important that you meet the prior requirements section. In this tutorial you will be introduced to some advance topics, and it is therefore very important that you understand the basics. 

For those of you who have read all the GUIDES previously recommended, you know that when the time comes to put your website online there are several options. This tutorial is going to introduce you on how to use one of the most powerful options in the market. If you are making a static website this information will be useful, however, if you are making a dynamic website than this tutorial is **a must read**. 

By the end of this tutorial, you should know how to answer the following questions:

 1. What is Google App Engine (GAE)?
 2. Why do I need to use GAE?
 3. How do I create a simple GAE website?
 4. How do I locally test a GAE project?
 5. How do I upload a GAE project?
 6. How do I make a GAE project available to the world?
 7. How can I improve the quality and organization of my website's code?
 8. Is GAE my only option? When should I use it?

## 2. What is GAE?

The [official documentation](https://developers.google.com/appengine/docs/whatisgoogleappengine) defines Google App Engine as the following:

> Google App Engine lets you run web applications on Google's infrastructure. App Engine applications are easy to build, easy to maintain, and easy to scale as your traffic and data storage needs grow. With App Engine, there are no servers to maintain: You just upload your application, and it's ready to serve your users.

In simple words, this means that GAE is an advanced hosting service for your websites and web applications. With this advanced hosting service, you merely code your website, deploy into to Google Cloud, and then you let them handle everything else. 

This is a very convenient thing: it means that all you have to do is to worry about coding your website or web application, upload your project to Google Servers and then let them worry about the maintenance.

Additional information:

 - [Google App Engine](http://en.wikipedia.org/wiki/Google_App_Engine)
 - [What is Google App Engine?](https://ep2013.europython.eu/conference/talks/google-app-engine-best-practices-latest-features)
 - [What is (isn't) Google App Engine?](https://developers.google.com/appengine/training/intro/whatisgae)


## 3. Why do I need GAE?

As previously stated, if you are making a dynamic website, this tutorial is a must read. This happens because GAE main strength is to provide everything you need for a dynamic website or web application. For this purpose, GAE's main features include:

- dynamic web serving, with full support for common web technologies
- persistent storage with queries, sorting and transactions, using a version of SQL for database queries
- automatic scaling and load balancing (starts as free but becomes paid later on)
- APIs for authenticating users and sending email using Google Accounts
- a fully featured local development environment that simulates Google App Engine on your computer
- task queues for performing work outside of the scope of a web request
- scheduled tasks for triggering events at specified times and regular intervals
- your own domain name (limited to GAE's standards)

GAE provides all of these features for free. So you if you starting and just want a nice place to host your website or your web application, this may be the solution you are looking for. However, if you start using too many resources, you will eventually need to  upgrade for a paid version.


Additional information:

- [What can I use the Google App Engine for?](http://stackoverflow.com/questions/4701139/what-can-i-use-the-google-app-engine-for)

## 4. GAE instalation and setup

Before we start with the live examples, we have to go through the proper set up of of GAE. Since we are going to work with the Python version, you should go to the [download page of GAE](https://developers.google.com/appengine/downloads) and download the Python SDK, depending on your operative system.


Before being able to use GAE, you have to install Python. This is where some steps may differ depending on your operative system. In this tutorial we are going to cover Windows and Linux. Windows is by far [the most common operative system used by our community](http://www.easypolls.net/poll.html?p=51bf6aa7e4b0604d061eee92), while Linux is shares simillarities with Mac and is a lot easier to access (it is free) and install. 

As a personal recommendation from the author, if you are making websites, you should use Linux instead of windows. Everything will be easier and faster, as you are about to see in the next chapters.

### 4.1 Installing on Linux

The main power of Linux is its terminal. Here we assume you are using one of the major Debian distributions, such as [Ubuntu or Mint](http://distrowatch.com/dwres.php?resource=major). If you are using a Red Hat distribution or any other, you simply have to adapt the commands of the terminal according to your distribution needs.

Before we can use GAE, we have to install python. To do that just open the terminal and type:

    sudo apt-get install python

And you are done.

Now that you have python installed, simply extract the zip file you have previously downloaded and you are ready to go. 

### 4.2 Installing on Windows

The first step is to intall Python on Windows. To do that visit the [download page on the official website](http://www.python.org/download/releases/) and choose the latest release compatible release with GAE. As of the moment of writting this tutorial, GAE supports only Python 2.7.x, so you need to download and install Python 2.7.6 via the MSI insaller.

Once Python is installed, you have to install and configure GAE for Windows. Run the MSI installer you have previously downloaded from GAE website. Once you have it installed, click the shortcut on the Desktop (or open it in any other way). When running GAE for the first time, **you are likely to see an error**.  

![GAE_error](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/fc0ab9e8da49632cd5596484950313cebee0a038/GAE-tutorial/GAE_error.png)

This is normal, in Linux GAE works out of the box (no configuration is needed) but in Windows you have to manually configure it in order to work properly. To correctly configure GAE on Windows, go to the menu Edit -> Preferences. There you have to point GAE the correct paths of everything it uses: Python executable, the GAE folder and your prefered text editor. This is my personal configuration:

![GAE_configuration](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/fc0ab9e8da49632cd5596484950313cebee0a038/GAE-tutorial/GAE_configuration.png)

In my personal configuration, I use the default paths for Python and GAE. As an editor I am using Notepad++ but you can use anything you want. The last is left empty on purpose, as they recommend in the description.

Once you have done these configurations, GAE should work properly. When you close GAE you will see a message saying that errors occurred, but that is fine (erros occurred when you opened GAE for the first time without having it configured and now GAE is saving that into a log, in case you need help for future reference), if you didn everything as described, you should never see errors like that again.

If you have more problems installing GAE on Windows, the following information may help:

 - [AppEngine-Install-Windows](http://www-personal.umich.edu/~csev/books/gae/handouts/AppEngine-Install-Windows.pdf)
 - 

## 5. GAE quick introduction  and Hello World

## 5.1 Basic commands and actions

To effecttively use GAE you must know how to create projects, run them localy and then uploadload them to the cloud. These sections will give you a brief introduction to those basic commands. For more information feel free to check the offficial documentation.

### 5.1.1 How to use GAE Linux

Creating a project in GAE is very simple. Inside your `google_appengine` folder, you have a folder called `new_project_template`. Simply create a copy of that folder inisde the `google_appengine` folder, change its name and you are ready to go.

For running and uploading your project however, there are 2 basic command you have to know:

1. To launch the local server. This will host your project in localhost:8080. This is an essential feature to test your application before deploying it to the servers. You can kill the server by closing the terminal or pressing CTRL+C: `python dev_appserver.py projectFolderName/` 
2. To deploy your project to Google servers. Use this command once you are done working and are ready to make your project available to the world: `python appcfg.py update projectFolderName/`

If you are new to Linux, I suggest you learn a few more terminal commands:

 - [Common Linux Commands](http://www.dummies.com/how-to/content/common-linux-commands.html)
 - [50 Most Frequently Used UNIX / Linux Commands (With Examples)](http://www.thegeekstuff.com/2010/11/50-linux-commands/)
 - [Switching From Windows to Nix or a Newbie to Linux – 20 Useful Commands for Linux Newbies](http://www.tecmint.com/useful-linux-commands-for-newbies/)
 
If this looks too much do not worry. The one command you will be using most of the time is the `cd foleNamer` command. All the others are nice to know, but you do not require them, you can just use the user interface.

### 5.1.2 How to use GAE Windows

To create a project in Windows using GAE simply go to `File -> Create New Application`. Then give a name to your application, **in lower case and without spaces between**. In fact, to be more precise, the name of your application must obey to the regular expression `r'^(?:(?:[a-z\d\-]{1,100}\~)?(?:(?!\-)[a-z\d\-\.]{1,100}:)?(?!-)[a-z\d\-]{0,99}[a-z\d])$`. Creating an application with a name that does not obey this regular expression will keep you from successfully launching your local server, thus keeping you from testing your app, as described in [this stackoverflow discussion](http://stackoverflow.com/questions/20378641/cannot-run-hello-world-on-google-app-engine-windows/20379156?noredirect=1#20379156).

After giving a proper name to your application, select a place to save it and, remember to write down the selected port, so you can later see your application in the browser:

![create_app_windows](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/fc0ab9e8da49632cd5596484950313cebee0a038/GAE-tutorial/create_app_windows.png)

In my case, I created an application with the name of hellowworld-windows, saved it in my desktop folder and decided to use the default port of 8080. This will be important later on.

To run the application in windows, simply select the project you wish to run, and click the `Run` button. Once the server is running you can visit your web app working by opening your browser and typing localhost:portNumber. In my case I would have to type localhost:8080. Alternativily, you can also just click on the `Browse` button, but it is important to remember how you can use the browser so you can test your website or web application in different browsers.

To stop the server press the `Stop` button. If for some reason your app explodes or crashes, you can click the `Log` button to see the error output and search for help. To deploy your application to Google's severs press the `Deploy` button. The `Edit` button will open the `main.py` file in your selected word processor (mine is Notepad++) and the button `Dashboard` will open your browser in the Google App Engines configure webapge.

## 5.2 Project Architecture

Although the ways in which you create, run and update projects differ from opertaive system (OS) to operative system, the architecture of a GAE project is the same no matter what.

Before we start you should try to create a project and explore it. In GAE, the simplest of apps has two main files: 

- app.yaml: this is your configuration file. In this file you define the python libraries and templates that you want to use, the version of python, and other important information such as the application ID or which file the server should run by defualt. For more information, visit the [detailed information page](https://developers.google.com/appengine/docs/python/config/appconfig).
- main.py: by default, this is the python program that Google servers will run and watch. This is where you place the logic of your web application or any queries you need to perform for your dynamic website.

The rest of the files, an icon and an auto-generated file are not important.

## 6. Coding your projects

As previously said, GAE is also useful for hosting your static websites. In this tutorial we will present two examples in Python:

1. Hello World - a simple example of how to deploy a purely static website with GAE.
2. Give me Randoms - a more complex example, that requires the server to make a dynamic computation before returning the page to the client.

Chapter 6.1 focuses on the first example. Through it you will learn how to test your web site or web app localy, register it in GAE and upload it to Google servers so you can effectively host it and make it available to the world.

In chapter 6.2 we go further, introduce the reader to templates and more advanced tools required to make dynamic websites and we also create an example, `Give me Randoms` that builds upon the knowledge gained in the previous chapter. 

Google App Engine supports a multitude of programming languages, such as Python, Java, PHP and Go, however, for the purposes this tutorial you will be using Python. Why Python? Python was selected so your learning process could be as easy and integrated with CodeCademy as possible. CodeCademy already has courses on Python, which you can master. Another reason is that PHP and Go are still experimental, and therefore not recommended. Last but not least, even though Java is a best choice for most apps, at the moment of writting of this tutorial, CodeCademy lacks any courses in Java, and teaching it in this tutorial would be confusing and out of scope.

### 6.1 The basics in action, Hello World 

This is a very simple example that is going to server as introduction on how you can make GAE display your html files once a certain URL is visited by a client. If you 

#### 6.1.1 Creating your project

First, create a new project. In that new project, create an `hello.html` file with the following content:

    <!DOCTYPE html PUBLIC "-//IETF//DTD HTML 2.0//EN">
    <HTML>
       <HEAD>
          <TITLE> A Small Hello </TITLE>
       </HEAD>
        <BODY>
           <H1> Hello World! </H1>
           <P>This is very minimal "hello world" HTML document.</P>
        </BODY>
    </HTML>


By now you should have the following files inside your folder:

    gae-hello-world-project/
          ├── app.yaml      (configuration file)
          ├── hello.html    (our html page)
          ├── main.py       (python server code)
          ├── favicon.ico   (random icon)
          └── index.yaml    (auto generated file)

In this simple example, we are going to display this every simple HTML file to our users. However this will not happen by magic. When a client first contacts with our server, the server runs the `main.py` file to know what to do with the client's request.  

Therefore, we must now change the `main.py` file so it can show the client the HTML we have created:

    import webapp2

    html = open('hello.html', 'r').read()

    class MainHandler(webapp2.RequestHandler):
        def get(self):
            self.response.write(html)

    app = webapp2.WSGIApplication([('/', MainHandler)], debug=True)

In this example we read our `hello.html` file and place it into a string called `html`. Then when the server receives a request from a client to the address `/` it runs the `get` method from the `MainHandler` class. The `get` method then responds to the client by telling it to render the HTML file we have created.

#### 6.1.2 Testing your app

Now that the application is created, we have to test if it works. For this purpose we need to run a local server and check if everything is OK. A quick revision of chapter 5 is advised

If you are using Linux, just enter GAE's folder, launch a terminal and type the command `python dev_appserver.py gae-hello-world-project/`. As tip, when typing the names of folders and files, you can use the terminal's auto complete feature by pressing the TAB key. 

If you are using Windows, select the project and press the `Run` button.

Now that you have launched the server, you can access your website by launching your preferred browser, and typing in the address bar `localhost:8080` (8080 is the default port for both cases if you did not change it).

If you have any errors, remember to check the terminal (Linux) or the Logs (Windows). 

#### 6.1.3 Registering your app

Before uploading your project to the Google servers you must first register it. To do this you need to have a google account, so if you do not have one, feel free to create one now.

When registering an application you must give it a unique ID. You can later delete this ID if you want, but **once an ID is used, it can never be used again (even if you delete it)**. To register you application go to:

 - [https://appengine.google.com/](https://appengine.google.com/)

Then go to `Create Project` and give it a name. Google will auto-generate a unique ID, but you can change that to anything you want as long as it is unique. Remember this unique ID as you will have to use it later!

Now that you have registered you app in Google, you have to edit the `app.yaml` file, and place the unique ID you have selected in the application field. As an example, this is what my `app.yaml` file looks like right now:

    application: mineral-style-421
    version: 1
    runtime: python27
    api_version: 1
    threadsafe: yes

    handlers:
    - url: /favicon\.ico
      static_files: favicon.ico
      upload: favicon\.ico

    - url: .*
      script: main.app

    libraries:
    - name: webapp2
      version: "2.5.2"

As you can see my unique app ID is "mineral-style-421". 

#### 6.1.4 Uploading your app

Now that you have registered your app in google and have edited all the configuration files, it is time to make your application available to the world and upload it to Google Servers. 

If you are on Linux, use the command `python appcfg.py update gae-hello-world-project/`, enter your e-mail and passowrd and see the magic happen. For more information you can always re-visit chapter 5.1.1.

In my case, my website is [http://mineral-style-421.appspot.com/](http://mineral-style-421.appspot.com/), you can click it and check it by yourself !

In Windows, click the `Deploy` button and follow along as well. For more information re-visit chapter 5.1.2.

After this step, your app should be freely available at the  http://your-app-id.appspot.com/ address. And that is it! 

### 6.2 Going Further, Give me Randoms

In the previous section we saw how to develop and deploy a basic static GAE project. This is what you would normaly do by hosting a static website. Now we are going to introduce you to more advanced capabilities. Imagine that you have a website that generates random numbers, and each time a client accesses your server, the client wants a set of unique random numbers. 

To achieve our goal, our server will have to compute those numbers, and then present them to the client. It is important that you realize that this computation could be anything dynamic, like accessing a database, computing a set of results from data the client gave you, or even access services provided by other applications and websites.

#### 6.2.1 Using Templates or Frameworks

This project could be all done in one single file, as some people do. However, Dynamic websites or web apps like the one we are going to present you, tend to get very complex very fast. Thus it is of the utmost importance to start learning good practices from the beginning - you will never make a decent project in only a single file.

Therefore, in this section we will present you to one of the most well known Python Templates for web development ([Jinja2](http://jinja.pocoo.org/docs/)) and we are going to build our example based on the knowledge from the previous section, and on Jinja2.

Templates are engines less complex than frameworks, but with more power. This extra power comes in the form of being able to better customize your website or app to your needs, however this is achieved at the cost of high learning curves and they usually have less funcionality and are less user friendly than frameworks. 

When building a website or web app you are not forced to use Jinja2. There are plenty of other template engines for python web development:

 - [https://wiki.python.org/moin/Templating](https://wiki.python.org/moin/Templating)
 
And if you prefer a more user friendly solution, you can also try one of the many python frameworks:

 - [https://wiki.python.org/moin/WebFrameworks](https://wiki.python.org/moin/WebFrameworks)


For this simple example however, using a complex framework would be overkill, and Jinja2 has a good mixture of power and simplicity that we need, not to mention a strong community as well. 

#### 6.2.2 Creating your project

#### 6.2.2.1 Folder structure 

First you need to create a project like in the first example. Then, create a folder named `html`, which will have all of your HTML files, and inside it create:

 - error.html : used when your request makes no sense
 - numbers.html : normal scenario where you display the random numbers to the client

By now, your folder should have the following structure:

    give_me_randomds/
        └── html      
            ├── numbers.html                 
            └── error.html    
        ├── app.yaml      
        ├── main.py       
        ├── favicon.ico   
        └── index.yaml    

#### 6.2.2.2 main.py

Because of the dynamic nature of our project, our `main.py` will be more complex:

    import webapp2
    import random
    import jinja2
    import os
    
    template_dir = os.path.join(os.path.dirname(__file__), 'html')
    jinja_env = jinja2.Environment(loader = jinja2.FileSystemLoader(template_dir))

    class Handler(webapp2.RequestHandler):
        def write(self, *a, **kw):
            self.response.out.write(*a, **kw)
    
        def render_str(self, template, **params):
            t = jinja_env.get_template(template)
            return t.render(params)
      
        def render(self, template, **kw):
            self.write(self.render_str(template, **kw))

    class RandomGenerator(Handler):

        def get(self, num_type, quantity_str, min_bound_str, max_bound_str):
     
            quantity = int(quantity_str)
            min_bound = int(min_bound_str)
            max_bound = int(max_bound_str)

            error_msg = ""

            if(quantity <= 0):
                error_msg += "quantity must be > 0 "
        
            if(min_bound > max_bound):
                error_msg += "min must be <= to max"

            if(error_msg != ""):
                self.render("error.html", error=error_msg)
                return

            randomList = []
            if(num_type == 'int'):
                for x in range(0, quantity):
                    randomList.append(random.randint(min_bound, max_bound))    	
            elif(num_type == 'float'):
                for x in range(0, quantity):
                    randomList.append(random.uniform(min_bound, max_bound))
        	
            self.render("numbers.html", list=randomList, quant=quantity, type=num_type, min_val=min_bound, max_val=max_bound)

    app = webapp2.WSGIApplication([('/type=(int|float)/quant=(\d+)/min=(\d+)/max=(\d+)', RandomGenerator)], debug=True)

So chew on this complexity let us take it by parts.

    import webapp2
    import random
    import jinja2
    import os
    
    template_dir = os.path.join(os.path.dirname(__file__), 'html')
    jinja_env = jinja2.Environment(loader = jinja2.FileSystemLoader(template_dir))
    
In this first part we take care of the imports needed (notice we import jinja2). Then we tell the operative system to mark our `html` folder, and in the last line we tell jinja2 to load it. From now on, every time we need to refer to an HTML file, all we have to do is write its name and jinja2 will look for an HTML file with that name inside the `html` foler.


    class Handler(webapp2.RequestHandler):
        def write(self, *a, **kw):
            self.response.out.write(*a, **kw)
    
        def render_str(self, template, **params):
            t = jinja_env.get_template(template)
            return t.render(params)
      
        def render(self, template, **kw):
            self.write(self.render_str(template, **kw))

This second part is the hardest. Since I assume your are a beginner in this area I will not explain it in detail because it makes uses of pyhton advanced knowledge that is out of the scope of this simple tutorial, however you should know that this class will allow you to send information to the HTML files you need in order to dynamically generate them with any number of arguments you may need.

    class RandomGenerator(Handler):

        def get(self, num_type, quantity_str, min_bound_str, max_bound_str):
     
            quantity = int(quantity_str)
            min_bound = int(min_bound_str)
            max_bound = int(max_bound_str)

            error_msg = ""

            if(quantity <= 0):
                error_msg += "quantity must be > 0 "
        
            if(min_bound > max_bound):
                error_msg += "min must be <= to max"

            if(error_msg != ""):
                self.render("error.html", error=error_msg)
                return

            randomList = []
            if(num_type == 'int'):
                for x in range(0, quantity):
                    randomList.append(random.randint(min_bound, max_bound))        
            elif(num_type == 'float'):
                for x in range(0, quantity):
                    randomList.append(random.uniform(min_bound, max_bound))
        	
            self.render("numbers.html", list=randomList, quant=quantity, type=num_type, min_val=min_bound, max_val=max_bound)
            
This is where all the logic of the program is stored. The `RandomGenerator` class inherits all the methods from the `Handler` class we hve seen previously. Its method, `get(...)` takes an interesting number of parameters. If you have been paying attention, you have probably remembered that our `get(self)` method from our Hello World example took no parameters. This method however expects parameters provided in the URL. We will get to that in shortly, but for now just assume that this `get(...)` methods is receiving those parameters.
    
    quantity = int(quantity_str)
    min_bound = int(min_bound_str)
    max_bound = int(max_bound_str)

In this method, we first convert all the paremeters into numbers. We have to do this because all of the paremeters are originally passed to our `get(...)` method as strings.

    error_msg = ""

    if(quantity <= 0):
        error_msg += "quantity must be > 0 "
        
    if(min_bound > max_bound):
        error_msg += "min must be <= to max"

    if(error_msg != ""):
        self.render("error.html", error=error_msg)
        return

Then we check to make sure that our input makes sense, and we change our `error_msg` accordingly. In the end, if the error message is empty, it means we can go on and that everything is OK, if not then we render the `error.html` file and we pass it our `error_msg` as a variable for it to display to the client. Because we are passing information to the HTML in real time, this means that the HTML file will be dynamicaly generated, and thus it has some interesting properties we will discuss once we finish reviewing the `main.py` file.
Finally, once we render the error page, we exit the `get(...)` method by returning nothing.


    randomList = []
    if(num_type == 'int'):
        for x in range(0, quantity):
            randomList.append(random.randint(min_bound, max_bound))        
        elif(num_type == 'float'):
            for x in range(0, quantity):
                randomList.append(random.uniform(min_bound, max_bound))
            
    self.render("numbers.html", list=randomList, quant=quantity, type=num_type, min_val=min_bound, max_val=max_bound)
          
The last part of our `get(...)` method is the success case. Here everything is as it should and so we simply create a list of random numbers that can either be of type `int` or `float`. The interesting part however, is the last line. This last line will dynamically render our `numers.html` by passing it the list we have just generated, as well as all the other inforamtion. 
          
    app = webapp2.WSGIApplication([('/type=(int|float)/quant=(\d+)/min=(\d+)/max=(\d+)', RandomGenerator)], debug=True)
    
And finally, the last line of our file, is the most important. This one line does many things for us:

 - **'/type=(int|float)/quant=(\d+)/min=(\d+)/max=(\d+)'**, This regular expression defines the address of our application. If you are new to regular expressions I strongly recommend some reading on the matter, as they will haunt you in your web developer carrier:
    - [Regular expression operations](http://docs.python.org/2/library/re.html)
    - [Python Regular Expressions](http://www.tutorialspoint.com/python/python_reg_expressions.htm)
 - `, RandomGenerator)]`, this part means that the class RandomGenerator will answer to requests that obey the previously mentioned regular expression.
 
This means that the only way to access this website, is by using a type of address, like the following:

 - http://localhost:8080/type=float/quant=10/min=10/max=20
 
Where `localhost:8080` is replaced by your website location. What happens if I do not type all the parametersor type a wrong number type? In such a case, your link will not obey to the regular expression, and you will receive a 404 Not Found answer from the server. If however, you type conflicting values for quantity, minimum or maximum, then you get redirect to the error page.

#### 6.2.2.3 error.html

    <!DOCTYPE html PUBLIC "-//IETF//DTD HTML 2.0//EN">
    <HTML>
      <HEAD>
        <TITLE> Give me Randoms </TITLE>
      </HEAD>
      <BODY>
        <H1>Error: {{error}}</H1>
        <p>Correct usage is: /type=(int|float)/quant=(\d+)/min=(\d+)/max=(\d+)</p>
      </BODY>
    </HTML>

This is a normal HTML file ... except for one line:

    <H1>Error: {{error}}</H1>

In the previous section we analysed how the `main.py` file sends information to the `error.html` file to dynamically generate it:

    if(error_msg != ""):
        self.render("error.html", error=error_msg)
        return

That `{{error}}` part in the HTML file is how jinja2 inputs the information you have created in your `main.py` file. The next example (` numbers.html`) will also make use of this jinja2 feature, but in a more complex way.

#### 6.2.2.4 numbers.html

    <!DOCTYPE html PUBLIC "-//IETF//DTD HTML 2.0//EN">
    <HTML>
      <HEAD>
        <TITLE> Give me Randoms </TITLE>
      </HEAD>
      <BODY>
        <H1>Asked for {{quant}} {{type}} Random Numbers between {{min_val}} and {{max_val}}</H1>
    
        <table border="1">
          {% for num in list %}
            <tr>
              <td>{{num}}</td>
            </tr>    
          {% endfor %}
        </table>

      </BODY>
    </HTML>

This file has two interesting sections as well:

    <H1>Asked for {{quant}} {{type}} Random Numbers between {{min_val}} and {{max_val}}</H1>

This line follows the same strategy explain in the previous section. Here we replace `{{xxx}}` with the value of the variable passed in `main.py`.

The second part, is more interesting:

    <table border="1">
        {% for num in list %}
        <tr>
            <td>{{num}}</td>
        </tr>    
        {% endfor %}
    </table>

Here the important thing is the ``{% for num in list %}` ... `{% for num in list %}` block. In Jinja2, when you want to insert pieces of Pyhton code inside your HTML you do it by using the `{% something_pyhtonic %}` code. In this case, we are accessing the variable `list` and we are repeating the:

    <tr>
        <td>{{num}}</td>
    </tr>

block for each number that `list` has. This way we generate the HTML file that the client will see dynamicaly. The true power of template engines like Jinja2 lies in this kind of operations. 

Now that you have completed the main files of the program you can run it localy and everything should work. The next section will focus onthe configuration files needed for your project to run on Google Cloud servers.

#### 6.2.2.5 app.yaml

    application: new-project-template
    version: 1
    runtime: python27
    api_version: 1
    threadsafe: yes

    handlers:
    - url: /favicon\.ico
      static_files: favicon.ico
      upload: favicon\.ico

    - url: .*
      script: main.app

    libraries:
    - name: webapp2
      version: latest
    - name: jinja2
      version: latest

So far you have been creating your project and testing it localy. Now you need to complete the configuration file so you can host your project in Google's servers. Just like before, you need to **Register** your project before you can upload it. Now is a good time to revisit the section 6.1.3 and section 6.1.4 if you need.

Before uploading it is important to notice a critical difference in the `app.yaml` file:

    libraries:
    - name: webapp2
      version: latest
    - name: jinja2
      version: latest
      
Because we are using Jinja2, and Google hosts it as well, we can specify in our file that we are using it. This way our project will always use the latest version of Jinja2. 

Now just upload your project and you are ready to go!

#### 6.2.3 Using Google Cloud SQL

In the previous secion you were introduced to a simple example that calculates a list of numbers upon a request, and then dynamicaly completes an HTML file with the generated numbers. This is the example of a logical operation. However, most of the time, you will use behaviour like this not to do computations, but to modify and read databases. 

Databases keep the information you require to run your website, they save anything from usernames and passwords to products and prices. GAE has its own language to query a database, a sub domain of the SQL language, called Google Cloud SQL (GC-SQL). GC-SQL has some differences from SQL; but if you are new to it do not worry, learning a simillar language like [MySQL](http://www.mysqltutorial.org/) or [postgresSQL](http://www.postgresql.org/docs/8.0/static/tutorial.html) is easy due to the amounts of tutorials and information available in the Internet and it surely helps understand GC-SQL better because the differences are minimal.

A section or even a chapter on GAE accessing and using Databases however would be huge, and would be more then enough for yet another tutorial. Thus, we do not cover GC-SQL, but we strongly advise you to read Google's documentation on the matter and to learn it, as it is a crucial tool for any web application or dynamic website:

 - [Google Cloud SQL](https://developers.google.com/cloud-sql/)
 - [Getting Started with Google Cloud SQL ](http://www.youtube.com/watch?v=_kQXgjIfLgo)
 - [Google Cloud Platform tutorial](http://www.youtube.com/watch?v=_kQXgjIfLgo)

## 7. Google App Engine Competition

Before going in a **very broad** discussion of GAE competition I want to introduce you to a few main engineering concepts:

 - **IAAS**: Infrastructure as a Service. In this case, a provide offers you his servers, hardware and physical material for you to work on. 
 - **PAAS**: Platform as a Service. The provider offers you servers running a specific software platform that you can then configure and use at your own will.

These definitions are simple, if you wish for a more detailed and formal definition, I suggest the following literature:

 - Definitions of IaaS:
     - [Infrastructure as a Service (IaaS) - searchcloudcomputing](http://searchcloudcomputing.techtarget.com/definition/Infrastructure-as-a-Service-IaaS)
     - [Infrastructure as a Service (IaaS) - techopedia](http://www.techopedia.com/definition/141/infrastructure-as-a-service-iaas)
     - [What is IaaS? - interoute](http://www.interoute.com/what-iaas)
     - [What is Infrastructure as a Service (IaaS) ? - building clouds](http://blogs.technet.com/b/privatecloud/archive/2012/04/04/what-is-infrastructure-as-a-service-iaas.aspx)
     - [Infrastructure as a Service (IaaS) - gartner](http://www.gartner.com/it-glossary/infrastructure-as-a-service-iaas)
 - Definitions of PaaS:
     - [Platform as a Service (PaaS) - search cloud computing](http://searchcloudcomputing.techtarget.com/definition/Platform-as-a-Service-PaaS)
     - [Platform as a Service (PaaS) - techpedia](http://www.techopedia.com/definition/147/platform-as-a-service-paas)
     - [Platform as a Service (PaaS) - gartner](http://www.gartner.com/it-glossary/platform-as-a-service-paas)
     - [What Is Platform as a Service (PaaS)? - dzone](http://cloud.dzone.com/articles/what-platform-service-paas)
     - [PaaS - Webopedia](http://www.webopedia.com/TERM/P/PaaS.html)     
 - Extra:
     - [Cloud computing - wikipedia](http://en.wikipedia.org/wiki/Cloud_computing)
     - [What is SAAS , PAAS and IAAS ? With examples - stackoverflow](http://stackoverflow.com/questions/16820336/what-is-saas-paas-and-iaas-with-examples)
 
Now you may be wondering why I am introducing you to these definitions. The thruth is that to know what actually competes with GAE, you have to understand it first. GAE is follow the **PaaS** model, thus when comparing other services (like Amazon Web Services, aka AWS, which follow the IaaS model) you have to know if you are not comparing oranges with aples. 

When building a web app or website, you have a long model of choices. The main competitors with GAE in the PaaS area, are as follows:

**PaaS**:

 1. [Heroku](https://www.heroku.com/) 
 2. [Dotcloud](https://www.dotcloud.com/)
 3. [Picloud](http://www.picloud.co)
 4. [EP](https://www.ep.io/)


However, instead of using a **PaaS** service, you can also use a **IaaS** service, install any operative system you desire in the machine you have rented, and then host your project there. This approach will give you a lot more work to do but it also gives you more configuration choices. In this domain, the main players are:

**IaaS**:

 1. [Amazon AWS](http://aws.amazon.com/)
 2. [Microsoft Azure](http://www.windowsazure.com/en-us/)
 3. [Rackspace Cloud](http://www.rackspace.com/cloud/)

Thus, when hosting your project, you shoudl evaluate if you need **IaaS** or **PaaS**, and then choose the best solution for you. And always remember to not compare oranges and apples - they are two different things !

## 8. Conclusion

In this tutorial you learned the basics of using GAE, and how it can and should help host your website or web app for free. 

Through it, you learned that GAE is a PaaS tool that allows you to freely host your website on Google's servers. You also learned how to create, test, register and upload projects to the GAE cloud (revision of chapters 5 and 6) and you have also learned that to code more efficiently you can and should use templates like Jinja2 or even frameworks. 

Last but not least you took a peak at the competition that GAE faces and how GAE differs itself from other great products, like AWS. 

However, you should keep mind that this was only but a small introduction to GAE. GAE is as huge as a world to explore. Here you were given the basic concepts and ideas to host a project on the Internet, but many important topics like GC-SQL, automatic billing and scalling were mentioned very lightly or were not mentioned at all. As usual, the rest of the homework is up to you.

## Extra Sources

- [Try GAE](https://developers.google.com/appengine/)
- [GAE Python tutorial](https://developers.google.com/appengine/docs/python/gettingstartedpython27/introduction)
- [GAE - Wiki](http://en.wikipedia.org/wiki/Google_App_Engine)
- [Youtube Search GAE Tutorial](http://www.youtube.com/results?search_query=google+app+engine+tutorial)

## Credits

 - [Pedro Martins](http://www.codecademy.com/fl4m3ph03n1x): me, the author, for doing all this stuff ! Phew, I am glad it is over :P
 - [Wafflegnome](http://www.codecademy.com/wafflegnome) and [Ksenia Dylova](http://www.codecademy.com/ksenja) for the moral support !
