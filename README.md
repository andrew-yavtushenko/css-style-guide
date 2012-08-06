#Style guides for CSS code

##Indents

1. Horizontal indents (tabs) should be made by spaces (soft-tabs), one indent – two spaces

2. All blocks of rules should be vertically indented with one line

3. Selector name and opening curly brace should be separated with space

4. Colon and rule value should be separated with space

5. If block has only one rule and one selector, selector and rule can stay on one line
  in other case each selector should stay on separate line, same for rules – each of it should stay on separate line
  
6. Rules with browser-specific prefixes should be indented in such way to make values stay on one vertical line

7. On rules with multiple values (box-shadow or gradient), each value should stay on separate line

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

1. Use IDs only for javascript

2. Class and ID names should be made with dash (-)   
######good:
```.my-class, #special-offer```    
####bad:
```.myClass, .my_class, onemoreclass```   

3. Always user low register

4. Use ID and class names that are as short as possible but as long as necessary.
######good:
```.nav, .author```   
######bad:
```.navigation, .atr```    

5. Name classes and ID semantically, i.e. name it not by it's look but by it's function   
######good:
```.promo-box, .selected-user, .remove-button```   
######bad:
```.black-box, .yellow-user, .red-button```   
if you can't make readable name for new class – you don't know what you're doing, read docs carefully one more time or ask someone

6. Avoid qualifying ID and class names with type selectors.
Unless necessary (for example with helper classes), do not use element names in conjunction with IDs or classes.
######good:
```.example, .error```
######bad:
```ul.example, div.error```
  
7. Use shorthand properties where possible.     

######good
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
######bad
```css
.my-class {
  box-shadow: rgba(0, 0, 0, 0.5) 0px 0px 3px 0px, rgba(0, 0, 0, 0.2) 0px 0px 10px -2px, black 0px 0px 11px 0px;
  background-color: #fff;
  background-image: url(images/cat.png);
  border-color: white;
  border-style: solid;
  border-width: 1px;
  margin-bottom: 10px;
  margin-left: 30px;
  margin-right: 30px;
  margin-top: 10px;
  padding-bottom: 20px;
  padding-left: 30px;
  padding-right: 10px;
  padding-top: 10px;
}```

8. Do not use units after 0 values unless they are required.
######good    
```
  margin: 0;
  padding: 0;
```