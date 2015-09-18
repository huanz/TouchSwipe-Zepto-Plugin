最近做webAPP应用用到一些touch事件，找了很多touch的库（包括zepto的touch模块），在手机上测试都是有各种各样的问题，要么就滑不动，要么只能左右滑动不能上下滑动等，终于找到一个好用强大的touch库，但是只有jquery版本的，然后我就把它改成了也兼容zepto的版本放到了这里。

github项目地址：[https://github.com/mattbryson/TouchSwipe-Jquery-Plugin](https://github.com/mattbryson/TouchSwipe-Jquery-Plugin)

本改装是基于官网的1.6.9，只需要zepto的核心模块：zepto,event,data(可选)


# Demos #

### Basic swipe ###

events: `swipe`,`swipeLeft`, `swipeRight`, `swipeUp`, `swipeDown`

	$("#test").swipe( {
		swipe:function(event, direction, distance, duration, fingerCount, fingerData) {
			$("#test").text("You swiped " + direction + " with " + fingerCount + " fingers");
		},
		threshold:0,
		fingers:'all'
	});

**threshold**

Default is 75px, set to 0 for demo so any distance triggers swipe

**fingers**

By setting the number of fingers to 'all', any number of fingers will trigger the swipe.

### Single swipe ###

events: `swipeLeft`, `swipeRight`, `swipeUp`, `swipeDown`, `swipe`


      $("#test").swipe({
		swipeLeft:function(event, direction, distance, duration, fingerCount) {
          $(this).text("You swiped " + direction + " " + ++count + " times " );  
        },
        threshold:0
      });
   

### Finger swipe ###

	 $("#test").swipe({
		swipeStatus:function(event, phase, direction, distance, duration, fingers, fingerData) {
			if(phase==$.fn.swipe.phases.PHASE_START) {
          		$(this).text("moving...");
        	} 
        	if(phase==$.fn.swipe.phases.PHASE_CANCEL) {
          		$(this).text("swipe cancelled (due to finger count) "  );
        	}   
        },
        swipe:function(event, direction, distance, duration, fingerCount, fingerData) {
          $(this).text("You swiped " + direction + " with " + fingerCount + " fingers");
        },
        threshold:0,
        fingers:2
      });

### Pinch ###

....

功能很强大，可以看example








