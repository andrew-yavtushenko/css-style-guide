#Style guides for CSS code

##Indents

1. Horizontal indents (tabs) should be made by spaces (soft-tabs), one indent – two spaces

2. All blocks of rules should be vertically indented with one line

3. Selector name and opening curly brace should be separated with space

4. Colon and rule value should be separated with space

5. If block has only one rule and one selector, selector and rule can stay on one line
  in other case each selector should stay on separate line, same for rules – each of it should stay on separate line
  
6. Rules with browser-specific prefixes should be indented in such way to make values stay on one vertical line

7. On rules with multiple values (box-shadow or gradient ), each value should stay on separate line

###Summary of indents in code

``` css
.my-class {
  height: 300px;
  width: 100px;
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
.another-crossbrowser-class {
  -webkit-box-shadow: 0 0 3px rgba(0,0,0,0.5);
     -moz-box-shadow: 0 0 3px rgba(0,0,0,0.5);
      -ms-box-shadow: 0 0 3px rgba(0,0,0,0.5);
       -o-box-shadow: 0 0 3px rgba(0,0,0,0.5);
          box-shadow: 0 0 3px rgba(0,0,0,0.5);
}

.multiple-values {
  box-shadow: 
    0 0 3px rgba(0,0,0,0.5),
    0 0 10px -2px rgba(0,0,0,0.2),
    0 0 11px #000;
}
```

##Naming

1. Class and ID names should be made with hyphens (-)
```.my-class, .sidebar-my-class``` good, ```.myClass, .my_class, onemoreclass``` bad, ```.lalalaidontknwowhathyphensare``` i find this shit in your code – you're dead

2. Don't use acronyms


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

Try to use such rules in common and avoid using specific rules like ```background-repeat``` or ```border-bottom-color```

Use specific rules when you need to define only this specific rule for current selector, or when you need to redefine existing rule