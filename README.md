找几个免费的获取地理位置的接口
==========================

检索了一下，发现腾讯、淘宝、新浪这么大地方都是有的。

但是准确定却不是很理想，很是苦恼啊！！

## 新浪接口:

```javascript

<script type="text/javascript" src="http://int.dpool.sina.com.cn/iplookup/iplookup.php?format=js"></script>
<script type="text/javascript">
	alert(remote_ip_info);
	// country 国家
	// province 省份
	// city 地区
</script>


```

## 淘宝接口

```javascript


<script type="text/javascript">
	var ip = '59.41.160.154';
	$.ajax({
		url: 'http://ip.taobao.com/service/getIpInfo.php?ip=' + ip,
		type: 'GET',
		success: function(msg){
			console.log(msg);
		}
	});
</script>


```

## 太平洋接口

[http://whois.pconline.com.cn/](http://whois.pconline.com.cn/)

这个提供了蛮多的接口，亲们可以打开页面自己亲自测试一下。

## 搜狐接口

[http://pv.sohu.com/cityjson](http://pv.sohu.com/cityjson) ---（默认GBK）

[http://pv.sohu.com/cityjson?ie=utf-8](http://pv.sohu.com/cityjson?ie=utf-8) ---（可设置编码utf8）

[http://txt.go.sohu.com/ip/soip](http://txt.go.sohu.com/ip/soip)

使用方式和上面的一样，经测试具体的地区不是很准确。

## 百度地图接口

[http://lbsyun.baidu.com/index.php?title=webapi/ip-api](http://lbsyun.baidu.com/index.php?title=webapi/ip-api)

[百度JavaScript API Demo](http://lbsyun.baidu.com/jsdemo.htm#a1_2)

使用前需要在百度的开发者平台申请 一个key来启用它的JS库

百度的用法已经写得很详细了，这里不再赘述。唯一的缺点就是，它接口的请求次数是有限制的，个人每日免费100000次，如果是企业每日3000000。请酌情使用

## 高德开放平台

[高德浏览器定位](http://lbs.amap.com/api/javascript-api/example/location/browser-location)

[高德ip定位](http://lbs.amap.com/api/javascript-api/example/location/get-city-name-by-ip-location)

和百度一样，要是用也要申请一个唯一的key值

以上接口都是通过ip地址来判断地理位置的，那要怎么获取ip地址呢？

## 获取ip地址

```javascript


<script>
var url = 'http://chaxun.1616.net/s.php?type=ip&output=json&callback=?&_=' + Math.random();

$.getJSON(url, function(data) {
    alert(data.Ip);
});
</script>

```

获取地理位置方法五花八门，还有h5提供了一个原生的方法来获取地理位置，但需要用户允许获取地理位置才行。

具体请参考：[geolocation 对象 MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Geolocation/Using_geolocation)

以上就是针对最近项目的需求收集的一些获取地理位置的方法。如果你有更好的方法，欢迎在[issues](https://github.com/smileyby/getAddress/issues)中留言。

