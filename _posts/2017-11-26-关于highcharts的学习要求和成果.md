---
layout: post
category: "python"
title:  "关于highcharts的学习要求和学习成果"
tags: [web,可视化]
---
highcharts是一个优秀的js插件，用于网页图表的可视化展现。
<!-- more -->
highcharts的学习初衷是希望补充在BI项目售前工作中数据可视化的知识储备，了解可视化的需求，实现思路，形成一套规范的解决方案。

##### 图表构成
一般情况下，Highcharts 包含标题（Title）、坐标轴（Axis）、数据列（Series）、数据提示框（Tooltip）、图例（Legend）、版权标签（Credits）等，另外还可以包括导出功能按钮（Exporting）、标示线（PlotLines）、标示区域（PlotBands）、数据标签（dataLabels）等。  
Highcharts 基本组成部分如下图所示：
![基本组成部分](/img/post_img/hdcbfq.png)

1. 标题（Title） 
图表标题，包含标题和副标题（subTitle），其中副标题是非必须的。  
2. 坐标轴（Axis）
坐标轴包含x轴（xAxis）和y轴（yAxis）。通常情况下，x轴显示在图表的底部，y轴显示在图表的左侧。多个数据列可以共同使用同一个坐标轴，为了对比或区分数据，Highcharts提供了多轴的支持。
3. 数据列（Series）  
数据列即图表上一个或多个数据系列，比如曲线图中的一条曲线，柱状图中的一个柱形。
4. 数据提示框（Tooltip）  
当鼠标悬停在某点上时，以框的形式提示该点的数据，比如该点的值、数据单位等。数据提示框内提示的信息完全可以通过格式化函数动态指定。
5. 图例（Legend）  
图例是图表中用不同形状、颜色、文字等 标示不同数据列，通过点击标示可以显示或隐藏该数据列。
6. 版权标签（Credits）    
显示在图表右下方的包含链接的文字，默认是Highcharts官网地址。通过指定credits.enabled=false即可不显示该信息。
7. 导出功能（Exporting）
通过引入 exporting.js即可增加图表导出为常见文件功能。
8. 标示线（PlotLines）
可以在图表上增加一条标示线，比如平均值线，最高值线等。
9. 标示区（PlotBands） 
可以在图表添加不同颜色的区域带，标示出明显的范围区域。



# Highcharts 配置选项详细说明

Highcharts 提供大量的配置选项参数，您可以轻松定制符合用户要求的图表，本章节为大家详细介绍Highcharts 配置选项使用说明：

* * *

## 参数配置(属性+事件)

1.  chart.events.addSeries：添加数列到图表中。

2.  chart.events.click：整个图表的绘图区上所发生的点击事件。

3.  chart.events.load：图表加载事件。

4.  chart.events.redraw：图表重画事件，当点击图注显示和隐藏绘图时可以触发。

5.  chart.events.selection：当图表曲线可选择放大时，当选择图表操作时，可以触发该事件。

6.  chart.height：所绘制图表的高度值。

7.  chart.inverted：图表中的x，y轴对换。

8.  chart.polar：是否为极性图表。

9.  chart.reflow：当窗口大小改变时，图表宽度自适应窗口大小改变。

10.  chart.renderTo：图表加载的位置，是页面上的一个DOM对象。

11.  chart.showAxes：在空白图表中，是否显示坐标轴。

12.  chart.type：图表的类型，默认为line，还有bar/column/pie……

13.  chart.width：图表绘图区的宽度，默认为自适应。

14.  chart.zoomType：图表中数据报表的放大类型，可以以X轴放大，或是以Y轴放大，还可以以XY轴同时放大。

15.  colors：图表中多数列时，各数列之间的颜色。是一个数组，一般不动。

16.  credits.enabled：是否允许显示版权信息。

17.  credits.href：版权所有的链接。

18.  credits.text：版权信息显示文字。

19.  exporting.buttons.exportButton.enabled：是否允许显示导出按钮。

