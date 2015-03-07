# HTML Colors extended 
 This concept intend to expand the html color names to a more complete panel adding a light & dark tint to the colors.

-------------------------------------

## USAGE
 The file embed pre-created classes, that uses the same names as the colors. 

 Here is how the classes are made : 
 ```scss
 .color{ 
  color: $color;
 }
 .color-light{ 
  color: $color-light;
 }
 .color-dark{ 
  color: $color-light;
 }
 ```

 You can use the classes directly in HTML : 
 ```html
  <div class="foo tomato">
    <p>lorem</p>
  </div>

  <div class="bar tomato-light">
    <p>Ipsum</p>
  </div>

  <div class="baz tomato-dark">
    <p>Dolor</p>
  </div>
 ```

 ```scss
  .foo{
    background: currentColor;
  }

  .bar{
    background: currentColor;
  }

  .baz{
    background: currentColor;
  }
 ```
 *__Use the `currentColor` css variable to extend the `color:` value to the background.__*


---
 You can also extend the classes into your styles : 
  ```html
  <div class="foo">
    <p>lorem</p>
  </div>

  <div class="bar">
    <p>Ipsum</p>
  </div>

  <div class="baz">
    <p>Dolor</p>
  </div>
 ```
 ```scss
  .foo{
    @extend tomato;
  }

  .foo{
    @extend tomato-light;
  }

  .foo{
    @extend tomato-dark;
  }
 ```
---
To define a color without a pre-created class, you can use variables that got the same names ad the colors : 
  ```scss
 .foo{ 
  color: $color-name;
 }
 .bar{ 
  color: $color-name-light;
 }
 .baz{ 
  color: $color-name-dark;
 }
 ```
e.g : 
 ```scss
 .foo{ 
  color: $red;
 }
 .bar{ 
  color: $red-light;
 }
 .baz{ 
  color: $red-dark;
 }
```

Or you can use the color-tint mixin `@include color-tint(<color>, <light/dark>, <ammount>%)` :
 ```scss
 .foo{ 
  @include color-tint(red , light, 15%);
 }
 
 .bar{ 
  @include color-tint(blue , dark, 5%);
 }
 
 .baz{ 
  @include color-tint(green , light, 35%);
 }
 ```

You can use variables in the mixin. 

## Options
There is 2 parameters you can change, and load at the begining of your projects (or pens). They will modify the general tint level of the natives color variables :

```scss
$light-tint: <amount-in-percent>;
$dark-tint: <amount-in-percent>;
```

-------------------------------------

## NOTE
To use the colors as background, use the `currentColor` variable, and if you want to add text in it, simply use a text tag, such as `p`, `h1`, `h2`, or anything else, it's more semantic, and you get more control over your text.

## Example
See it live : [On codepen](http://codepen.io/LukyVj/pen/Wbgjob)
