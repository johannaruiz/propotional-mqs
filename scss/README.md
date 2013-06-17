Try creating your media queries like objects or modules with @content and @include
e.g.
 @mixin modular-mq($breakpoint) {  
   @if $breakpoint == medium {  
     @media (#{$media} and $feature: $value) { @content; }  
   }  
   @else if $breakpoint == small {  
     @media (#{$media} and $feature: $value2) { @content; }  
   }  
 }
 @include breakpoint(small){
   css rules go here
 }
 @include breakpoint(medium){
  css rules go here
 }


 Example
 @mixin pmq($bp){
   @if $bp == small{
     @media #{$_s} and ($w: $tw_frty){ @content; }
   }
   @else if $bp == medium{
     @media #{$_s} and ($w: $th_twty){ @content; }
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
