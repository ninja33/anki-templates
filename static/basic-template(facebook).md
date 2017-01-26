#Anki 基本模板 Facebook样式

## 正面模板(Front Template)
```html
<!-- 页眉区块 -->
<div class="bar head">牌组名称 : {{Deck}}</div>

<!-- 正面区块 -->
<div class="section">
<div id="front" class="items">{{正面}}</div>

<!-- 本行为注释，如需使用额外字段，请删除本行与后面的注释行
<div id="front-extra1" class="items">正面额外字段名1</div>
<div id="front-extra2" class="items">正面额外字段名2</div>
本行为注释，如需使用额外字段，请删除本行与上面的注释行 -->

</div>
```

## 样式(Styling)
```css
</style>

<!-- 
Anki 基本模板 Facebook样式
作者：你家老黄（ninja33）
网址：http://ninja33.github.io
QQ群：25091023
 -->

<style>

/*卡片全局样式*/
.card {
  font-family      : helvetica, arial, sans-serif; /*字体名称*/
  font-size        : 14px;    /*字体大小-14px*/
  text-align       : left;    /*对齐方式-左对齐*/
  color            : #1d2129; /*字体颜色-#1d2129*/
  background-color : #e9ebee; /*背景颜色-#e9ebee*/
}

/*页眉页脚全局样式*/
.bar{
  border-radius   : 3px;               /*圆角幅度-3px*/
  border-bottom   : 1px solid #29487d; /*底边线颜色-#29487d*/
  color           : #fff;              /*字体颜色-白色*/ 
  padding         : 5px;               /*四周留白-5px*/ 
  text-decoration : none;              /*文本修饰-无*/ 
  font-size       : 12px;              /*字体大小-12px*/ 
  font-weight     : bold;              /*字体磅数-加粗*/
}

.bar #url a{
  text-decoration : none;
  font-size       : 12px;
  color           : #fff;
  font-weight     : bold;
}

/*页眉样式*/
.head{
  padding-left : 25px;  /*左侧留白-25px 为图标预留空间*/
  background   : #365899 url(_clipboard.png) no-repeat /*记事本图标*/
}

/*页脚样式*/
.foot{
  padding-right : 25px;  /*右侧留白-25px 为图标预留空间*/
  text-align    : right; /*文本右对齐*/
  background    : #365899 url(_cloud.png) no-repeat right /*云端图标*/
}

/*区块全局样式*/
.section {
  border           : 1px solid;               /*边缘样式-实线1px*/
  border-color     : #e5e6e9 #dfe0e4 #d0d1d5; /*边缘颜色*/
  border-radius    : 3px;                     /*圆角幅度-3px*/
  background-color : #fff;                    /*背景颜色-白色*/
  position         : relative;                /*定位-相对定位*/
  margin           : 5px 0;                   /*间隔-上下5px，左右0px*/ 
}

/*区块项全局样式*/
.items{
  font-size  : 12px;               /*字体大小-12px*/
  border-top : 1px solid #e5e5e5;  /*边缘样式-实线1px*/
  margin     : 0 12px;             /*区块间隔*/
  padding    : 10px 0 8px 0;       /*区块留白*/
}

/*正面背面全局样式*/
#front, 
#back{
  border-top  : 0px;        /*顶部边线-0px，防止和定期区块边线重叠*/
  line-height : 1.2em;      /*段落行高-1.2em*/
}

/*正面字段样式*/
#front{
  font-size  : 24px;       /*字体大小-24px*/
  color      : #000;       /*字体颜色-黑色*/
  text-align : left;       /*文本对齐-居左*/
}

/*背面字段样式*/
#back{
  font-size  : 16px;       /*字体大小-16px*/
  color      : #0000ff;    /*字体颜色-蓝色*/
  text-align : left;       /*文本对齐-居左*/
}

/*额外字段预留样式*/
#front-extra1{
}
#front-extra2{
}
#back-extra1{
}
#back-extra1{
}

</style>

<!-- 
JS帮助函数
效果：折叠展开效果。点击特定的区块/图片后，使指定的某区块折叠或展开
用法：将函数toggle赋予区块或者图片的onclick事件，并将e命名为要折叠的区块ID
举例：点击页眉，将正面区块折叠，可以按如下方式操作
在页眉的区块中加onclick=toggle(e），其中将e命名为要折叠的区块ID'front'
修改后的页眉区块如下
<div class="bar head" onclick="toggle('front')">牌组名称 : {{Deck}}</div>
-->
<script>
function toggle(e){
	var box=document.getElementById(e);
	if(box.style.display=='none'){
		box.style.display='block';
	}
	else{
		box.style.display='none';
	}
}
</script>

<style>
```
## 背面模板(Back Template)
```html
{{FrontSide}}

<!-- 背面区块 -->
<div class="section">
<div id="back" class="items">{{背面}}</div>

<!-- 本行为注释，如需使用额外字段，请删除本行与后面的注释行
<div id="back-extra1" class="items">背面额外字段名1</div>
<div id="back-extra2" class="items">背面额外字段名2</div>
本行为注释，如需使用额外字段，请删除本行与上面的注释行 -->

</div>

<!-- 页脚区块 -->
<!-- 如有外部引用的网址，可以将下列 href="#" 改成 href={{网址字段}}-->
<div class="bar foot">
  <div id="url"><a href="#">网址信息</a></div>
</div>


<!-- 
JS帮助函数
效果：词性彩色高亮。在指定的区块中，若有英语词性符号，则高亮成预定义的彩色背景
用法：将下列函数querySelectorAll('#back')中的back，换成含有英语词性的区块ID
举例：比如正面字段所在区块ID:front包含了形如Test - 'n.测试'这样的英语单词解释，需要高亮词性n. 那么只要把下列函数中相应地方改为querySelectorAll('#front')就可以了
-->

<script type="text/javascript">
var colorMap = {
    'n.':'#e3412f',
    'a.':'#f8b002',
    'adj.':'#f8b002',
    'ad.':'#684b9d',
    'adv.':'#684b9d',
    'v.':'#539007',
    'vi.':'#539007',
    'vt.':'#539007',
    'prep.':'#04B7C9',
    'conj.':'#04B7C9',
    'pron.':'#04B7C9',
    'art.':'#04B7C9',
    'num.':'#04B7C9',
    'int.':'#04B7C9',
    'interj.':'#04B7C9',
    'modal.':'#04B7C9',
    'aux.':'#04B7C9',
    'pl.':'#D111D3',
    'abbr.':'#D111D3',
  };
  [].forEach.call(document.querySelectorAll('#back'), function(div) {
  div.innerHTML = div.innerHTML
  .replace(/\b[a-z]+\./g, function(symbol) {
    if(colorMap[symbol]) {
      return '<a style="background-color:' + colorMap[symbol] + ';border-radius: 4px; color:white; padding:0 3px;margin-right:5px">'+
      symbol + '</a>';
    }else{
      return symbol;
    }
  });
 });

</script>

```
