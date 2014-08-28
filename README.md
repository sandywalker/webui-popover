WebUI-Popover
=============

A lightWeight popover plugin with jquery ,enchance the  popover plugin of bootstrap with some awesome new features. It works well with bootstrap ,but bootstrap is not necessary!


Browser compatibility: ie8+,Chrome,Safari,Firefox,Opera

## Requirement

jquery1.7+,jquery2.x

##Features
* fast speed
* easy trigged by click or hover
* support more placements
* auto caculate placement
* close button in popover
* multipule popovers in same page
* different styles
* support url and iframe


##Getting Started
```javascript
$('.some-trigger').webuiPopover(options);
```

### default options
```javascript
{
        placement:'auto',//values: auto,top,right,bottom,left,top-right,top-left,bottom-right,bottom-left
	width:'auto',//can be set with Number
	height:'auto',//can be set with Number
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





