# Welcome to my project website test.
 This automatic page generator is the easiest way to create beautiful pages for all of your projects. Author your page content here [using GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/), select a template crafted by a designer, and publish.

Go [to the website](https://m2vh.github.io/websitetest/#mysvgcircle) to see the site in action.

 
## some svg experiment

html inside markdown file. we use the following html inside the markdown file.

```html
<svg id="mysvgcircle" 
     width="100" 
     height="100" 
     viewBox="0 0 500 500" 
     preserveAspectRatio="none">
 
  <circle id="mycircle" 
          cx="50" 
          cy="50" 
          r="40" 
          stroke="green" 
          stroke-width="4" 
          fill="yellow" />
</svg>

<div height="200" width="100%">
<svg id="mysvgpath" 
     viewBox="0 0 500 500" 
     preserveAspectRatio="none"
     position="relative">
 <path d="M 200 125 m -100 0 a 100 100 0 1 0 200 0 a 100 100 0 1 0 -200 0" 
       fill="yellow" 
       id="mypath">
</path>
 </svg>
</div>
```

we should see a circle, and a path forming a circle.

First a circle, where viewBox is size of parent div

<div id="myExperiment">
<div width="100" height="100">
<svg id="mysvgcircle"  
     viewBox="0 0 100 100" 
     preserveAspectRatio="none"
     position="relative">
  <circle id="mycircle" 
          cx="50" 
          cy="50" 
          r="40" 
          stroke="green" 
          stroke-width="4" 
          fill="yellow" />
</svg>
</div>

then draw a path with viewBox double size of parent div.

<div height="200" width="200">
<svg id="mysvgpath" 
     viewBox="0 0 400 400" 
     preserveAspectRatio="none"
     position="relative">
 <path d="M 200 200 m -100 0 a 100 100 0 1 0 200 0 a 100 100 0 1 0 -200 0" 
       fill="yellow" 
       stroke="green" 
       stroke-width="4" 
       id="mypath">
</path>
 </svg>
</div>
</div>

## create a SVG circle

```html
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

## use some javascript

```javascript
$('#wrapper').animate({width:550},5000,function(){
    $(this).animate({height:100},5000);
});
```
