Basic concepts and initial information
-

**Styles and scripts**

The plugin will render the slider using a minimal of JS and CSS code, so you need to have the scripts and styles options enabled in your template

Remember to add following code in layout:

In your head section
```
{% styles %}
```

At the end of your body section

```
{% scripts %}
```

**Slides Order**

The slides order is defined in the *Slides* tab of the Slider, you can drag and drop it for the desired order. Each slider have it's own order configuration. However, if you need it you can set the Slides Order to *Random* option in the component configuration

```
[moonSlider]
slug = "slider-demo"
slidesOrder = "random"
```


Basic operation
-
Add the component MoonSlider to your page or partial; Define the Slider slug and the order of de slides.

```
[moonSlider]
slug = "slider-demo"
slidesOrder = "slider"
```

In your page or partial html code add the component

```
{% moonSlider %}
```

This will display the slider in your page or partial **and that's it**

**Consideration:**

The component will render the slider using the width of their container, so, it's a good idea to have a defined container, for example

```
<!-- container for slider -->
<div id="slider-container" style="width: 900px">
    {% component "moonSlider" %}
</div>
```

In this example, the slider will have 900px for width.

The eight of the slider is defined in the slider properties in the sizes tab


Advanced operation
-
If you don't want to use the default reder of the slider, you can use all the elements of the slider and slides in order to build your slider with the front end library of your preference (SlickSlider, Glide JS, Swiffy Slider, etc)

Once you have attached the moonSlider component to your page, there will available a set of variables in the page for use it as you need

```
moonSlider.name
moonSlider.slug
```
Name and Slug of the slider


```
moonSlider.nav.controls
```
The position for the controls (arrows) of the slider. Values:
- none
- inline
- outline

```
moonSlider.nav.dots
```
The position for the position markers (dots) of the slider. Values:
- none
- inline
- outline


Boolean values
```
moonSlider.is_active //Defines if the Slider is active or not
moonSlider.options.autoplay //defines if the slider will autoplay the transitions
moonSlider.options.lazyload //lazyload for the images
moonSlider.options.loop //defines if the slider will loop at the end
```

```
moonSlider.options.items
```
Integer. How many slides are available per block


```
moonSlider.options.mode
```
Defines the slider mode. Values:
- **Gallery**. In this mode, the slides transition is a fade out and fade in for all the elements in the slider. It's a good option for images galleries

- **Carousel**. In this mode, the elements of the slider moves from right lo left



```
moonSlider.options.time
```
Integer. The time between each change of the slides. Applys for carousel and gallery mode. Autoplay value must be in true


```
moonSlider.slides
```

This is an array of all the slides in the slider. For use it you need to apply a for

```
{% for slide in moonSlider.slides %}
..
..
{% endfor %}
```

Each slide have the next variables

Boolean variables

```
slide.is_active
slide.button_enabled
```

string variables
```
slide.name
slide.slug
slide.url
```

control variables

```
slide.start_date
slide.end_date
```

Media Paths
```
slide.image_button.path
slide.image_desktop.path
slide.image_tablet.path
slide.image_mobile.path
slide.image_over.path
slide.video.path
```

Position of the floatting button (if available)

```
slide.button_position.horizontal
slide.button_position.vertical
```

Questions or bug reports
-
We are happy to help!

Send us an email to [hello@polilla.studio](mailto:hello@polilla.studio) and we'll reply you as soon as we can.

Or you can visit [GitHub Issues Page](https://github.com/Polilla-Studio/moonslider-plugin-pub/issues) to report any issues with plugin.
