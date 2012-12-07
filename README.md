DesignerCharting
=================

## About ##
DesignerCharting is a collection of charting objects for Adobe LiveCycle Designer. 
The main purpose is to provide business charting capabilities to Adobe LiveCycle Output
and Adobe LiveCycle Forms as well as Adobe Acrobat and Adobe Reader.

DesignerCharting can also be used with SAP's Adobe Document Services (ADS), which is where
the project started. It is used to provide charting capabilities for utilities customers
as part of their statement presentment process. Configured correctly it's possible to 
produce several hundred charts per minute.

We are currently in the process of providing documentation and samples for the component.

The code will be provided at a later stage.

## Supported Chart Types ##
DesignerCharting currently supports column, stacked column, bar and stacked bar chart
types. Additional chart types are under development.

## Basic usage ##
DesignerCharting is driven by binding or supplying (XML) data with two main child nodes
nodes. The name of the root node for the chart can be freely chosen.
```xml
...
 <chart>
     <options>
        ....
     </options>
     <dataSeries>
       ...
     </dataSeries>
 </chart>
...    
```

The generation of the chart is done by calling the initialization and rendering within
the LiveCycle Designer events e.g. the initialize event of the DesignerCharting object

```js
	DesignerCharting.init(this);
	DesignerCharting.ColumnChart.render();
```

The above code renders a ColumnChart where the data node for the chart must be bound to
the DesignerChart object. If this is not the case the reference to the data node can be
passed in the init call. The example below passes a reference to a node called 
$data.chartData.

```js
	DesignerCharting.init(this, $data.chartData);
```

  