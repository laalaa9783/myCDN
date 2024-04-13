---
title: Markdown语法练习之标签外挂（Tag Plugins）
date: 2024-04-01 21:00:36
tags: [Markdown, 学习]
categories: Markdown
series: markdown练习
---
全文参考：https://butterfly.js.org/posts/4aa8abbe/#Tabs
## Note
```Markdown
{% note [color] [no-icon/icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```
color	【可选】顔色
(default / blue / pink / red / purple / orange / green)
icon	【可选】可配置自定义 icon (只支持 fontawesome 图标)
style	【可选】可以覆盖配置中的 style（simple/modern/flat/disabled）

{% note purple 'far fa-hand-scissors' simple %}
剪刀石头布
{% endnote %}
{% note blue 'far fa-hand-scissors' modern %}
剪刀石头布
{% endnote %}
{% note pink 'far fa-hand-scissors' flat %}
剪刀石头布
{% endnote %}
{% note red 'far fa-hand-scissors' disabled %}
剪刀石头布
{% endnote %}

使用mermaid标签可以绘制Flowchart（流程图）、Sequence diagram（时序图 ）、Class Diagram（类别图）、State Diagram（状态图）、Gantt（甘特图）和Pie Chart（圆形图），具体可以查看[mermaid文档](https://mermaid.js.org/#/)

## Tabs
```Markdown
{% tabs Unique name, [index] %}
<!-- tab [Tab caption] [@icon] -->
Any content (support inline tags too).
<!-- endtab -->
{% endtabs %}

Unique name   : Unique name of tabs block tag without comma.
                Will be used in #id's as prefix for each tab with their index numbers.
                If there are whitespaces in name, for generate #id all whitespaces will replaced by dashes.
                Only for current url of post/page must be unique!
[index]       : Index number of active tab.
                If not specified, first tab (1) will be selected.
                If index is -1, no tab will be selected. It's will be something like spoiler.
                Optional parameter.
[Tab caption] : Caption of current tab.
                If not caption specified, unique name with tab index suffix will be used as caption of tab.
                If not caption specified, but specified icon, caption will empty.
                Optional parameter.
[@icon]       : FontAwesome icon name (full-name, look like 'fas fa-font')
                Can be specified with or without space; e.g. 'Tab caption @icon' similar to 'Tab caption@icon'.
                Optional parameter.
```
{% tabs test4 %}
<!-- tab 第一個Tab -->
**tab名字為第一個Tab**
<!-- endtab -->
<!-- tab @fab fa-apple-pay -->
**只有圖標 沒有Tab名字**
<!-- endtab -->
<!-- tab 炸彈@fas fa-bomb -->
**名字+icon**
<!-- endtab -->
{% endtabs %}

## Button
```Markdown
{% btn [url],[text],[icon],[color] [style] [layout] [position] [size] %}

[url]         : 链接
[text]        : 按钮文字
[icon]        : [可选] 图标
[color]       : [可选] 按钮背景颜色(默认style时）
                       按钮字体和边框颜色(outline时)
                       default/blue/pink/red/purple/orange/green
[style]       : [可选] 按钮样式 默认实心
                       outline/留空
[layout]      : [可选] 按钮布局 默认为line
                       block/留空
[position]    : [可选] 按钮位置 前提是设置了layout为block 默认为左边
                       center/right/留空
[size]        : [可选] 按钮大小
                       larger/留空
```
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block center larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block right outline larger %}

{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,green larger %}

<div class="btn-center">
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline green larger %}
</div>

## Label
{% note red no-icon %}
由于hexo的渲染限制，在段落开头使用label标签外挂会出现一些问题。例如：连续开头使用label标签外挂的段落无法换行。建议不要在段落开头使用label标签外挂。
{% endnote %}
```Markdown
{% label text color %}
color:【可选】背景颜色，默认为default
       default/blue/pink/red/purple/orange/green
```
臣亮言：{% label 先帝 %}創業未半，而{% label 中道崩殂 blue %}。今天下三分，{% label 益州疲敝 pink %}，此誠{% label 危急存亡之秋 red %}也！然侍衞之臣，不懈於內；{% label 忠志之士 purple %}，忘身於外者，蓋追先帝之殊遇，欲報之於陛下也。誠宜開張聖聽，以光先帝遺德，恢弘志士之氣；不宜妄自菲薄，引喻失義，以塞忠諫之路也。
宮中、府中，俱為一體；陟罰臧否，不宜異同。若有{% label 作奸 orange %}、{% label 犯科 green %}，及為忠善者，宜付有司，論其刑賞，以昭陛下平明之治；不宜偏私，使內外異法也。

## Timeline
```Markdown
{% timeline title,color %}
<!-- timeline title -->
xxxxx
<!-- endtimeline -->
<!-- timeline title -->
xxxxx
<!-- endtimeline -->
{% endtimeline %}
color：default/blue/pink/red/orange/purple/green
```
{% timeline 2024,pink %}
<!-- timeline 04-07 -->
test
<!-- endtimeline -->
{% endtimeline %}

