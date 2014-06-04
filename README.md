BeforeAfterImageSlider
======================

This is a simple open source tool for creating before/after image sliders. Just provide two image URLs and this will do the rest of the work for you. 

###Instructions

####HTML Implementation
The easist way to implement the image slider is to add this code to your markup:

    <div id="klba-wrapper">
        <img src="http://firstimage.jpg" />
        <img src="http://secondimage.jpg" />
    </div>
    <script src="path/to/slider.js"></script>

Each image can also take some additional attributes.

    <img src="http://image.jpg" data-label="2009" data-credit="Alex Duner/Northwestern Knight Lab" />

If each image has an `data-label` attribute defined, the slider will display a label on each image. If each image has a `data-credit` attribute defined, the slider will display a credit for each image.

The main wrapper can also take some additional attributes as well to specify a few options:

    <div id="klba-wrapper" data-startingposition="35%" data-showlabels="false" data-showcredits="false" data-animate="false">

Specifying a starting position with `data-startingposition` lets you focus the users attention on the part of the image where the change is most noticiable. To toggle the visibility of the labels and the credits respectivly, set `data-showlabels` and `data-showcredits` to false. And to disable the animation, set `data-animate` to false.


####Javascript Implementation
The `ImageSlider` class takes three arguments. First, is the string of the ID of the element you want to turn into a slider. Second is an array of two objects. Each object *must* have `src` defined and can optionally define a `label` and a `credit`. The third argument lets you set additional options for the image slider.

    <div id="klba-slider"></div>
    <script>
    slider = new ImageSlider('klba-slider', 
        [
            {
                src: 'http://firstimage.jpg',
                label: '2009',
                credit: 'Image Credit'
            },
            {
                src: 'http://secondimage.jpg',
                label: '2014',
                credit: "Image Credit"
            }
        ], 
        {
            animate: true,
            showLabels: true,
            showCredits: true,
            startingPosition: "50%"
        });
    </script>

