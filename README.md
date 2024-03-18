<!--
author: Sebastian Zug

version: 0.0.1

link:    style.css

language: en

narrator: US English Male

logo:     img/logo.gif

comment:  This template allows you to compare two images side by side and slide between them to see the differences.

@beforeAndAfter: @beforeAndAfter_(@uid,@0,@1)

@beforeAndAfter_
<section class="container" id="beforeAndAfter_@0">
<div class="image-container">
<img src="@1" alt="before"/>
<img src="@2" alt="after"/>
</div>
<script style="display: block">
    setTimeout(() => {
        const container = document.getElementById('beforeAndAfter_@0');
        document.getElementById('slider_@0').addEventListener('input', (e) => {
            container.style.setProperty('--position', `${e.target.value}%`);
        })
    }, 1000);

`HTML:
<input id="slider_@0" type="range" min="0" step="1" max="100" value="50" aria-label="Percentage of before photo shown" class="slider" />
<div class="slider-line" aria-hidden="true"></div>
<div class="slider-button" aria-hidden="true">
    <svg width="30" height="30" fill="currentColor" viewBox="0 0 256 186">
        <line x1="128" y1="40" x2="128" y2="216" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line>
        <line x1="96" y1="128" x2="16" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line>
        <polyline points="48 160 16 128 48 96" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline>
        <line x1="160" y1="128" x2="240" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line>
        <polyline points="208 96 240 128 208 160" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline>
    </svg>
</div>`
</script>
    
</section>
@end

-->

# Before and After

    --{{0}}--
This extension allows you to compare two images side by side and slide between them to see the differences.

__Try it on LiaScript:__

https://LiaScript.github.io/course/?https://raw.githubusercontent.com/LiaTemplates/BeforeAndAfter/main/README.md

__The Project on GitHub:__

https://github.com/LiaTemplates/BeforeAndAfter


    --{{1}}--
There are three ways to use this template.
The easiest way is to use the import statement and the url of the raw text-file of the master branch or any other branch or version.
But you can also copy the required functionality directly into the header of your Markdown document, see therefor the last slide.
And of course, you could also clone this project and change it, as you wish.

    {{1}}
1. Load the macros via

   __current version:__
   `import: https://raw.githubusercontent.com/LiaTemplates/BeforeAndAfter/0.0.1/README.md`

   __latest version:__
   `import: https://raw.githubusercontent.com/LiaTemplates/BeforeAndAfter/main/README.md`


2. Copy the definitions into your Project

3. Clone this repository on GitHub


## `@beforeAndAfter`


    --{{0}}--
You can use the `@beforeAndAfter` macro to compare two images side by side and slide between them to see the differences.
Simply provide the two image URLs as parameters to the macro, without additional spaces in between.
You can see the result below.

```markdown
@beforeAndAfter(img/glacier-1883.jpg,img/glacier-2015.jpg)
```

---

@beforeAndAfter(img/glacier-1883.jpg,img/glacier-2015.jpg)

---

> __Lyell Glacier 2015__
> 
> Are there glaciers in Yosemite National Park? Yes, but not for long. You can see there's not much left of the Lyell Glacier; in fact, it's now more accurately called the Lyell Ice Patch since it is not technically a glacier anymore (there's no more downhill movement). Only the Maclure Glacier remains in the park.
> 
> Although the Earth's climate does fluctuate naturally over tens of thousands of years, today's rapid warming means we're saying goodbye to many of these features in our lifetimes.
>
> 1883 photo: USGS/Israel Russell
> 
> 2015 photo: NPS/Keenan Takahashi
>
> Source: https://www.flickr.com/photos/npsclimatechange/22954029562


### Styling


    --{{0}}--
If your images are too large, you can use the `style` attribute to set a maximum width for the images.

``` markdown
<!-- style="max-width: 80vh;" -->
@beforeAndAfter(img/hubble.jpg,img/webb.jpg)
```

---

<!-- style="max-width: 70vh;" -->
@beforeAndAfter(img/hubble.jpg,img/webb.jpg)

---

> __Hubble and Webb showcase the Pillars of Creation (side by side)__
>
> The NASA/ESA Hubble Space Telescope made the Pillars of Creation famous with its first image in 1995, but revisited the scene in 2014 to reveal a sharper, wider view in visible light, shown above at left...
>
> Source: https://www.esa.int/ESA_Multimedia/Images/2022/10/Hubble_and_Webb_showcase_the_Pillars_of_Creation_side_by_side


## Implementation


    --{{0}}--
If you want to use the code directly, you can copy the following definitions into the main comment of your project.
Thereby `@beforeAndAfter` uses the "helper" macro `@beforeAndAfter_` to which the urls are passes as well as a unique id to distinguish between different components.


```html
link:    style.css

@beforeAndAfter: @beforeAndAfter_(@uid,@0,@1)

@beforeAndAfter_
<section class="container" id="beforeAndAfter_@0">
<div class="image-container">
<img src="@1" alt="before"/>
<img src="@2" alt="after"/>
</div>
<script style="display: block">
    setTimeout(() => {
        const container = document.getElementById('beforeAndAfter_@0');
        document.getElementById('slider_@0').addEventListener('input', (e) => {
            container.style.setProperty('--position', `${e.target.value}%`);
        })
    }, 1000);

`HTML:
<input id="slider_@0" type="range" min="0" step="1" max="100" value="50" aria-label="Percentage of before photo shown" class="slider" />
<div class="slider-line" aria-hidden="true"></div>
<div class="slider-button" aria-hidden="true">
    <svg width="30" height="30" fill="currentColor" viewBox="0 0 256 186">
        <line x1="128" y1="40" x2="128" y2="216" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line>
        <line x1="96" y1="128" x2="16" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line>
        <polyline points="48 160 16 128 48 96" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline>
        <line x1="160" y1="128" x2="240" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line>
        <polyline points="208 96 240 128 208 160" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline>
    </svg>
</div>`
</script>
    
</section>
@end
```