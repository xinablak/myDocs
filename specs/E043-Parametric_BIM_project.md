# SPECIFICATION FOR BIM PROJECT
## Parametric Overpass Model Previewer


## BASIC DESCRIPTION

### PURPOSE

The main objective is to assemble a tool, in a broad sense, that parametrically creates a BIM model with a representation of a highway profile and a small bridge structure passing over it. Given the number of overpasses, their individual widths and the width of the highway profile at each location, several models can be created. 
Based on this information and other reference values for the elements comprising the overpass, a cost-estimation report will be produced for all the structures as well as some visualization media in the form of images with perspective views and sections of the model.
Finally, each of these models can be exported to an industry format, IFC, for further development.
For the purpose of assembling the BIM model, the procedures that will be used don't depend directly on the detail level of the model, only requiring that the basic geometry be defined to enable the main estimates for the structure. The level of detail will have an impact on the precision of the cost-estimates if it affects the number and geometry of the representation of the overpass's components. This will happen mainly for low levels of detail.


### MAIN INPUT

The main parameters to consider are:

* Number of overpasses to create
* Width of the Highway stretch that will be traversed by the overpass at each traversal location.
* width of the overpasses.

These parameters, by themselves, are not enough to completely define a BIM model but if a base reference model exists, they will enable the establishment of a typified solution for the given input.


### MAIN OUTPUT

* 2D Representation media of the BIM models with structural solutions adapted to the provided input.
* Cost-estimate/Quantity-estimate for all the generated models.
* BIM model in IFC format for all the generated overpasses.


### WHAT THE TOOL DOES

* Based on the main input parameters, the principal geometry of the model will be adjusted accordingly.
* The level of detail of the BIM models can be adjusted without breaking the main functionality.
* There is a secondary layer of parameters that allows the finetuning of the model and the cost-estimates.


### WHAT THE TOOL DOES NOT

* It does not simulate or assembles any kind of animation for the construction process of the overpasses
* It does not take into account additional parameters of the highway profile such as elevation difference, skew angle, etc.


### ADDITIONAL PARAMETERS 

* Main overpass span (based on main Highway profile);
* Typified sidespan-mainspan relations to determine the total length of the overpass;
* Beam width and midslabs/cantilever widths (based on total width of the overpass);
* Beam height and midslabs/cantilever thicknesses;
* Number of Beams (based on the overpass width);


### ASSUMPTIONS

* The piers will be those adopted from the actual PS35 project, with a fixed, average height. They will have simple footings as foundations.
* The abutments will also be assumed to have a fixed geometry, with a certain amount of reinforcement, having a fixed contribution to the final prices / quantities.
* The will be a minimum and maximum widths both for the Highway as well as for the Overpass. These will also affect some of the other parameters.


## LOGIC

* The logic for determining the main model-derived data will be based on the analysis of past solutions adopted for overpass bridges designed by the company, and the required relations to the input parameters will be established.
* For that, several projects will be studied, in order to setup an algorithm that adjusts the geometry to the input data. Once the basic model-defining variables are determined, these will be used to also adjust the parameters that govern the output related quantities.
* The basic parameter is the width of the main highway profile. Based on these values, the main span of the overpass shall be defined and then a total length for the bridge will be determined based on span relations. This will have an impact on the height of the overpass beams and to some extent the thickness of the slabs.
* The second most important parameter is the total width of the overpass. Based on this, a metric to determine the number of beams must be derived and then, depending on the main span length, and the total width of the overpass, widths and thicknesses for the slabs and cantilevers must be obtained.

## ASSETS

* The tool will be composed of three distinct areas:
    * Input Area (Microsoft Excel Sheet)
    * Processing Area (Grasshopper environment connected to a Tekla BIM Model through live-link)
    * Output Area (Microsoft Excel output file [BOQ] and IFC BIM Model)

* Notes:
    * The Input Area will also pre-Process the input data and resolve the main aspects that define the Processing Solution. 
    * The Processing Area will just take this pre-analysed data and use it to produce the main parameters that are going to govern the geometry of the BIM Model.
    * The Input Area will also directly post-process the derived data and generate the main BOQ-related results.

### Input Area (Excel)

The Input Area consists in a Microsoft Excel worksheet formatted and prepared to facilitate the input of data. The main input it will handle is:

* main input parameters (previously defined)
* type and dimensions for piers to be used in simulation (only one type at a time)
* type and dimensions for the deck to be used in simulation (only one type at a time)

Unless it is shown that more than one type is very useful, such a feature will not be implemented. To be able to create several budgets for different crossing types, the whole routine must be run as many times as needed.

### Processing Area (Grasshopper - Tekla)

Some notes about the processing area of the program

### Output Area (Excel / IFC)

Additional notes about the output format for data, both in Excel format for BOQ as well as in IFC format for the model proper.




