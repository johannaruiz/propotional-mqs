##Sass Reference for constructing Media Queries  

**Note:** *Coming in the next few days, automated creation of media queries with looping through lists(arrays) of variables to construct media queries.*  

###Simple Media Query Construction
<pre>
  <code>
    @media #{$media} and ($feature: $value){}   
  </code>
  Note: Do not forget the interpolation braces --> #{}
</pre>

*Try creating your media queries like objects or modules with the directives @mixin, @content and @include* 

Below is an example of using the @mixin, @content @include directives to make complex object oriented media queries with ease  

###Sass
<pre>
  <code>
    @mixin pmq($bp){
      @if $bp == small{ 
        @media #{$_s} and ($w: $tw_frty){ 
          @content; 
        }
      }
      @else if $bp == medium{ 
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


