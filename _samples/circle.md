---
layout: sample
author: Marco M. von Hagen
codename: m2vh
permalink: samples/circle.html
---

# The circle

The RAW [file](https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/_samples/svg/circle.svg).  
The file on [github](https://github.com/M2vH/websitetest/blob/gh-pages/_samples/svg/circle.svg).

We include a circle by referencing to an external SVG-file.

```html
<!--  -->
<div id="my_circle_svg" min-width="200px" max-width="500px">
<object data="./svg/circle.svg" type="image/svg+xml" id="my_circle">

<!-- we need the <img> tag to display on github -->
<img src="https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/_samples/svg/circle.svg?sanitize=true">

</object>
</div>

```
<div id="my_button">
<button name="circle_button" onclick="myCircleFunction()">Klick Me</button>
</div>



<div id="my_circle" min-width="200px" max-width="500px">
<object data="./svg/circle.svg" type="image/svg+xml" id="my_circle_svg">

<!-- we need the <img> tag to display on github -->
<img src="https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/_samples/svg/circle.svg?sanitize=true">

</object>
</div>


<div id="my_circle_script">
<script src="https://gist.github.com/M2vH/49ed98ba53d3c05a3b51ddbb24e6a6b5.js"></script>
</div>

