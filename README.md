WebUI-Popover
=============

A lightWeight popover plugin with jquery, enchance the  popover plugin of bootstrap with some awesome new features. It works well with bootstrap, but bootstrap is not necessary!


Browser compatibility: ie8+,Chrome,Safari,Firefox,Opera

## Requirement

jquery1.7+

##Features
* fast,lightweight
* support more placements
* auto caculate placement
* close button in popover
* multipule popovers in same page
* different styles
* support url and iframe
* support async mode
* different animations
* support backdrop


##NPM
```bash
  npm install webui-popover
```

##Bower
```bash
  bower install webui-popover
```

##CDN
WebUI Popover Support CDN from version 1.2.1, avaliable on [JSDELIVR](http://www.jsdelivr.com/?query=webui-popover)

##Demo
[WebUI Popover Demo](http://sandywalker.github.io/webui-popover/demo/)

##Getting Started

####Including it on your page
Localfile
```html
<link rel="stylesheet" href="jquery.webui-popover.css">
...
<script src="jquery.js"></script>
<script src="jquery.webui-popover.js"></script>
```
Or CDN

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/jquery.webui-popover/1.2.1/jquery.webui-popover.min.css">
...
<script src="https://cdn.jsdelivr.net/jquery/1.11.3/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/jquery.webui-popover/1.2.1/jquery.webui-popover.min.js"></script>
```

####Use the plugin as follows:

```javascript
$('a').webuiPopover(options);
```

####Some Examples:

 Simplest Popover
```javascript
$('a').webuiPopover({title:'Title',content:'Content'});
```

 Create Popover by dom element data-* attribute
```html
<a href="#" data-title="Title" data-content="Contents..." data-placement="right">show pop</a>
```
```javascript
$('a').webuiPopover();
```

 Popover  content can  be easily setted by next element with class 'webui-popover-content'
 ```html
<a href="#" >shop pop</a>
<div class="webui-popover-content">
	<p>popover content</p>
</div>
 ```
 ```javascript
$('a').webuiPopover();
 ```

 Or, just use jQuery selector (id selector recommended) to set the Popover content.

 ```html
<a href="#" >shop pop</a>
<div id="myContent">
	<p>popover content</p>
</div>
 ```
 ```javascript
$('a').webuiPopover({url:'#myContent'});
 ```

 Popover with specified placement.
```javascript
$('a').webuiPopover({title:'Title',content:'Content',placement:'bottom'});
```

 Popover trigged by mouse hover.
```javascript
$('a').webuiPopover({content:'Content',trigger:'hover'});
```

 Create Sticky Popover.
```javascript
$('a').webuiPopover({content:'Content',trigger:'sticky'});
```

 Popover with inversed style.
```javascript
$('a').webuiPopover({content:'Content',style:'inverse'});
```
 Popover with fixed width and height
```javascript
$('a').webuiPopover({content:'Content',width:300,height:200});
```

 Popover with close button
```javascript
$('a').webuiPopover({title:'Title',content:'Content',closeable:true});
```

 Animate the Popover
```javascript
$('a').webuiPopover({title:'Title',content:'Content',animation:'pop'});
```

 Popover with iframe
```javascript
$('a').webuiPopover({type:'iframe',url:'http://getbootstrap.com'});
```


 Async Mode
```javascript
$('a').webuiPopover({
						type:'async',
						url:'https://api.github.com/',
						content:function(data){
 							var html = '<ul>';
 							for(var key in data){html+='<li>'+data[key]+'</li>';}
							html+='</ul>';
							return html;
						}
 					});
```

 Async simply by url
 ```javascript
$('a').webuiPopover({
	type:'async',
	url:'http://some.website/htmldata'
});
 ```

 Trigger the Popover by manual
```javascript
 //Initailize
 $('a').webuiPopover({trigger:'manual'});
...

 //Show it
 $('a').webuiPopover('show');

 //Hide it
 $('a').webuiPopover('hide');

```



### default options
```javascript
{
	placement:'auto',//values: auto,top,right,bottom,left,top-right,top-left,bottom-right,bottom-left,auto-top,auto-right,auto-bottom,auto-left,horizontal,vertical
    container: document.body,// The container in which the popover will be added (i.e. The parent scrolling area). May be a jquery object, a selector string or a HTML element. See https://jsfiddle.net/1x21rj9e/1/
	width:'auto',//can be set with  number
	height:'auto',//can be set with  number
	trigger:'click',//values:  click,hover,manual(handle events by your self),sticky(always show after popover is created);
	style:'',//values:'',inverse
	animation:null, //pop with animation,values: pop,fade (only take effect in the browser which support css3 transition)
	delay: {//show and hide delay time of the popover, works only when trigger is 'hover',the value can be number or object
	    show: null,
	    hide: 300
	},
	async: {
		type:'GET', // ajax request method type, default is GET
	    before: function(that, xhr) {},//executed before ajax request
	    success: function(that, data) {}//executed after successful ajax request
	    error: function(that, xhr, data) {} //executed after error ajax request
	},
	cache:true,//if cache is set to false,popover will destroy and recreate
	multi:false,//allow other popovers in page at same time
	arrow:true,//show arrow or not
	title:'',//the popover title, if title is set to empty string,title bar will auto hide
	content:'',//content of the popover,content can be function
	closeable:false,//display close button or not
  direction:'', // direction of the popover content default is ltr ,values:'rtl';
	padding:true,//content padding
	type:'html',//content type, values:'html','iframe','async'
	url:'',//if type equals 'html', value should be jQuery selecor.  if type equels 'async' the plugin will load content by url.
	backdrop:false,//if backdrop is set to true, popover will use backdrop on open
	dismissible:true, // if popover can be dismissed by  outside click or escape key
	autoHide:false, // automatic hide the popover by a specified timeout, the value must be false,or a number(1000 = 1s).
	offsetTop:0,  // offset the top of the popover
	offsetLeft:0,  // offset the left of the popover
	onShow: function($element) {}, // callback after show
	onHide: function($element) {}, // callback after hide
}
```

###Global Methods

In some situation, you may want to manipulate the plugin like 'show/hide' popovers by  global methods.  The new object **WebuiPopovers** is introduced and exposed to the global window object, so you can access these methods like 'WebuiPopovers.someMethod()...'. 

Here are examples of calling code.

```javascript

//Show Popover by click other element.
$('a').on('click',function(e){
	e.stopPropagation(); // Stop event propagation is needed, otherwise may trigger the document body click event handled by plugin.
	WebuiPopovers.show('#mypop');
});


//Hide Popover by jQuery selector
WebuiPopovers.hide('#mypop');

//Hide All Popovers
WebuiPopovers.hideAll();


```



Welcome to visit my github page: [http://sandywalker.github.io/]
