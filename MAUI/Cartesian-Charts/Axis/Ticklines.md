---
layout: post
title: Axis Tick Line in .NET MAUI Chart control | Syncfusion
description: Learn here all about chart axis tick line and its customization in Syncfusion .NET MAUI Chart (SfCartesianChart) control.
platform: maui
control: SfCartesianChart
documentation: ug
---

# Tick Lines in .NET MAUI Chart

Tick lines are the small lines which is drawn on the axis line representing the axis labels. Tick lines will be drawn outside of the axis by default. 

And also minor tick lines can be added to the axis by defining the [MinorTicksPerInterval](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.RangeAxisBase.html#Syncfusion_Maui_Charts_RangeAxisBase_MinorTicksPerInterval) property. This property will add the minor tick lines to every interval based on value.

N> For category axis, minor tick lines are not applicable. Since it is rendered based on index positions.

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart>
. . .
<chart:SfCartesianChart.PrimaryAxis>
    <chart:NumericalAxis MinorTicksPerInterval="4"/>
</chart:SfCartesianChart.PrimaryAxis>

<chart:SfCartesianChart.SecondaryAxis>
    <chart:NumericalAxis />
</chart:SfCartesianChart.SecondaryAxis>

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . .
chart.PrimaryAxis = new NumericalAxis()
{
    MinorTicksPerInterval = 4 
};

chart.SecondaryAxis = new NumericalAxis();

{% endhighlight %}

{% endtabs %}

## Customization

Both major and minor tick lines can be customized by using the [MajorTickStyle](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxis.html#Syncfusion_Maui_Charts_ChartAxis_MajorTickStyle) and [MinorTickStyle](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.RangeAxisBase.html#Syncfusion_Maui_Charts_RangeAxisBase_MinorTickStyle) properties respectively. They provide options to change the [StrokeWidth](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxisTickStyle.html#Syncfusion_Maui_Charts_ChartAxisTickStyle_StrokeWidth), [TickSize](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxisTickStyle.html#Syncfusion_Maui_Charts_ChartAxisTickStyle_TickSize), [Stroke](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Charts.ChartAxisTickStyle.html#Syncfusion_Maui_Charts_ChartAxisTickStyle_Stroke) of tick lines. By default minor tick lines will not be visible.

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart>
. . .
<chart:SfCartesianChart.PrimaryAxis>
    <chart:NumericalAxis MinorTicksPerInterval="4">
        <chart:NumericalAxis.MajorTickStyle>
            <chart:ChartAxisTickStyle Stroke="Red" StrokeWidth="1" TickSize="10"/>
        </chart:NumericalAxis.MajorTickStyle>
        
        <chart:NumericalAxis.MinorTickStyle>
            <chart:ChartAxisTickStyle Stroke="Red" StrokeWidth="1"/>
        </chart:NumericalAxis.MinorTickStyle>
    </chart:NumericalAxis>
</chart:SfCartesianChart.PrimaryAxis>

<chart:SfCartesianChart.SecondaryAxis>
    <chart:NumericalAxis />
</chart:SfCartesianChart.SecondaryAxis>

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . .
NumericalAxis numerical = new NumericalAxis();
numerical.MajorTickStyle.StrokeWidth = 1;
numerical.MajorTickStyle.Stroke = Colors.Red;
numerical.MinorTicksPerInterval = 4;
numerical.MinorTickStyle.StrokeWidth = 1;
numerical.MinorTickStyle.Stroke = Colors.Red;
chart.PrimaryAxis = numerical;

chart.SecondaryAxis = new NumericalAxis();

{% endhighlight %}

{% endtabs %}

![Axis tick lines customization support in MAUI Chart](Axis_images/maui_chart_axis_tickline_customization.jpg)