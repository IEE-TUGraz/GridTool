# GridTool

GridTool is an easy-to-use tool to convert and simplify electricity grid data from [OpenStreetMap](https://www.openstreetmap.org/) for the use in energy simulation models (ESMs). Instead of relying on relations between lines and power stations (that are often missing) in the OpenStreetMap-data, the tool uses a heuristic approach to identify grid nodes and simplifies the data.

The GridTool shortens the lengthy process of converting and simplyfying electricity grid data from transmission and distribution system operators (TSOs and DSOs) for the use in ESMs to mere seconds.

The tool is programmed in MATLAB and the main advantages are its flexibility and easy customizability. The final results are two Excel files. One contains the nodes (power stations) and the second one contains the lines.

You can use this code freely according to the LICENSE file (https://opensource.org/licenses/MIT), but please cite our (preprint) paper [[1]](https://doi.org/10.36227/techrxiv.20551569) if you do.

## Software Architecture
GridTool is split into 6 modules that itself are divided into 24 functions to ensure clarity, maintainability and easy expandability. The flowchart in Figure 1 shows the 6 modules and 24 functions. A detailed description of the functionality of these functions can be found in [[1]](https://doi.org/10.36227/techrxiv.20551569) as well as in the comments of the MATLAB code itself.

<p align="center">
  <img src="Figures/GridTool_FlowChart_Detailed.png" alt="Flowchart_GridTool" width="80%" /></br>
  <b>Figure 1.</b> Flowchart showing the 6 modules and 24 funcitons of the GridTool.
</p>

## System Requirements
* PC with MATLAB version R2021a installed and a valid licence (GridTool is programmed in a way that it should be compatible with older and newer versions, but it is not tested with other MATLAB versions.)

## Manual
This provides a step-by-step instruction on how to run the GridTool. The steps are also visualized in the Figure 2.
1) Download the GridTool.m file on a PC that meets the system requirements.
2) Download the electricity grid data from OpenStreetMap using the [OverpassTurbo](https://overpass-turbo.eu/) website. An example of a query to download Austria's electricity grid lines between 220 kV and 380 kV can be found in the file *OverpassTurbo_Example_Query.txt*. Run the query in OverpassTurbo and export  the result as "Raw OSM data", which downloads the data in the json file format. For testing purposes you can also use the *2022-08-02_Austria_220kV_and_380kV.json* file provided in the repository.
3) Open the GridTool.m file in Matlab.
4) Adjust the settings in the *Initialization and Settings* section of the code.
5) Run the code by clicking the "Run"-button or pressing "F5".
4) A file window opens to select the previously downloaded json file.
5) After a few seconds, a new window pops up to select the desired voltage levels. Multiple voltage levels can be selected by holding the "Alt" key.
6) The GridTool is completed, when it displays "CONVERSION COMPLETED" in the MATLAB console. The final files can be found in the folder where the GridTool.m file is saved.

<p align="center">
  <img src="Figures/GridTool_Illustrative_Example.png" alt="GridTool_Illustrative_Example]" width="80%" /></br>
  <b>Figure 2.</b> Step-by-step guide for how to use the GridTool.
</p>

## Illustrative Example: Austrian Transmission Grid
In the figure below is a comparison between the official grid map from the Austrian transmission system operator APG (downloaded: August 3rd, 2022) and the result of the GridTool (data downloaded from OpenStreetMap: August 2nd, 2022). To run this illustrative example, you can use the *2022-08-02_Austria_220kV_and_380kV.json* file found in this repository with the GridTool. Figure 3 compares the official grid map from Austrias transmission system operator [APG](https://www.apg.at/stromnetz/stromnetz-oesterreich/) with the results of the GridTool.

<p align="center">
  <img src="Figures/APG_Netzkarte.png" alt="APG_Netzkarte]" width="40%" />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="Figures/Final_Results_Map.png" alt="GridTool_Final_Results_Map]" width="40%" /></br>
  <b>Figure 3.</b> Official grid map from the Austrian transmission operator APG (l.s) and final results from the GridTool displayed on a map (r.s).
</p>

## Use Cases
The GridTool has been already used for research in different papers and projects. Some examples are listed below.

### Project START2030
The publicly funded project [START2030](https://start2030.wifo.ac.at/) aims at providing comprehensive analyses of the economic incidence and social impacts of a transition to a 100% renewable electricity system by 2030 as determined by Austria's Renewable-Energy-Act (EAG). For this the techno-economic simulation model ATLANTIS [[2]](https://doi.org/10.1007/s10100-015-0413-8) and the macroeconomic model DYNK [[3]](https://doi.org/10.1016/j.enpol.2018.11.030) are linked. For this project Austria's electricity grid in ATLANTIS was expanded to include the 110 kV network. As there is no public information about the distribution grid available from the Austrian DSOs, the GridTool was utilized to use the data from OpenStreetMap.

### Publication Modelling Africa's Power System
In order to build a digital twin of Africa's power system, the GridTool has been used to get electricity grid data. The data was then implemented into the Low-Carbon Expansion and Generaton (LEGO) model to perform techno-economic simulations. A research using this digital twin about transforming Africa's power system to 100% renewables can be found here [[4]](https://www.energy-proceedings.org/wp-content/uploads/2022/08/MITAB_2022_paper_2510.pdf).

## References
[1] R. Gaugl, S. Wogrin, U. Bachhiesl, L. Frauenlob, (2022). *"GridTool: An Open-Source Tool to Convert Grid Data,"* Preprint [https://doi.org/10.36227/techrxiv.20551569](https://doi.org/10.36227/techrxiv.20551569)

[2] H. Stigler, U. Bachhiesl, G. Nischler, G. Feichtinger, (2016). *"ATLANTIS: techno-economic model of the European electricity sector,"* Central European Journal of Operations Research, <i>24</i>(4), 965–988. [https://doi.org/10.1007/s10100-015-0413-8](https://doi.org/10.1007/s10100-015-0413-8)

[3] M. Kirchner, M. Sommer, K. Kratena, D. Kletzan-Slamanig, C. Kettner-Marx, (2019). *"CO2 taxes, equity and the double dividend – Macroeconomic model simulations for Austria,"* Energy Policy, Volume 126, Pages 295-314, ISSN 0301-4215, [https://doi.org/10.1016/j.enpol.2018.11.030](https://doi.org/10.1016/j.enpol.2018.11.030).

[4] R. Gaugl, S. Wogrin, and U. Bachhiesl (2022). *"Transition of the African Power System to Renewable Energies-A Case Study,"* Energy Proceedings MIT A+B Applied Energy Symposium, Volume 25, ISSN 2004-2965, [https://www.energy-proceedings.org/transition-of-the-african-power-system-to-renewable-energies-a-case-study/](https://www.energy-proceedings.org/transition-of-the-african-power-system-to-renewable-energies-a-case-study/)
