# 2D-basicImplement

## Map Edit

Create map file:

1. open tiled-windows
2. New map (地圖方向: orthogonal,圖層格式: CSV,圖塊繪製順序: 右下)
3. Save as json file

Create tileset:

1. New Tileset(基於圖塊集圖像,No Embed in map)
2. 來源: 選擇tile圖片
3. Save As json file

Edit map:

在Layers區域，每個圖層以Group包起來，zindex=Group層數*10 (start from 0)

玩家預設zindex為15，會往下找最近的圖層做碰撞，所以預設就是兩層Group，Group1為地面、Group2為玩家層數及預設的地圖碰撞層

使用以下結構編輯:
```
Group 2 (zindex=10)
-objectlayer
-collision
-tilelayer

Group 1 (zindex=0)
-objectlayer
-collision
-tilelayer
```

Use mapFile:

編輯Setting.js，將地圖的圖片+檔案放置在同個資料夾中，其中key為檔名,value為檔案路徑

```js

var assetSource = {
    imgs: {
        'defaultMap_tilecolor':'../asset/map/defaultMap/defaultMap_tilecolor.png'
    },
    sounds: {

    },
    jsons: {
        'defaultMap':'../asset/map/defaultMap/defaultMap.json',
        'defaultMap_tilecolor':'../asset/map/defaultMap/defaultMap_tilecolor.json'
    }
};

var map = new TileMap2(world, asset.jsons['defaultMap']);
```
![Alt text](image/mapEdit1.jpg)
