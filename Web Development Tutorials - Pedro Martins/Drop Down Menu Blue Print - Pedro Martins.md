## Prior Requirements

- [Web Fundamentals](http://www.codecademy.com/tracks/web) 
- [Javascript](http://www.codecademy.com/tracks/javascript)
- [JQuery](http://www.codecademy.com/tracks/jquery)

----------

Sometimes users post their websites and their work for others to see. Sometimes that work is worthy of being remembered and thus it becomes a [RESOURCE]. Then, sometimes some resources are too good to not become something else, something better - to not become a [TUTORIAL].
Such is the case with this resource made by [LulzSec][LulzSec-user]. After studying his submission I decided that with the propper magic it could become something more useful to the community, and so I turned it into a tutorial that I hope you all enjoy. 

----------

## Introduction
In this tutorial you will learn how to create and develop a basic drop down menu that you can place at the top of your web page with the help of some external JavaScript libraries. This drop down menu can be further improved with a specific font and with more information, but we leave that you, here we are going to focus on explaining the basics. 
The full code of a more complex example can be download in the end inside the **Going Further** section, where you can evaluate all the tips and tricks that the user [O Pirata][pirata-user] used to make his CodeCademy project.

By the end of this tutorial, you should be able to answer the following questions:

- How do I create a drop down menu bar?
- How can I customize its items?
- How can I customize its color?
- Are there easier ways to create custom drop down menu bars?

## Drop Down Menu Blue Print
First, let us take a look at what we are going to do here. The website you are about to create will look like the following image (click it to visit the website!):
[![website-pirata-movie][website-pirata-movie]][website-pirata]

### Folder Structure
To fully understand the following sections it is important to know the folder structure used in the project. The project is therefore defined with the following structure:

    Website_O_Pirata/
        ├── css/
        │   ├── default.css
        │   └── style.css
        ├── js/
        │   ├── cbpHorizontalMenu.min.js
        │   └── modernizr.custom.js
        └── index.html

This also represents all the files that you will need to successfully create the website on your local machine. The next sections will explain the index.html file and the files inside the css folder in detail. The files in the js folder are libraries and are therefore out of the scope of this tutorial. If you wish to learn more about them you can always read the suggested links and tutorials or make a search on your own.

### HTML 
The first step of making any website is creating the HTML structure and this one is no exception. The full HTML file can be seen in the following link:

- [html-file][html-file]

First let us start by the `<head></head>` tags. Here you can see that there are two CSS files that are required, the style.css and the default.css files. We will cover these two files later in the next subsection. Now you may be thinking that we are done with our pre-requisites. However such is not true. If you scroll down to the last lines of the body element you will see the following code:

    <!-- We load our JavaScript files in the end -->
    <script src="js/modernizr.custom.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    <script src="js/cbpHorizontalMenu.min.js"></script>
    <script>
        $(function() {
            cbpHorizontalMenu.init();
        });
    </script>

In this piece of code we have all our JavaScript pre-requisites. by looking closely at the code, we can see that our HTML file will require three libraries:

1. Modernzr
2. Jquery
3. cbpHorizontalMenu

The first library is a normal one, you download the code and link it to your HTML file like you would link any other library. You can download the version of Modernizr that we use by going here:

- [modernizr-custom-download][modernizr-custom-download]

And visit the official website here:

- [modernizr-custom-website][modernizr-custom-website]

The second library is the widely known jQuery library. This library is so well known that even CodeCademy has a course on it. You can check CodeCademy's course on jQuery here:

- [jQuery-CC-course][jQuery-CC-course]

You can visit jQuery's official website here:

- [jQuery-website][jQuery-website]

Instead of downloading and linking our HTML file to that library like we did with the first one, we simply link our HTML to a jQuery version that is hosted by Google. This why we do not have to waste space holding that library, let Google servers do it :P

The final one is the trickier. cbpHorizontalMenu was downloaded and linked like Modernizr, however that is still not enough. Sometimes for libraries to properly work they need to be initialized first, and that is what we do with our little piece of embedded JavaScript. Note that you should never embed JavaScript code into an HTML file, it makes it harder to read and does not separate concerns. However, for the sake of simplicity, I decided to make an exception in this specific case - after all we are are talking about 3 lines of code :P

You can download our version of the cbpHorizontalMenu library here:

- [cbpHorizontalMenu-download][cbpHorizontalMenu-download]

And you can check the official website here:

- [cbpHorizontalMenu-website][cbpHorizontalMenu-website]

However, by now I am sure you have a question not yet answered: Why place the JavaScript imports at the end of the HTML file and not at the top of the file between the `<head></head>` tags?
There are two main reasons for doing that:

1. When you load your JavaScript files at the end, the client visiting your website does not have to wait for them to be loaded before he can start seeing the website.
2. One of the required libraries (cbpHorizontalMenu) must be initialized with a JavaScript function that needs to know all the HTML content before it can properly load the library.

The first reason simply allows your clients to see the website faster. It keeps the user from waiting an eternity without seeing any sort of progress, but keep in mind that he/she will not be able to play around with it until the libraries are loaded.
The second reason is trickier. As I explained before some libraries need to be properly initialized. cbpHorizontalMenu initialization procedure says that we must call the `init()` function at the end of an HTML file so it can initialize and properly load the cbpHorizontalMenu library. You can play around with this - try moving this piece of code into the `<head></head>` section and then see for yourself if it still works :P

Now that the pre-requisites are done, it is time to delve into the HTML body structure.

    <nav id="cbp-hrmenu" class="cbp-hrmenu">
        <ul>
            <li class ="">
                <a href="#">Products</a>
                <div class="cbp-hrsub">
                    <div class="cbp-hrsub-inner">
                        <div>
                            <h4>Learning & Games</h4>
                            <ul>
                                <li>
                                    <a href="#">Catch the Bullet</a>
                                </li>
                                <li>
                                    <a href="#">Snoopydoo</a>
                                </li>
                                <li>
                                    <a href="#">Fallen Angel</a>
                                </li>
                                <li>
                                    <a href="#">Sui Maker</a>
                                </li>
                                <li>
                                    <a href="#">Wave Master</a>
                                </li>
                                <li>
                                    <a href="#">Golf Pro</a>
                                </li>
                            </ul>
                            </div>
                            <div>
                                <h4>Utilities</h4>
                                <ul>
                                    <li>
                                        <a href="#">Gadget Finder</a>
                                    </li>
                                    <li>
                                        <a href="#">Green Tree Express</a>
                                    </li>
                                    <li>
                                        <a href="#">Green Tree Pro</a>
                                    </li>
                                    <li>
                                        <a href="#">Wobbler 3.0</a>
                                    </li>
                                    <li>
                                        <a href="#">Coolkid</a>
                                    </li>
                                </ul>
                            </div>
                            <div>
                                <h4>Education</h4>
                                <ul>
                                    <li>
                                        <a href="#">Learn Thai</a>
                                    </li>
                                    <li>
                                        <a href="#">Math Genius</a>
                                    </li>
                                    <li>
                                        <a href="#">Chemokid</a>
                                    </li>
                                </ul>
                                <h4>Professionals</h4>
                                <ul>
                                    <li>
                                        <a href="#">Success 1.0</a>
                                    </li>
                                    <li>
                                        <a href="#">Moneymaker</a>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </li>
            <!-- More <li></li> items -->
        </ul>
    </nav>


The evolving tag is the `<nav id="cbp-hrmenu" class="cbp-hrmenu"></nav>` tag. This tag has both the id and class of `cbp-hrmenu`, which is needed by the style.css file and the cbpHorizontalMenu library. Then we have the `<ul></ul>` tag which defines the list with all the items inside it.

Following the `<ul></ul>` we have the child `<li class=""></li>` tag. At first one may consider the `class=""` portion of the code. However, you should **not** do that. The libraries used will dynamically modify the `<li class=""></li>` into a `<li class="cbp-hropen"></li>` tag, thus allowing you to see that the item is clicked and therefore open. 

Then we have the `<a href="#">Products</a>` which is merely the click-able title followed by the divs. These divs have the classes `cbp-hrsub` and `cbp-hrsub-inner` which will define how the items inside them will be displayed according to the style.css file.

The process then repeats itself by adding and nesting more unordered lists and items withing each other, as you can see in the full version of the HTML code. By now it should be clear that how you can customize the items of the bar - by adding and nesting lists and items.

One important thing to notice however: if you place too many items in one row, they will be automatically moved to the one directly below it. This can be seen in the original source code present in the **Going Further** section.

### CSS
There are two css files required:

- [default.css][default.css-download]
- [style.css][style.css-download]

The first one applies a hack known as the clearfix hack. For more information about this hack you can visit the following links:

- [clearfix-stackoverflow][clearfix-stackoverflow]
- [clearfix-learnlayout][clearfix-learnlayout]

The second one defines the style of the menu: the sizes, colors, borders, footers and so on. This file is divided into six main sections:

- **mix**, general styling for the `cbp-hrmenu` classes 
- **general ul style**, for the unordered lists children of cbp-hrmenu elements
- **first level ul style**, defines styling for the unordered lists, list items and anchors according to the nesting. 
- **sub-menu**, Overall styling and color for all classes and sub-menus. It also adds a responsive design feature by taking into consideration the screen size. 
- **footer**, styling for the footer. Important to notice that in this example I use the `footer` tag from HTML instead of a `div` tag with class footer like it is done in the original example.
- **about my style**, specific personalizations.

So, it should be clear now that if you want to customize the color, size and other attributes of your drop down menu, you should change the style.css file and **not** the default.css file.

## Going Further
Going further would include two main things:

- studying the source code and understanding how you can change it and improve it
- studying and understanding the libraries used at a deeper level

 The first point is quite clear. By studying the source code you can learn more and play with it. There are two different source code versions. My version (by Pedro Martins) is a lot cleaner, simpler and it was designed for this tutorial. The original version (by O Pirata) includes an imported font, two-row lists and un-minized versions of some of the libraries used. Consequently, I provide both versions of the code:
 
- [Tutorial version by Pedro Martins][source-pedro]
- [Original version by O Piarata][source-pirata]

I suggest that you start by studying my version of the code, and then evolve into studying the original version, which is more complex.

The second point requires you to read the APIs, documentation and check examples of the libraries. This will allow you in due time to further improve your skills using these resources and will make of you a more independent coder.
For additional resources you can check these links:

- [modernizr tutorials][modernizr-tut]
- [jquery tutorials][jquery-tut]
- [jquery lessons][jquery-lessons]

## Problems and alternatives
The problem with using this solution is that you will eventually need some other functionality in your website, like a slider, or video-player or even a different drop down menu style. Thus you will eventually end up with a web site filled with plugins that will conflict with each other and become hard to maintain over time. Furthermore this solution requires the coder to delve deeply into the css code styles to understand it and because it is mainly designed as a custom solution it has little to no support in the Internet. 

To fix this, there are other solutions - namely using frameworks. The quality of this alternative is highly dependent on the framework you decide to use, but one we recommend is the Bootstrap. Bootstrap allows you to make not just drop down menus but many other things. You can read all about the Bootstrap framework in our tutorial:

- [Twitter Bootstrap - Websites for all Screens, Devices, Browsers and more!][bootstrap-tutorial] 

## Conclusion
If I did my job decently by now you should be able to know how to create a drop down menu by using this method. First you create your HTML file with the CSS and JavaScript imports that you need **in the right place**. Then you simply add and nest the lists with the correct classes as you go. If you still have problems with the lists and nesting you can easily check the source code examples for more information.

You can customize the structure of your menu by changing the HTML and the colors and styles by changing the style.css file. 

Finally, there are other ways and alternatives to create drop down menus, and we provide one of them with the Bootstrap tutorial. 

## Special Thanks

- [O Pirata][pirata-user], thank you for your strong initiative and source code. They made this tutorial possible. Your new position as a co-leader is definitely deserved and I look forward working with you.

[pirata-user]: http://www.codecademy.com/thelulzboat
[website-pirata-movie]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/website.gif
[website-pirata]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/Website_O_Pirata/index.html
[html-file]: http://tny.cz/3e3a1223
[modernizr-custom-download]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/Website_O_Pirata/js/modernizr.custom.js
[modernizr-custom-website]: http://modernizr.com/
[jQuery-CC-course]: http://www.codecademy.com/tracks/jquery
[jQuery-website]: http://jquery.com/
[cbpHorizontalMenu-download]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/Website_O_Pirata/js/modernizr.custom.js
[cbpHorizontalMenu-website]: http://tympanus.net/codrops/2013/03/05/horizontal-drop-down-menu/
[clearfix-stackoverflow]: http://stackoverflow.com/questions/8554043/what-is-clearfix
[clearfix-learnlayout]: http://learnlayout.com/clearfix.html
[bootstrap-tutorial]: http://www.codecademy.com/groups/html-projects/discussions/51aa686665ce54dbae0017a8
[modernizr-tut]: http://www.tutorialspoint.com/html5/html5_modernizr.htm
[jquery-tut]: http://www.w3schools.com/jquery/default.asp
[source-pedro]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/pedrodropdown.zip
[source-pirata]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/lulzsecdropdown.zip
[default.css-download]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/Website_O_Pirata/css/default.css 
[style.css-download]: https://dl.dropboxusercontent.com/u/785815/DropDownMenu/Website_O_Pirata/css/style.css
[jquery-lessons]: http://learn.jquery.com/about-jquery/