20.  exporting.buttons.exportButton.menuItems：导出按钮的菜单选项。

21.  exporting.buttons.exportButton.onclick：导出按钮被点击的事件，不是内部的菜单。

22.  exporting.buttons.printButton.enabled：是否允许打印按钮。

23.  exporting.buttons.printButton.onclick：打印按钮的点击事件。

24.  exporting.enabled：打印和导出按钮是否被允许。

25.  exporting.filename：被导出文件的文件名。

26.  exporting.type：默认导出图片的文件格式。

27.  exporting.url：SVG图表转换并导出的接口处理地址。

28.  exporing.width：默认导出图片的宽度。

29.  labels：标签，可以加载到图表的任何位置，里面有items，style。

30.  lang：语言参数配置，与导出按钮菜单有关的配置，时间名称的配置等。

31.  legend.enabled：是否允许图注。

32.  navigation.buttonOptions.enabled：图表中所有导航中的按钮是否可被点击。

33.  plotOptions.area.allowPointSelect：是否允许数据点的点击。

34.  plotOptions.area.color：绘图的颜色。

35.  plotOptions.area.dataLabels.enabled：是否允许数据标签。

36.  plotOptions.area.enableMouseTracking：是否允许数据图表中，数据点的鼠标跟踪气泡显示。

37.  plotOptions.area.events.checkboxClick：数据图表中图注中复选框的点击事件。

38.  plotOptions.area.events.click：数据图表中，数据点的点击事件。

39.  plotOptions.area.events.hide：数据图表中，某一数据序列隐藏时的事件。

40.  plotOptions.area.events.show：数据图表中，某一数据序列显示时的事件。

41.  plotOptions.area.events.legendItemClick：数据图表中，图注中的项目被点击时的事件，直接赋值false，则不可点击。

42.  plotOptions.area.events.mouseOut：数据点的鼠标移出事件。

43.  plotOptions.area.events.mouseOver：数据点的鼠标经过事件。

44.  plotOptions.area.marker.enabled：图表中绘图中是否显示点的标记符。

45.  plotOptions.area.marker.states.hover.enabled：是否允许标记符的鼠标经过状态。

46.  plotOptions.area.marker.states.select.enabled：是否允许标记符的选择状态。

47.  plotOptions.area.point.events.click：图表中每一个单独的点点击事件。

48.  plotOptions.area.point.events.mouseOut

49.  plotOptions.area.point.events..mouseOver

50.  plotOptions.area.point.events.remove：删除图表中的点时的事件。

51.  plotOptions.area.point.events.select：图表中点选择事件。

52.  plotOptions.area.point.events.unselect：图表中点取消选择时的事件。

53.  plotOptions.area.point.events.update：图表中数据发生更新时的事件。

54.  plotOptions.area.visible：加载时，数据序列默认是显示还是隐藏。

55.  plotOptions.area.zIndex：在多序列的情况下，调整每一个序列的层叠顺序。

56.  以上的point.events同样还适用于其他面积类图表（arearange、areaspline、areasplinerange），其他的柱状图（bar、column）及所有图表。

57.  plotOptions.area.showInLegend：是否在图注中显示。

58.  plotOptions.area.stacking：是以值堆叠，还是以百分比堆叠。

59.  plotOptions.area.states.hover.enabled：鼠标放上的状态是否允许。

60.  plotOptions.area.stickyTracking：鼠标粘性跟踪数据点。

61.  plotOptions.arearange，plotOptions.areaspline，plotOptions.areasplinerange类同于plotOptions.area

62.  plotOptions.bar.groupPadding：对于柱状图分组，每个分组之间的间隔。

63.  plotOptions.bar.grouping：是否对数据进行分组。

64.  plotOptions.bar.minPointLength:：定义当point值为零时，点的最小长度为多少

65.  plotOptions.bar.showInLegend：是否在图注中显示。

