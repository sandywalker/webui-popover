WebUI-Popover
=============

A lightWeight popover plugin with jquery ,enchance the  popover plugin of bootstrap with some awesome new features. It works well with bootstrap ,but bootstrap is not necessary!


Browser compatibility: ie8+,Chrome,Safari,Firefox,Opera

## Requirement

jquery1.7+,jquery2.x

##Features
* fast,lightweight
* easy trigged by click or hover
* support more placements
* auto caculate placement
* close button in popover
* multipule popovers in same page
* different styles
* support url and iframe


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
$('.some-trigger').webuiPopover(options);
```

Create  Simplest Popover
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',content:'Pop content'});
```

Create  Popover with bottom placement
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',content:'Pop content',placement:'bottom'});
```

Create  Popover trigged by mouse hover
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',content:'Pop content',trigger:'hover'});
```

Create  inversed style Popover 
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',content:'Pop content',style:'inverse'});
```
Create  Popover with fixed width and height
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',content:'Pop content',width:300,height:200});
```

Create  Popover with close button
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',content:'Pop content',closable:true});
```

Create  Popover with iframe
```javascript
$('.some-trigger').webuiPopover({title:'Pop title',url:'http://getbootstrap.com',iframe:true});
```





### default options
```javascript
{
	placement:'auto',//values: auto,top,right,bottom,left,top-right,top-left,bottom-right,bottom-left
	width:'auto',//can be set with  number
	height:'auto',//can be set with  number
	trigger:'click',//values:click,hover
	style:'',//values:'',inverse
	delay:300,//delay time of the popover, works only when trigger is 'hover'
	cache:true,//if cache is set to false,popover will destroy and recreate
	multi:false,//allow other popovers in page at same time
	arrow:true,//show arrow or not
	title:'',//the popover title ,if title is set to empty string,title bar will auto hide
	content:'',//content of the popover,content can be function
	closeable:false,//display close button or not
	padding:true,//content padding
	iframe:false,//iframe or not
	url:''//if not empty ,plugin will load content by url, 'content' option will be ignored
}
```





