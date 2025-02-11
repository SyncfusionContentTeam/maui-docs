---
layout: post
title: Axis labels in .NET MAUI Chart control | Syncfusion
description: Learn here all about axis labels and its customization in Syncfusion .NET MAUI Chart (SfCartesianChart) control.
platform: maui
control: SfCartesianChart
documentation: ug
---

# Axis labels in .NET MAUI Chart

Axis labels are used to show the units or measures or category value of axis to visualize the data user friendly. It will be generated based on the range and the values binded to [XBindingPath](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartSeries.html#Syncfusion_Maui_Charts_ChartSeries_XBindingPath) or [YBindingPath](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.XYDataSeries.html#Syncfusion_Maui_Charts_XYDataSeries_YBindingPath) properties of series.

## Label Rotation

The [LabelRotation](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxis.html#Syncfusion_Maui_Charts_ChartAxis_LabelRotation) property is used to define the angle for the label content.

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart>
    . . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:CategoryAxis LabelRotation="90"/>
    </chart:SfCartesianChart.PrimaryAxis>

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . .
chart.PrimaryAxis = new CategoryAxis()
{
    LabelRotation = 90
};

{% endhighlight %}

{% endtabs %}

## Label customization

The [LabelStyle](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxis.html#Syncfusion_Maui_Charts_ChartAxis_LabelStyle) property of axis provides options to customize the font-family, font-size, font-attributes and text color of axis labels. The axis labels can be customized using following properties:

* `Background` - Gets or sets the background color of the labels.
* `CornerRadius` - Gets or sets a value that defines the rounded corners for labels.
* `FontAttributes` - Gets or sets the font style for the label.
* `FontFamily` - Gets or sets the font family name for the label.
* `FontSize` - Gets or sets the font size for the label.
* `Margin` - Gets or sets the margin of the label to customize the appearance of label. 
* `Stroke` - Gets or sets the border stroke color of the labels.
* `StrokeWidth` - Gets or sets the border thickness of the label.
* `TextColor` - Gets or sets the color for the text of the label.
* `LabelFormat` - Gets or sets the label format. This property is used to set numeric or date-time format to the chart axis label.
* `LabelAlignment` - Gets or sets the axis label at start, end, and center positions.

## Edge Labels Drawing Mode

Chart axis provides support to customize the rendering position of the edge labels using the [EdgeLabelsDrawingMode](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxis.html#Syncfusion_Maui_Charts_ChartAxis_EdgeLabelsDrawingMode) property. [EdgeLabelsDrawingMode](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxis.html#Syncfusion_Maui_Charts_ChartAxis_EdgeLabelsDrawingMode) property default value is `Shift`.

| Action | Description |
|--|--|
| Center | Indicates that the edge label should appear at the center of its GridLines. |
| Fit | Indicates that the edge labels should be fit within the area of SfCartesianChart. |
| Hide | Indicates that the edge labels will be hidden |
| Shift | Indicates that edge labels should be shifted to either left or right so that it comes within the area of Chart. |

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart>
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:DateTimeAxis EdgeLabelsDrawingMode="Center"/>
    </chart:SfCartesianChart.PrimaryAxis>

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . . 
chart.PrimaryAxis = new DateTimeAxis()
{
    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Center
};

{% endhighlight %}

{% endtabs %}

![Axis edge label positioning support in MAUI Chart](Axis_images/maui_chart_axis_edge_labels_drawing.jpg)

## Edge Labels Visibility
 
The visibility of the edge labels of the axis can be controlled using the [EdgeLabelsVisibilityMode](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.RangeAxisBase.html#Syncfusion_Maui_Charts_RangeAxisBase_EdgeLabelsVisibilityMode) property. The default value of [EdgeLabelsVisibilityMode](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.RangeAxisBase.html#Syncfusion_Maui_Charts_RangeAxisBase_EdgeLabelsVisibilityMode) is `Default`, which displays the edge label based on auto interval calculations.

**Always Visible**

`AlwaysVisible` option in [EdgeLabelsVisibilityMode](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.RangeAxisBase.html#Syncfusion_Maui_Charts_RangeAxisBase_EdgeLabelsVisibilityMode) is used to view the edge labels even in chart area zoomed state.

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart>
    . . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:NumericalAxis EdgeLabelsVisibilityMode="AlwaysVisible"/>
    </chart:SfCartesianChart.PrimaryAxis>

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . .
chart.PrimaryAxis = new NumericalAxis()
{
    EdgeLabelsVisibilityMode = EdgeLabelsVisibilityMode.AlwaysVisible
};

{% endhighlight %}

{% endtabs %}

**Visible**

`Visible` option is used to display the edge labels irrespective of the auto interval calculation until zooming (i.e., in normal state).

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart>
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:NumericalAxis EdgeLabelsVisibilityMode="Visible"/>
    </chart:SfCartesianChart.PrimaryAxis>

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . .
chart.PrimaryAxis = new NumericalAxis()
{
    EdgeLabelsVisibilityMode = EdgeLabelsVisibilityMode.Visible
};

{% endhighlight %}

{% endtabs %}