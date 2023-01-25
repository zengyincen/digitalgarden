---
{"dg-publish":true,"dg-home":true,"banner":"https://api.dujin.org/bing/1920.php","banner_y":0.624,"banner_lock":true,"banner_icon":"🏡","obsidianUIMode":"preview","permalink":"/1-boxes/home/home/","tags":["gardenEntry"],"dgPassFrontmatter":true}
---

# Home
#### 站内导航  | [[9 - Tools/index/index-A\|闪念笔记]] | [[1 - Boxes/Work/任务看板\|任务看板]]  |  [[9 - Tools/index/关键词漫游\|找灵感]]  | [[9 - Tools/index/index-H\|帮助]] | [[1 - Boxes/Home/我的书架\|书架]] | [[1 - Boxes/Home/我的影音\|影音]]
#### 在线工具  | [必应搜索](https://cn.bing.com) | [WikiHow](https://zh.wikihow.com/) | [时空地图](https://www.allhistory.com/map) | [全景地图](https://map.baidu.com/@12958167.77,4825775.8,21z,87t,92.92h#panoid=09002200122003121004462317C&panotype=street&heading=9.24&pitch=7.39&l=21&tn=B_NORMAL_MAP&sc=0&newmap=1&shareurl=1&pid=09002200122003121004462317C) | [微信读书](https://weread.qq.com) | [[9 - Tools/iframe/喜马拉雅\|喜马拉雅]] | [[9 - Tools/iframe/每日一文\|每日一文]] | [[9 - Tools/iframe/审美\|审美]] |[颜色选择器](https://photokit.com/colors/color-picker/?lang=zh)|[[9 - Tools/iframe/下载电子书\|下载电子书]]|
````ad-info
title:常规操作
collapse: open
 `button-style` `button-refreshhomepage`  `button-doubanbook` `button-doubanmovie`  
 
````
````ad-info
title:常用网站
collapse: open
color:51,112,255
`button-feishu`   `button-vika` `button-plugin` `button-cubox` `button-emoji`
````


## 最近阅读
| 封面                                                                     | 名字                                   | 作者       |
| ---------------------------------------------------------------------- | ------------------------------------ | -------- |
| ![\|60](https://img1.doubanio.com/view/subject/l/public/s2768378.jpg)  | [[2 - Booknote/三体\|三体]]           | 刘慈欣      |
| ![\|60](https://img1.doubanio.com/view/subject/l/public/s33758847.jpg) | [[2 - Booknote/瓦尔登湖\|瓦尔登湖]]       | 亨利·戴维·梭罗 |
| ![\|60](https://img9.doubanio.com/view/subject/l/public/s29799055.jpg) | [[2 - Booknote/云边有个小卖部\|云边有个小卖部]] | 张嘉佳      |
| ![\|60](https://img1.doubanio.com/view/subject/l/public/s1727290.jpg)  | [[2 - Booknote/追风筝的人\|追风筝的人]]     | 卡勒德·胡赛尼  |
| ![\|60](https://img9.doubanio.com/view/subject/l/public/s29412594.jpg) | [[2 - Booknote/西西弗斯神话\|西西弗斯神话]]   | Albert   |


---
# 图表看板
## 笔记排行榜
```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Bar

#-----------------#
#- chart data    -#
#-----------------#
data: | 
  dataviewjs:
  return dv.pages()
           .groupBy(p => p.file.folder)
           .sort(p => p.rows.length)
           .map(p => ({folder: p.key || "ROOT", count: p.rows.length}) )
           .array()
           .reverse();

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "count"
  yField: "folder"
  padding: auto
  height: 400
  color: "#ff2d51"
  
  meta:
    count:
      alias: "数量"

```

---
## 标签云

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: WordCloud

#-----------------#
#- chart data    -#
#-----------------#
data: | 
  dataviewjs: 
  return (() => {
    const tags = this.app.metadataCache.getTags();
   
    let dataArray = [];
    Object.keys(tags).forEach(key => dataArray.push ({tag: key.replace("#",""),count: tags[key]}));
    return dataArray;
   })();


#-----------------#
#- chart options -#
#-----------------#
options:
  wordField: "tag"
  weightField: "count"
  colorField: "tag"
style:
  backgroundColor: "translucent"

#-----------------------------------------------#
#--- 可选择多彩颜色(colorField) 或单色 (color) ---#
#---  colorField: "tag" ---#
#---  color: "#bb5548" ---#
#-----------------------------------------------#

  wordStyle:
    rotation: 0
```
```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Radar

#-----------------#
#- chart data    -#
#-----------------#
data:
  - item: "马列主义"
    user: "a"
    score: 2
  - item: "哲学"
    user: "a"
    score: 65
  - item: "社会科学总论"
    user: "a"
    score: 10
  - item: "政治、法律"
    user: "a"
    score: 4
  - item: "军事"
    user: "a"
    score: 2
  - item: "经济"
    user: "a"
    score: 10
  - item: "文化教育"
    user: "a"
    score: 28
  - item: "语言文字"
    user: "a"
    score: 14
  - item: "文学"
    user: "a"
    score: 20
  - item: "艺术"
    user: "a"
    score: 0	
  - item: "历史地理"
    user: "a"
    score: 9
  - item: "自然科学总论"
    user: "a"
    score: 1
  - item: "数理化"
    user: "a"
    score: 0
  - item: "天文地球"
    user: "a"
    score: 3
  - item: "生物"
    user: "a"
    score: 3
  - item: "医药卫生"
    user: "a"
    score: 3
  - item: "农业"
    user: "a"
    score: 4
  - item: "工业"
    user: "a"
    score: 11
  - item: "交通"
    user: "a"
    score: 1
  - item: "航空航天"
    user: "a"
    score: 1
  - item: "环境安全"
    user: "a"
    score: 0
  - item: "综合"
    user: "a"
    score: 1

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "item"
  yField: "score"
  seriesField: ""
  color: "#ff461f"
  meta:
    score:
      alias: "Score"
      min: 0
      nice: true
  xAxis:
    line: null
    tickLine: null
  yAxis:
    label: false
    grid:
      alternateColor: "rgba(0, 0, 0, 0.04)"
  point: {}
  area: {}
```
---
## 柱状图

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Column

#-----------------#
#- chart data    -#
#-----------------#
data: |
  dataviewjs:
  return dv.pages()
           .groupBy(p => p.file.folder)
           .map(p => ({folder: p.key || "根目录", count: p.rows.length}))
           .array();

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "folder"
  yField: "count"
  padding: auto
  color: "#801dae"
  columnStyle:
    fillOpacity: 1
    lineWidth: 0.9
    strokeOpacity: 1.7
    shadowColor: "grey"
    shadowBlur: 5
    shadowOffsetX: 5
    shadowOffsetY: 5

  meta:
    count:
      alias: "文件数量" 
```
---



<div style="background-color:#d4a1a1;text-align:center;">我是有底线的</div>
