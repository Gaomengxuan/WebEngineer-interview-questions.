### 怎么样评价 Vue
* 其实Vue.js不是一个框架，因为它只聚焦视图层，是一个构建数据驱动的Web界面的库
* Vue.js通过简单的API（应用程序编程接口）提供高效的数据绑定和灵活的组件系统。
* 轻量级的框架
* 双向数据绑定
* 指令
* 插件化

### Vue.js与其他框架的区别？
####相同点：
* 都支持指令：内置指令和自定义指令。

* 都支持过滤器：内置过滤器和自定义过滤器。

* 都支持双向数据绑定。

* 都不支持低端浏览器。

####不同点：

* AngularJS的学习成本高，比如增加了Dependency Injection特性，而Vue.js本身提供的API都比较简单、直观。

* 在性能上，AngularJS依赖对数据做脏检查，所以Watcher越多越慢。

* Vue.js使用基于依赖追踪的观察并且使用异步队列更新。所有的数据都是独立触发的。对于庞大的应用来说，这个优化差异还是比较明显的。


###Vue与React的区别

####相同点：

* React采用特殊的JSX语法，Vue.js在组件开发中也推崇编写.vue特殊文件格式，对文件内容都有一些约定，两者都需要编译后使用。

* 中心思想相同：一切都是组件，组件实例之间可以嵌套。

* 都提供合理的钩子函数，可以让开发者定制化地去处理需求。

* 都不内置列数AJAX，Route等功能到核心包，而是以插件的方式加载。

* 在组件开发中都支持mixins的特性。

####不同点：

* React依赖Virtual DOM,而Vue.js使用的是DOM模板。React采用的Virtual DOM会对渲染出来的结果做脏检查。

* Vue.js在模板中提供了指令，过滤器等，可以非常方便，快捷地操作DOM。
### 怎么判断设备类型 ，meta标签和js判断设备类型   （navigator.userAgent判断浏览器类型）
* 方法1

```
var os = function() {
     var ua = navigator.userAgent,
     isWindowsPhone = /(?:Windows Phone)/.test(ua),
     isSymbian = /(?:SymbianOS)/.test(ua) || isWindowsPhone, 
     isAndroid = /(?:Android)/.test(ua), 
     isFireFox = /(?:Firefox)/.test(ua), 
     isChrome = /(?:Chrome|CriOS)/.test(ua),
     isTablet = /(?:iPad|PlayBook)/.test(ua) || (isAndroid && !/(?:Mobile)/.test(ua)) || (isFireFox && /(?:Tablet)/.test(ua)),
     isPhone = /(?:iPhone)/.test(ua) && !isTablet,
     isPc = !isPhone && !isAndroid && !isSymbian;
     return {
          isTablet: isTablet,
          isPhone: isPhone,
          isAndroid : isAndroid,
          isPc : isPc
     };
}();
```

* 方法2

```

(function(){
    var res = GetRequest();
    var par = res['index'];
    if(par!='gfan'){
        var ua=navigator.userAgent.toLowerCase();
        var contains=function (a, b){
            if(a.indexOf(b)!=-1){return true;}
        };
        var toMobileVertion = function(){
            window.location.href = 'http://caibaojian.com/'
        }

        if(contains(ua,"ipad")||(contains(ua,"rv:1.2.3.4"))||(contains(ua,"0.0.0.0"))||(contains(ua,"8.0.552.237"))){return false}
        if((contains(ua,"android") && contains(ua,"mobile"))||(contains(ua,"android") && contains(ua,"mozilla")) ||(contains(ua,"android") && contains(ua,"opera"))
    ||contains(ua,"ucweb7")||contains(ua,"iphone")){toMobileVertion();}
    }
})();
function GetRequest() {
   var url = location.search; //获取url中"?"符后的字串
   var theRequest = new Object();
   if (url.indexOf("?") != -1) {
      var str = url.substr(1);
      strs = str.split("&");
      for(var i = 0; i < strs.length; i ++) {
         theRequest[strs[i].split("=")[0]]=unescape(strs[i].split("=")[1]);
      }
   }
   return theRequest;
}

```
