66.  plotOptions.bar.stacking：是以值堆叠，还是以百分比堆叠（normal/percent）。

67.  plotOptions.column，plotOptions.columnrange类同于plotOptions.bar

68.  plotOptions.line的相关配置类似于plotOptions.area配置。

69.  plotOptions.pie.ignoreHiddenPoint：在饼状图中，某一个序列经图注点击隐藏后，整个饼状图是重新以100%分配，还是只在原图基础上隐藏，呈现一个缺口。

70.  plotOptions.pie.innerSize：绘制饼状图时，饼状图的圆心预留多大的空白。

71.  plotOptions.pie.slicedOffset：与allowPointSelect结合使用，当点被点击时，对应的扇区剥离，这个参数即配置离开的距离。

72.  plotOptions.pie的其他常用配置参数类同于plotOptions.area,plotOptions.scatter，plotOptions.series，plotOptions.spline的相关配置类似于plotOptions.area配置。

73.  series：是一个数组。

74.  series.data.color：某一个数据的颜色。

75.  series.data.dataLabels：序列中某一个数据的数据标签。

76.  series.data.events类同于plotOptions.area.point.events的相关配置。

77.  series.data.marker类同于plotOptions.area.marker的相关配置。

78.  series.data.name：配置数据点的名称。

79.  series.data.sliced：配置在饼图中，扇区的分离距离大小。

80.  series.data.x：点的x值。

81.  series.data.y：点的y值。

82.  series.name：数据序列的名称。

83.  series.stack：堆叠的分组索引。

84.  series.type：数据序列的展示类型。

85.  series.xAxis，series.yAxis：当使用多坐标轴时，指定某个数列对应哪个坐标轴。

86.  subtitle：配置图表的子标题。

87.  title：配置图表的标题。

88.  tooltip：配置图表中数据的气泡提示。

89.  tooltip.valueDecimals：允许的小数点位数。

90.  tooltip.percentageDecimals：允许百分比的小数点后位数。

91.  xAxis，yAxis配置设置坐标轴

92.  allowDecimals：坐标轴上是否允许小数。

93.  categories：是一个数组，坐标轴的分类。

94.  plotLines：绘制主线。

95.  tickColor：刻度颜色。

96.  tickInterval：刻度的步进值。

97.  labels.rotation：刻度标签旋转度数

## Chart：图表区选项

Chart图表区选项用于设置图表区相关属性。

|	参数	|	描述	|	默认值
|	---------	|	:---------:	|	:---------: |
|	backgroundColor	|	设置图表区背景色	|	#FFFFFF
|	borderWidth	|	设置图表边框宽度	|	0
|	borderRadius	|	设置图表边框圆角角度	|	5
|	renderTo	|	图表放置的容器，一般在html中放置一个DIV，获取DIV的id属性值	|	null
|	defaultSeriesType	|	默认图表类型line, spline, area, areaspline, column, bar, pie , scatter	|	0
|	width	|	图表宽度，默认根据图表容器自适应宽度	|	null
|	height	|	图表高度，默认根据图表容器自适应高度	|	null
|	margin	|	设置图表与其他元素之间的间距，数组，如[0,0,0,0]	|	[null]
|	plotBackgroundColor	|	主图表区背景色，即X轴与Y轴围成的区域的背景色	|	null
|	plotBorderColor	|	主图表区边框的颜色，即X轴与Y轴围成的区域的边框颜色	|	null
|	plotBorderWidth	|	主图表区边框的宽度	|	0
|	shadow	|	是否设置阴影，需要设置背景色backgroundColor。	|	FALSE
|	reflow	|	是否自使用图表区域高度和宽度，如果没有设置width和height时，会自适应大小。	|	TRUE
|	zoomType	|	拖动鼠标进行缩放，沿x轴或y轴进行缩放，可以设置为：'x','y','xy'	|	''
|	events	|	事件回调，支持addSeries方法，click方法，load方法，selection方法等的回调函数。	|	

