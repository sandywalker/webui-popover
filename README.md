WebUI-Popover
=============

A lightWeight popover plugin with jquery ,enchance the  popover plugin of bootstrap with some awesome new features. It works well with bootstrap ,but bootstrap is not necessary!


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

##Demo
[WebUI Popover Demo](http://sandywalker.github.io/webui-popover/demo/)

##Getting Started

####Including it on your page
```html
<link rel="stylesheet" href="jquery.webui-popover.css">
...
<script src="jquery.js"></script>
<script src="jquery.webui-popover.js"></script>
```

####Use the plugin as follows:

```javascript
$('a').webuiPopover(options);
```

####Some Examples:

Create  Simplest Popover
```javascript
$('a').webuiPopover({title:'Title',content:'Content'});
```

Create  Popover by dom element data-* attribute
```html
<a href="#" data-title="Title" data-content="Contents..." data-placement="right"></a>
```
```javascript
$('a').webuiPopover();
```

Create  Popover with bottom placement
```javascript
$('a').webuiPopover({title:'Title',content:'Content',placement:'bottom'});
```

Create  Popover trigged by mouse hover
```javascript
$('a').webuiPopover({title:'Title',content:'Content',trigger:'hover'});
```

Create  inversed style Popover 
```javascript
$('a').webuiPopover({title:'Title',content:'Content',style:'inverse'});
```
Create  Popover with fixed width and height
```javascript
$('a').webuiPopover({title:'Title',content:'Content',width:300,height:200});
```

Create  Popover with close button
```javascript
$('a').webuiPopover({title:'Title',content:'Content',closeable:true});
```

Create  and Animate the Popover 
```javascript
$('a').webuiPopover({title:'Title',content:'Content',animation:'pop'});
```

Create  Popover with iframe
```javascript
$('a').webuiPopover({type:'iframe',url:'http://getbootstrap.com'});
```

Create  Popover Async Mode
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





### default options
```javascript
{
	placement:'auto',//values: auto,top,right,bottom,left,top-right,top-left,bottom-right,bottom-left,auto-top,auto-right,auto-bottom,auto-left
	width:'auto',//can be set with  number
	height:'auto',//can be set with  number
	trigger:'click',//values:  click,hover,manual
	style:'',//values:'',inverse
	constrains:null, // constrains the direction when placement is  auto,  values: horizontal,vertical
	animation:null, //pop with animation,values: pop,fade (only take effect in the browser which support css3 transition)
	delay: {//show and hide delay time of the popover, works only when trigger is 'hover',the value can be number or object
	    show: null,
	    hide: 300
	},
	async: {
	    before: function(that, xhr) {},//executed before ajax request
	    success: function(that, data) {}//executed after successful ajax request
	},
	cache:true,//if cache is set to false,popover will destroy and recreate
	multi:false,//allow other popovers in page at same time
	arrow:true,//show arrow or not
	title:'',//the popover title ,if title is set to empty string,title bar will auto hide
	content:'',//content of the popover,content can be function
	closeable:false,//display close button or not
	padding:true,//content padding
	type:'html',//content type, values:'html','iframe','async'
	url:''//if not empty ,plugin will load content by url
}
```





