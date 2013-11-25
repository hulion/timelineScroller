timelineScroller
================

利用TweenMax的timeline，簡化捲軸式網站的語法...


HTML code

<css歸零>
<link href="css/css_reset.css" rel="stylesheet" type="text/css">

<載入外部JS>
<script src="js/jquery-1.10.2.min.js"></script>
<script src="js/gs/TweenMax.min.js"></script>
<script src="js/gs/TimelineMax.min.js"></script>

<捲軸框架設定>
<div id="scrollbox"></div>

<載入捲軸語法js>
<script src="js/scrollerJS.js"></script>




CSS code

設定整個html總長度 - 時間軸長度
#scrollBox{ width:100%; height:6000px; }




JS code

timelineSetHandler() 函式 =====================================================================

/*設定動態*/
		
//第一段動畫
tl.from("#logo", 2, {top:1000, ease:Quart.easeOut})
  .add("label_01"); //設定動畫標籤1
		  
//第二段動畫
tl.to("#logo", 2, {top:-100, delay:1, ease:Power1.easeIn})
  .from("#img01", 3, {top:1000, ease:Quart.easeOut}, '-=2')
  .add("label_02"); //設定動畫標籤2
		
//第三段動畫
tl.from("#end", 2, {rotation:120, left:-2000, top:1000, ease:Power1.easeInOut})
  .to("#img01", 1, {rotation:120, left:2000, top:0, ease:Power1.easeInOut}, '-=0.9')
  .add("label_03"); //設定動畫標籤3


resizeHandler() 函式 =====================================================================

/*設定所有物件的初始位置*/
TweenLite.to($("#logo"), 0, { rotation:0, left:sw/2 - $('#logo').width()/2, top:sh/2 - $('#logo').height()/2 });

TweenLite.to($("#img01"), 0, { rotation:0, left:sw/2 - $('#img01').width()/2, top:sh/2 - $('#img01').height()/2 });

TweenLite.to($("#end"), 0, { rotation:0, left:sw/2 - $('#end').width()/2, top:sh/2 - $('#end').height()/2 });




