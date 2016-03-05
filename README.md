# 日历控件

> 引用JSLit.js 下载 [JSLite.io](http://JSlite.io)，兼容 `JSLite` 和 `jQuery`

![日历控件](https://raw.githubusercontent.com/JSLite/calendar/master/calendar.gif "日历控件")  
![日历控件](https://raw.githubusercontent.com/JSLite/calendar/master/calendar2.gif "日历控件")  

## 安装方法

页面引用 `JSLite` 或者`jQuery`  


```html 
<div id="JSLiteCalenbar4"><input type="text"></div>
<script type="text/javascript" src="../JSLite.js"></script>
<script type="text/javascript" src="JSLite.Calendar.js"></script>
<script type="text/javascript">
    var obj4 = document.getElementById("JSLiteCalenbar4")
    var cal=new $.calendar($("#JSLiteCalenbar4")[0],function(date){
        console.log(date);
        //返回更改的时间值date=2014-10-11
        $('#JSLiteCalenbar4 input').val()
        this.calBoxs.prev().val(date)
    })
    .hide()
    .time("yyyy/MM月dd日 hh:mm:ss",'default')
    console.log(cal);
</script>
```

# 扩展方法 

- `hidePrevBtn`:隐藏上一页 按钮 显示未来时间，不能翻阅历史
- `hide`:点击显示界面  
- `setDate`:设置时间，传json
- `time`:设置是否可以选则时间 (时分) 
    "yyyy/MM月dd日 hh:mm:ss" 序列号时间格式
    'default' 默认再`input`中显示默认时间或者指定时间

## hide 

> 点击显示界面

```html
<div id="JSLiteCalenbar2"><div class="">点击显示</div></div>
<script type="text/javascript">
    var obj3 = document.getElementById("JSLiteCalenbar2")
    new $.calendar(obj3,{
        "now":"2014-09-15"
    },function(date){
        //返回更改的时间值date=2014-10-11
        console.log(date)
    }).hide();
</script>
```

## 例子一

```js
var obj3 = document.getElementById("JSLiteCalenbar2")
new JSLite.calendar(obj3,{
    "now":"2014-09-15"
    
},function(date){
    //返回更改的时间值date=2014-10-11
    console.log(date)
    console.log("obj3")
}).time("yyyy/MM月dd日 hh:mm:ss",'default');
 
 
 
var cal = new JSLite.calendar(obj,function(){
    return {
        "now":"2014-09-15",//服务器当前时间
        "change":true,//是否更改当前时间以前的内容
        "interfaceNum":3,//显示当前以后多少个日历
        "workdate":[
            {
                "date":"2013-12",
                "day":["1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "20"] 
            },{
                "date":"2014-09",
                "day":["10", "2", "3", "4", "5", "6", "20"] 
            },{
                "date":"2014-05",
                "day":["10", "2", "3", "4", "5", "6", "20"] 
            },{
                "date":"2014-10",
                "day":["12", "2", "3", "4", "5", "6", "20"] 
            }
        ]
    }
},function(date){
    //返回更改的时间值date=["2014-10-10,0","2014-10-11,0"]
    console.log(date)
}).hidePrevBtn()
```

## 例子二

```js
var obj3 = document.getElementById("JSLiteCalenbar2")
new JSLite.calendar(obj3,function(date){
    //返回更改的时间值date=2014-10-11
    console.log(date)
    console.log("obj3")
}).hidePrevBtn().hide()
```
