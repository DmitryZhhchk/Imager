# Imager
This poject is example of using Vue, axios and SixLaboSr.ImageSharper in an MVC application.


In fact, it receives a picture and pixelates  it into a new one.
As an option it is possible to use squares or circles as a pattern to create a new image.


It is a Model-View-Controller project.
As a model, there is a  ImgProcessor class which works with an image using  SixLaboSr.ImageSharper.
This class is used as a singletone, so we create it only once when application starts. Then it  processes 
and reloads different images.

Controller(HomeController) receives data(a loaded picture and some parameters) from a view, calls ImgProcessor 
to process an image and returns a new image to view as Base64String.

In a View(Index.cshtml) we provide simple interface to load image and choose some options.
There are a little of bootstrap(to align and scale elements), vue.js to work with selectboxes and buttons.
Using axios allows ajax request so we can send command to controller to change an image  without
reloading all the page. It should be mentioned that if a big image is loaded it looks like nothing happens 
for some time because browser doesn't reload the page and there are no signs of work in progress.
