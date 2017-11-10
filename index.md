# Welcome to my project website test.
 This automatic page generator is the easiest way to create beautiful pages for all of your projects. Author your page content here [using GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/), select a template crafted by a designer, and publish.

Please [klick](https://m2vh.github.io/websitetest/#myExperiment) to jump to the svg section of this site.

Please [klick](./mytest) this hard link to jump to project layout.

 
## some svg experiment

html inside markdown file. we use the following html inside the markdown file.

```html

<div id="myExperiment">
 <div width="100" height="100">
  <svg id="mySvgCircle"  
     viewBox="0 0 100 100" 
     preserveAspectRatio="none"
     position="relative">
  <circle id="myCircle" 
          cx="50" 
          cy="50" 
          r="40" 
          stroke="green" 
          stroke-width="4" 
          fill="yellow" />
  </svg>
 </div>

<div id="myWrapperBox">

 <div id="myPathWrapper">

  <svg id="mySvgPath" 
      viewBox="0 0 400 400" 
      preserveAspectRatio="none"
      position="relative">
     
   <path d="M 200 200 m -100 0 a 100 100 0 1 0 200 0 a 100 100 0 1 0 -200 0" 
       fill="yellow" 
       stroke="green" 
       stroke-width="4" 
       id="myPath">
       
   </path>
  </svg>
 </div> <!-- myPathWrapper -->
</div> <!-- myWrapperbOX -->

</div> <!-- myExperiment -->

```

### The SVG in action

We should see a circle, and a path forming a circle.

First a circle, where viewBox is size of parent div

<div id="myExperiment">
 <div width="100" height="100">
  <svg id="mySvgCircle"  
     viewBox="0 0 100 100" 
     preserveAspectRatio="none"
     position="relative">
  <circle id="myCircle" 
          cx="50" 
          cy="50" 
          r="40" 
          stroke="green" 
          stroke-width="4" 
          fill="yellow" />
  </svg>
 </div>

then draw a path with viewBox double size of parent div.

<div id="myWrapperBox">

 <div id="myPathWrapper">

  <svg id="mySvgPath" 
      viewBox="0 0 400 400" 
      preserveAspectRatio="none"
      position="relative">
     
  <path d="M 200 200 m -100 0 a 100 100 0 1 0 200 0 a 100 100 0 1 0 -200 0" 
       fill="yellow" 
       stroke="green" 
       stroke-width="4" 
       id="myPath">
       
 </path>
 </svg>
</div> <!-- myPathWrapper -->
</div> <!-- myWrapperbOX -->
</div>

## create a SVG circle with a script

```xml

<svg xmlns="http://www.w3.org/2000/svg">
  <script>
    var svg   = document.documentElement;
    var svgNS = svg.namespaceURI;

    var circle = document.createElementNS(svgNS,'circle');
    circle.setAttribute('cx',100);
    circle.setAttribute('cy',200);
    circle.setAttribute('r',50);
    circle.setAttribute('fill','red');
    circle.setAttribute('stroke','black');
    circle.setAttribute('stroke-width','20px');
    circle.setAttribute('stroke-opacity','0.5');

    svg.appendChild(circle);
  </script>
</svg>

```

## use some javascript to animate :-(

we still get Error Codes when trying to use javascript.

```javascript
$('#wrapper').animate({width:550},5000,function(){
    $(this).animate({height:100},5000);
});
```

so we use CSS to animate

```css
#myPathWrapper {
  animation-duration: 3s;
  animation-name: pump;
  animation-iteration-count: 10;
  animation-direction: alternate;
}

@keyframes pump {
  from {
    width: 100px;
  }
  to {
    width:500px;
  }
}

#myWrapperBox {
  height: 500px;
}

```


## use a link to raw github file to display svg-file 

the raw file is found here: https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/assets/svg/mytest.svg

### the svg should be displayed on the github page

We use `?sanitize=true` at the end of the link to point to the raw file.
The svg will be displayed on gh-pages website as well.

![https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/assets/svg/mytest.svg](https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/assets/svg/mytest.svg?sanitize=true)

The markdown looks like this

```markdown

![link](https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/assets/svg/mytest.svg?sanitize=true)

```

### link to external svg file in markdown

We want to use the `<object>` tag to include external svg file

```markdown

<div id="myExternalSvg">
 <object id="myObject"
         data="https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/assets/svg/mytest.svg"
         type="image/svg+xml">
 </object>
</div>

```

The `<object>`-tag is not working properly, because the github-server is sending `X-Frame: deny` in its header.
Let's see, if `<img>` is  possible.

<div id="myExternalSvg">
 <img id="myObject" src="https://raw.githubusercontent.com/M2vH/websitetest/gh-pages/assets/svg/mytest.svg?sanitize=true">
</div>

