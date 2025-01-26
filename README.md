# 2D-basicImplement

## Edit Map

```
建立map:
New map...
地圖方向: orthogonal
圖層格式: CSV
圖塊繪製順序: 右下
Save As json file

導入tile:
New Tileset
基於圖塊集圖像
No Embed in map

來源: 選擇tile圖片
Save As json file

在Layers區域 每個圖層以Group包起來
新增一般tile及碰撞tile: 選Tile Layer 並命名為 tilelayer
新增不規則碰撞物件: Object Layer 並命名為objectlayer

Group 2
-objectlayer
-collision
-tilelayer

Group 1
-objectlayer
-collision
-tilelayer

```