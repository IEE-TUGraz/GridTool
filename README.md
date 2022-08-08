# GridTool
Open-source tool to convert OpenStreetMap electricity grid data for use in energy simulation models (ESMs).

GridTool is an easy-to-use tool to convert and simplify electricity grid data from OpenStreetMap (https://www.openstreetmap.org/) for the use in energy simulation models (ESMs). Instead of relying on relations between lines and power stations (that are often missing) in the OpenStreetMap-data, the tool uses a heuristic approach to identify grid nodes and simplifying the data.

The GridTool shortens the lengthy process of converting and simplyfying electricity grid data from transmission and distribution system operators (TSOs and DSOs) for the use in ESMs to mere seconds.

The tool is programmed in MATLAB and the main advantages are its flexibility and easy customizability.

## Software Architecture
GridTool is split into 6 modules that itself are divided into 24 functions to ensure clarity, maintainability and easy expandability. A flowchart showing the 6 modules and 24 functions can be seen below:

![GridTool_FlowChart](Figures/GridTool_FlowChart_Detailed.png)

## System Requirements
* PC with MATLAB version R2021a installed (GridTool is programmed in a way that it should be compatible with older and newer versions, but it is not tested with other MATLAB versions.)

## How to run the GridTool
1) Download the GridTool.m file on a PC that meets the system requirements
2) Download the electricity grid data from OpenStreetMap using the OverpassTurbo-website (https://overpass-turbo.eu/). An example of a query to download Austria's electricity grid lines between 220 kV and 380 kV can be found in the file **OverpassTurbo_Example_Query.txt**. Run the query in OverpassTurbo and export and download the result as "Raw OSM data".
