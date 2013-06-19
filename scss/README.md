##Sass Reference for constructing Media Queries  

**Note:** *Coming in the next few days, automated creation of media queries with looping through lists(arrays) of variables to construct media queries dynmaically. Also creation of other SCSS files to modularize code.* **Stay Tuned for Updates.**  

###Simple Media Query Constructiong
<pre>
  <code>
    @media #{$media} and ($feature: $value){}   
  </code>
  Note: Do not forget the interpolation braces --> #{}
</pre>

*Try creating your media queries like objects or modules with the directives @mixin, @content and @include* 

Below is an example of using the @mixin, @content @include directives to make complex object oriented media queries with ease  

###SCSS
<pre>
  <code>
    @mixin pmq($vp){
      @if $vp == small{ 
        @media #{$_s} and ($w: $tw_frty){ 
          @content; 
        }
      }
      @else if $vp == medium{ 
        @media #{$_s} and ($w: $th_twty){ 
          @content; 
        }
      }
    }
    
    @include pmq(small){
      body{
        width:100%;
      }
    }
    @include pmq(medium){
      body{
        width:95%
      }
    }
    
    *The same method above but referencing an item of a list*
    
    @mixin pmq($vp){
      @if $vp == #{nth($viewports, 12)}{ 
        @media #{$_s} and ($w: $tw_frty){ 
          @content; 
        }
      }
      @else if $vp == #{nth($viewports, 11)}{ 
        @media #{$_s} and ($w: $th_twty){ 
          @content; 
        }
      }
    }

    @include pmq(small){
      body{
        width:100%;
      }
    }
    @include pmq(medium){
      body{
        width:95%
      }
    }
  </code>
</pre>

###CSS Output
<pre>
  <code>
    @media screen and (width: 15em){
      body{
        width: 100%;
      }
    }
    @media screen and (width: 20em){
      body {
        width: 95%;
      }
    }
  </code>
</pre>

###SCSS###

*This example of dynamically creating a list of media queries from lists, one list for the media type and a second list for the viewport.*
*My goal is to create the ability to dynamically create media queries by combining this method with the top method by using @mixin and @content.*
<pre>
  <code>
    @each $vp in $viewports{
      @media #{nth($media-types, 8)} and ($vp){
        /**/
      }
    }
  </code>
</pre>

###CSS Output###
<pre>
  <code>
    @media screen and (120em) {
      /**/
    }
    @media screen and (105em) {
      /**/
    }
    @media screen and (90em) {
      /**/
    }
    @media screen and (75em) {
      /**/
    }
    @media screen and (64em) {
      /**/
    }
    @media screen and (60em) {
      /**/
    }
    @media screen and (50em) {
      /**/
    }
    @media screen and (48em) {
      /**/
    }
    @media screen and (37.5em) {
      /**/
    }
    @media screen and (30em) {
      /**/
    }
    @media screen and (20em) {
      /**/
    }
    @media screen and (15em) {
      /**/
    }
  </code>
</pre>



