---
title: tips of js, css and html
date: 2017-06-23 10:30:26
categories: Web #文章文类
tags: [javascript, css, html] #文章标签，多于一项时用这种格式
---

# Difference between auto and 100%

parent div height by default is auto, which will be regulated by their children div.
childern div height 100%, will match and follow parent's height. 

<!--more-->
 
# Automatic correction in textarea

``` html
<textarea name="nTa" id="iTa" cols="30" rows="10" spellcheck="true" autocapitalize="true" autocomplete="true" autocorrect="true"></textarea>
```
spellcheck is the attribute to set to determine if to check user's spell, just like its name said.


# float and clear left to make div display in a line 

``` html
<div style="margin: 10px">
	<div id="chartdiv" style="height:400px;width:300px; float: left;"></div>
    <div id="chartdiv1" style="height:400px;width:300px; margin-left: 65px; float: left;"></div>
</div>

<div style="margin: 10px; clear: left;">
    <div id="chartdiv2" style="height:400px;width:300px; float: left;"></div>	
    <div id="chartdiv3" style="height:400px;width:100%; max-width: 400px; margin-left: 65px; float: left;"></div>	
</div>


<div style="clear: left">
    <div id="idDiv1" data-div1="567" style="width:auto; height: auto; border: 1px solid red;">
        <div style="border: 2px solid yellow; width:200px; height:200px">
            abc
        </div>
    </div>
</div>
```

alternative if use div's display attribute, set it to inline-block, which could by easier. But in some cases, display need to set to another value, like block, if you changed it, that could change the whole style of the element. In such cases, combination of float and clear would be a good idea.


# js prototype function: call

``` js
$("#idBtn1").click(function(argument) {
    setTimeout(function(){
        console.log(this);
    }, 100);
})

$("#idBtn2").click(function(argument) {
    setTimeout(function(){
        console.log(this);
        console.log(this.attr("id"));
    }.call($(this)), 100);
}) 
```
in case one, it will print the window DOM object.
in case one, it will print jQuery button object, because it has binded the new context to the function.

