#Style guides for CSS code

##Indents

1. Horizontal indents (tabs) should be made by spaces (soft-tabs), one indent – two spaces

2. All blocks of rules should be vertically indented with one line

3. Selector name and opening curly brace should be separated with space

4. Colon and rule value should be separated with space

5. If block (selector with one or more rules) has only one rule, it can stay on a same line with selector name
  in other case each selector should stay on separate line, same for rules – each of it should stay on separate line
  
6. Rules with browser-specific prefixes should be indented in such way to make values stay on one vertical line

###Summary of indents in code

``` css
.my-class {
  width: 100px;
  height: 300px;
}

.my-second-class {
  display: block;
  position: relative;
}

.class-with-one-rule {position: relative;}

.class-one,
.class-two,
.class-three {
  background: #ccc;
}

.my-crossbrowser-class {
  background-image: -webkit-linear-gradient(#444, #222);
  background-image:    -moz-linear-gradient(#444, #222);
  background-image:     -ms-linear-gradient(#444, #222);
  background-image:      -o-linear-gradient(#444, #222);
  background-image:         linear-gradient(#444, #222);
}
```

##Complex rules

Some of the rules in CSS can handle many properties

for example:

```css
.my-class {
  background: url(images/cat.png) no-repeat center top #fff;
  border: 1px solid #fff;
  box-shadow: 
    0 0 3px rgba(0,0,0,0.5),
    0 0 10px -2px rgba(0,0,0,0.2),
    0 0 11px #000;
  margin: 10px 30px;
  padding: 10px 10px 20px 30px;
}

```