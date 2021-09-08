# 事件的处理

- 监听标注点可拖拽

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
      src="https://api.map.baidu.com/api?v=3.0&ak=您的密钥"
    >
      //v3.0版本的引用方式：src="https://api.map.baidu.com/api?v=3.0&ak=您的密钥"
    </script>
  </head>

  <body>
    <div id="container"></div>
    <script type="text/javascript">
      // 创建地图实例
      var map = new BMap.Map('container');
      // 创建点坐标
      map.centerAndZoom(point, 18);
      //添加点的坐标
      const pointsAll = [
        {
          x: 117.356921,
          y: 39.082631,
        },
        {
          x: 117.357337,
          y: 39.082279,
        },
      ];
      //把点加到地图上
      for (let i = 0; i < pointsAll.length; i++) {
        //创建标注图标
        var myIcon = new BMap.Icon(
          './images/worldmap.png',
          new BMap.Size(64, 64), //标记点图片的大小
          { anchor: new BMap.Size(10, 25) } //偏移的位置
        );
        var point = new BMap.Point(pointsAll[i].x, pointsAll[i].y);
        var marker = new BMap.Marker(point, { icon: myIcon }); // 创建标注
        //监听点击事件
        marker.enableDragging();
        marker.addEventListener('dragend', function (e) {
          window.alert('您点击了标注' + e.point.lng + ',' + e.point.lat);
        });
        map.centerAndZoom(point, 18); //设定缩放级别这句必须有
        map.addOverlay(marker); // 将标注添加到地图中
      }
    </script>
  </body>
</html>
```

![底图](../logo/tuozhuai.png)

- 监听标注点点击

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
      src="https://api.map.baidu.com/api?v=3.0&ak=您的密钥"
    >
      //v3.0版本的引用方式：src="https://api.map.baidu.com/api?v=3.0&ak=您的密钥"
    </script>
  </head>

  <body>
    <div id="container"></div>
    <script type="text/javascript">
      // 创建地图实例
      var map = new BMap.Map('container');
      // 创建点坐标
      map.centerAndZoom(point, 18);
      //添加点的坐标
      const pointsAll = [
        {
          x: 117.356921,
          y: 39.082631,
        },
        {
          x: 117.357337,
          y: 39.082279,
        },
      ];
      //把点加到地图上
      for (let i = 0; i < pointsAll.length; i++) {
        //创建标注图标
        var myIcon = new BMap.Icon(
          './images/worldmap.png',
          new BMap.Size(64, 64), //标记点图片的大小
          { anchor: new BMap.Size(10, 25) } //偏移的位置
        );
        var point = new BMap.Point(pointsAll[i].x, pointsAll[i].y);
        var marker = new BMap.Marker(point, { icon: myIcon }); // 创建标注
        //监听点击事件
        marker.addEventListener('click', function (e) {
          console.log(e); //获取到所有的数据
          window.alert('您点击了标注');
        });
        map.centerAndZoom(point, 18); //设定缩放级别这句必须有
        map.addOverlay(marker); // 将标注添加到地图中
      }
    </script>
  </body>
</html>
```

![底图](../logo/click.png)
