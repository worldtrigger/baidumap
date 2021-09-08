# 模式切换

### 驾车路线

```html

<!DOCTYPE html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
<title>驾车路线规划</title>
<script type="text/javascript" src="//api.map.baidu.com/api?v=3.0&ak=您的密钥"></script>
<style type="text/css">
body, html,#container {width: 100%;height: 100%;overflow: hidden;margin:0;font-family:"微软雅黑";}
</style>
</head>
<body>
<div id="container"></div>
<script type="text/javascript">
var map = new BMap.Map("container");
map.centerAndZoom(new BMap.Point(116.404, 39.915), 14);
var driving = new BMap.DrivingRoute(map, {
    renderOptions: {
        map: map,
        autoViewport: true
    }
});
var start = new BMap.Point(116.310791, 40.003419);
var end = new BMap.Point(116.486419, 39.877282);
driving.search(start, end);
</script>
</body>
</html>

```

### 公交路线

```html

<!DOCTYPE html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
<title>公交路线规划</title>
<script type="text/javascript" src="//api.map.baidu.com/api?v=3.0&ak=您的密钥"></script>
<style type="text/css">
body, html,#container {width: 100%;height: 100%;overflow: hidden;margin:0;font-family:"微软雅黑";}
</style>
</head>
<body>
<div id="container"></div>
<script type="text/javascript">
var map = new BMap.Map("container");
map.centerAndZoom(new BMap.Point(116.404, 39.915), 14);
var transit = new BMap.TransitRoute(map, {
    renderOptions: {
        map: map,
        autoViewport: true

    },
    // 配置跨城公交的换成策略为优先出发早
    intercityPolicy: BMAP_INTERCITY_POLICY_EARLY_START,
    // 配置跨城公交的交通方式策略为飞机优先
    transitTypePolicy: BMAP_TRANSIT_TYPE_POLICY_AIRPLANE
});
var start = new BMap.Point(116.310791, 40.003419);
var end = new BMap.Point(121.490546, 31.233585);
transit.search(start, end);
</script>
</body>
</html>

```

### 步行路线

```html

<!DOCTYPE html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
<title>步行路线规划</title>
<script type="text/javascript" src="//api.map.baidu.com/api?v=3.0&ak=您的密钥"></script>
<style type="text/css">
body, html,#container {width: 100%;height: 100%;overflow: hidden;margin:0;font-family:"微软雅黑";}
</style>
</head>
<body>
<div id="container"></div>
<script type="text/javascript">
var map = new BMap.Map("container");
map.centerAndZoom(new BMap.Point(116.404, 39.915), 14);
var walking = new BMap.WalkingRoute(map, {
    renderOptions: {
        map: map,
        autoViewport: true
    }
});
var start = new BMap.Point(116.310791, 40.003419);
var end = new BMap.Point(116.326419, 40.003519);
walking.search(start, end);
</script>
</body>
</html>

```

### 骑行路线

```html

<!DOCTYPE html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
<title>骑行路线规划</title>
<script type="text/javascript" src="//api.map.baidu.com/api?v=3.0&ak=您的密钥"></script>
<style type="text/css">
body, html,#container {width: 100%;height: 100%;overflow: hidden;margin:0;font-family:"微软雅黑";}
</style>
</head>
<body>
<div id="container"></div>
<script type="text/javascript">
var map = new BMap.Map("container");
map.centerAndZoom(new BMap.Point(116.404, 39.915), 14);
var riding = new BMap.RidingRoute(map, {
    renderOptions: {
        map: map,
        autoViewport: true
    }
});
var start = new BMap.Point(116.310791, 40.003419);
var end = new BMap.Point(116.386419, 40.003519);
riding.search(start, end);
</script>
</body>
</html>

```
