# 快速开始

本文档是基于百度地图 3.0 来设计和实现的

## 1.注册 APPKey

去官方网站的后台注册 APPkey

获取到 key 值后 引用即可

## 2.最基础的 DEMO

```html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>Hello, World</title>
    <style type="text/css">
      html {
        height: 100%;
      }
      body {
        height: 100%;
        margin: 0px;
        padding: 0px;
      }
      #container {
        height: 100%;
      }
    </style>
    <script
      type="text/javascript"
      src="https://api.map.baidu.com/api?v=3.0&ak=您的APPkey"
    >
      //v3.0版本的引用方式：src="https://api.map.baidu.com/api?v=3.0&ak=您的密钥"
    </script>
  </head>

  <body>
    <div id="container"></div>
    <script type="text/javascript">
      var map = new BMap.Map('container');
      // 创建地图实例
      var point = new BMap.Point(116.404, 39.915);
      // 创建点坐标
      map.centerAndZoom(point, 18);
      // 初始化地图，设置中心点坐标和地图级别
      map.enableScrollWheelZoom(true);
    </script>
  </body>
</html>
```

## 3.看完文档后(很重要)

看完文档后要是没找到对应的例子 请看百度地图的开源库和官方 DEMO
