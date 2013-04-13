#Proportional CSS3 Media Queries

Proportional Media Queries are based upon the idea that Responsive Web Design is supposed to be fluid using relative measurements. With that thought process in mind, using pixels for media queries seems to be cumbersome at times. I got the idea that since it's standard practice to use relative units (ems, rems, %) for font sizing in responsive web design, why not use relative measurement units for targeting the viewport width. And that's exactly what I did. 

Using the standard formula for font-sizing: 100% = 16px = 1em = 14pt.
So I applied that principle to the viewport width.
  * 240px = 15em
  * 320px = 20em
  * 480px = 30em
  * 600px = 37.5em
  * 768px = 48em
  * 800px = 50em
  * 960px = 60em
  * 1024px = 64em
  * 1200px = 75em
  * 1400px = 87.5em
  * Continue targeting screen sizes based on device width e.g. larger displays, tv's etc. 

Also since there are the beautiful high resolution displays, it's becoming standard practice to serve up device and screen and device specific CSS based upon resolution and pixel density using media queries for the high resolution displays such as Apple's Retina Display. 

e.g. @media(min-resolution : 192dpi), (-webkit-min-device-pixel-ratio: 2){
      /* Code Goes Here */
      }
Some standard device pixel ratio's to target:
  * 3
  * 2
  * 1.5
  * 1.3
  * 1.25

Resolutions to target
  * 300 dpi
  * 244 dpi
  * 192 dpi
  * 144 dpi
  * 124.8 dpi
  * 120 dpi

Use a combination of these to target viewport width and pixel densities to usher in a new era of responsive and adaptive web development
