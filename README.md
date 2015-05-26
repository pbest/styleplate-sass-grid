# sass-grid
A super flexible, simple, and 'semantic' SASS-based grid system

# How to use: #
1.  Edit variables to match design  
2.  Add the grid-container mixin to parent element(s)  
3.  Start adding the span(n) mixin to your individual grid elements  
4.  Add the span(n) mixin to your media queries for a responsive grid flow  
5.  Be happy with your clean semantic HTML!!!

#sample usage:#
Variables:
<pre>
    $number_of_columns: 12;  
    $max_width: 1140px;   
    $spacing_unit: rem;  
    $horizontal_spacing: 20;  
    $vertical_spacing: 10;
</pre>  
  
SCSS:
<pre>
   .parent {
    @include grid_container;
   }
   
   .child1 {
     @include span(25);
     
     @media screen and (max-with:767px) { // mobile
       @include span(50);
     }
   }
</pre>
  
CSS Output:  
<pre>
*, *:before, *:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.parent {
  padding-left: 0rem;
  padding-right: 0rem;
  padding-top: 0rem;
  padding-bottom: 0rem;
  margin-left: auto;
  margin-right: auto;
  max-width: 1140px;
}

.parent::after {
  content: "";
  display: table;
  clear: both;
}

.parent > * {
  padding-left: 0rem;
  padding-right: 0rem;
  padding-top: 0rem;
  padding-bottom: 0rem;
}

.child1 {
  float: left;
  width: 25%;
}

@media screen and (max-with: 767px) {
  .child1 {
    float: left;
    width: 50%;
  }
}
</pre>

 
 
   
