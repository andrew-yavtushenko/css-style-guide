#Style guides for CSS code

##Style Rules
* ####Use valid CSS where possible.
  Unless dealing with CSS validator bugs or requiring proprietary syntax, use valid CSS code.     
  Use tools such as the [W3C CSS](http://jigsaw.w3.org/css-validator/) validator to test.     
  Using valid CSS is a measurable baseline quality attribute that allows to spot CSS code that may not have any effect and can be removed, and that ensures proper CSS usage.

* ####Use IDs only for javascript   

* ####Class and ID names should be made with dash (-)       
  #####good:       
  ```css
    .my-class, #special-offer
  ```     
  #####bad:     
  ```css
    .myClass, .my_class, onemoreclass
  ```     

* ####Always use low register names     
  #####good:      
  ```css
    .my-class
  ```
  #####bad:
  ```css
    .MY-CLASS, .myClass, .MyClass, .MyClAsS  
  ```

* ####Use ID and class names that are as short as possible but as long as necessary.    
  #####good:    
  ```css
    .nav, .author
  ```     
  #####bad:   
  ```css
    .navigation, .atr
  ```    

* ####Name classes and ID semantically, i.e. name it not by it's look but by it's function   
  #####good:
  ```css
    .promo-box, .selected-user, .remove-button
  ```   
  #####bad:
  ```css
    .black-box, .yellow-user, .red-button
  ```   
  if you can't make readable name for new class – you don't know what you're doing, read docs carefully one more time or ask someone

* ####Avoid qualifying ID and class names with type selectors.
  Unless necessary (for example with helper classes), do not use element names in conjunction with IDs or classes.
  #####good:
  ```css
    .example, .error
  ```
  #####bad:
  ```css
    ul.example, div.error
  ```
  
* ####Use shorthand properties where possible.     
  #####good:
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
  #####bad:
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
    }
  ```

* ####Do not use units after 0 values unless they are required.
  #####good:    
  ```css
    margin: 0;
    padding: 0;
  ```
  #####bad:    
  ```css
    margin: 0px;
    padding: 0px;
  ```

* ####Do not use put 0s in front of values or lengths between -1 and 1.    
  #####good:     
  ```css
    font-size: .8em;
  ```    
  #####bad:    
  ```css
    font-size: 0.8em;
  ```    

* ####For color values that permit it, 3 character hexadecimal notation is shorter and more succinct.   
  #####good:     
  ```css
    color: #ebc;
  ```    
  #####bad:    
  ```css
    color: #eebbcc;
  ```

* ####Avoid user agent detection as well as CSS “hacks”—try a different approach first.   
  It’s tempting to address styling differences over user agent detection or special CSS filters, workarounds, and hacks. Both approaches should be considered last resort in order to achieve and maintain an efficient and manageable code base. Put another way, giving detection and hacks a free pass will hurt projects in the long run as projects tend to take the way of least resistance. That is, allowing and making it easy to use detection and hacks means using detection and hacks more frequently—and more frequently is too frequently.

##Formating rules

* ####Horizontal indents (tabs) should be made by spaces (soft-tabs), one indent – two spaces    
  #####good:      
  ```css
    .my-class {
      height: 300px;
      width: 100px;
    }
  ```

* ####All blocks of rules should be vertically indented with one line
  #####good:      
  ```css
    .my-class {
      height: 300px;
      width: 100px;
    }   

    .another-class {
      height: 400px;
      width: 200px;
    }
  ```
  #####bad:      
  ```css
    .my-class {
      height: 300px;
      width: 100px;
    }   
    .another-class {
      height: 400px;
      width: 200px;
    }
  ```

* ####Selector name and opening curly brace should be separated with space      
  #####good:    
  ```css
    .class {rule: value;}
  ```   
  #####bad:     
  ```css
    .class{rule: value;}
  ```   

* ####Colon and rule value should be separated with space    
  #####good:      
  ```css
    .class {rule: value;}
  ```   
  #####bad:       
  ```css
    .class{rule:value;}
  ```    

* ####If block has only one rule and one selector, selector and rule can stay on one line
  in other case each selector should stay on separate line, same for rules – each of it should stay on separate line    
  #####good:
  ```css
    .class-one,
    .class-two,
    .class-three {
      display: block;
      position: relative;
    }
    
    .class-three {
      display: block; 
      position: relative;
    }
    
    .lonely-rule {position: relative;}
  ```
  #####bad:
  ```css
    .class-one, .class-two, .class-three {
      display: block;
      position: relative;
    }
    .class-three {
      display: block; position: relative;
    }
  ```
  
* ####Rules with browser-specific prefixes should be indented in such way to make values stay on one vertical line
  ```css
    .my-crossbrowser-class {
      background-image:    -moz-linear-gradient(#444, #222);
      background-image:     -ms-linear-gradient(#444, #222);
      background-image:      -o-linear-gradient(#444, #222);
      background-image: -webkit-linear-gradient(#444, #222);
      background-image:         linear-gradient(#444, #222);
    }
    .another-crossbrowser-class {
         -moz-box-shadow: 0 0 3px rgba(0,0,0,0.5);
          -ms-box-shadow: 0 0 3px rgba(0,0,0,0.5);
           -o-box-shadow: 0 0 3px rgba(0,0,0,0.5);
      -webkit-box-shadow: 0 0 3px rgba(0,0,0,0.5);
              box-shadow: 0 0 3px rgba(0,0,0,0.5);
    }
  ```

* ####On rules with multiple values (box-shadow or gradient), each value should stay on separate line
  ``` css
    .multiple-values {
      box-shadow: 
        0 0 3px rgba(0,0,0,0.5),
        0 0 10px -2px rgba(0,0,0,0.2),
        0 0 11px #000;
    }
  ```
* ####Use single quotation marks for attribute selectors and property values where necessary.
  When quoting attribute selectors and property values, use single ('') rather than double ("") quotation marks. Do not use quotation marks in URI values (url()).    
  #####good:
  ```css
    body {
      background: url(images/cat.png)
    }

    html {
      font-family: 'open sans', arial, sans-serif;
    }
  ```
  #####bad:
  ```css
    body {
      background: url("images/cat.png")
    }

    html {
      font-family: "open sans", arial, sans-serif;
    }
  ```

* ####Alphabetize declarations    
  Put declarations in alphabetical order in order to achieve consistent code in a way that is easy to remember and maintain. Ignore vendor-specific prefixes for sorting purposes.
  
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
  
  
##Sources

![I don't know what i'm doing](blob/master/dog.jpg "Doggy")