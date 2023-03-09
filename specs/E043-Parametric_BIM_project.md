# SPECIFICATION FOR BIM PROJECT
## Parametric Overpass Model Previewer

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
* Cost-estimate for all the generated models.
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

