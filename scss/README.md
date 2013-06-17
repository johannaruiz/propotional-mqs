#Sass Reference for constructing Media Queries
*Try creating your media queries like objects or modules with @content and @include*

##Sass
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

##CSS Output
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


