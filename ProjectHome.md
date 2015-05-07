# Image preloader based on jQuery #

---

## Params ##
  * onDone : function()
  * onEachLoad : function(img)
  * onLoadError : function(img)-- called when an image was not succefully loaded
  * fadeIn : int(default 500) - time of fadein
  * delay : int(default 100) - time between showing next image
  * interval : int(default 200) - time between next check if any of images is loaded
  * parentWrap : string(default 'a') - just needed :P
  * loader : string(default 'img/loader.gif') - path to loader image

## Basic usage ##
We just need to specify element in wich we want to preload images.

`$('#gallery').preloader();`

You also need an image loader like this: ![http://i.imgur.com/FV68z.gif](http://i.imgur.com/FV68z.gif)
If you don't like this one, you also can look on this site http://preloaders.net
When you got your lovely loader you have to set path to it like this:

`$('#gallery').preloader({loader: 'path/to/loader/loader.gif'});`


## Function usage ##
Just 3 short codes to show how each function works. Check console for output.
### onDone ###
```
$('#gallery').preloader({onDone: function() {
  console.log('All images loaded succesfull');
}});
```

### onEachLoad ###
```
$('#gallery').preloader({onEachLoad: function(e) {
  console.log(e.attr('src')+' was loaded succesfully!');
}});
```

### onLoadError ###
```
$('#gallery').preloader({onLoadError: function(e) {
  e.replaceWith($('<p>This image was not loaded succesfully!</p>'));
}});
```