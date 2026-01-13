# RiR_Review
Toolbar focused on review

For instructions on necessary installations see: [White Work](https://work.white.se/rhino-inside-revit/)  
General guides RiR: https://www.rhino3d.com/inside/revit/1.0/guides/  
Add the toolbar folder to your rhino.inside.revit tab according to this instruction (in the picture): https://discourse.mcneel.com/t/sharing-rhino-inside-scripts-among-team/131474/4 
or run the script with Grasshopper Player

## List of Scripts with short description

### Rotate Walls slightly off axis
**10_Rev_Off Axis_Wall** - Shows walls in plan that are slightly off axis (smaller than 1 degree) from grid directions  
**11_Ro_Wall_Off Axis** - Rotates selected walls if they are slightly off axis
**20_Check_Ceiling_Room** - Check where ceiling and room outlines deviates and draws these regions on a reflected ceiling plan 

# Script Documentation

## 10_Rev_Off Axis_Wall

**Intent:**  
To visualize and select walls with off axis direction

**Input:**  
An active viewport with visible gridlines

**Output:**  
Filled regions showing which walls that are off axis, These walls are also selected in the viewport.

**Dependencies:**  
Rhino  
Revit  
Rhino Inside Revit  

**Instructions:**
The script is best runned from the Revit Toolbar
1. While in a plan view with visible gridlines, click the script icon.
2. If walls are selected by the script, you might use **11_Ro_Wall_Off Axis** to rotate the walls.   
The script will select walls that are >1 degree of the direction of a gridline.
A new type of filled region is created which is deletable with **00_Del_RiR**

**Limitations/Known issues** 
If your model lacks filled regions or if theese are hidden in ypor active view they might not be visible.

**Linked scripts**
**10_Rev_Off Axis_Wall** can be used to rotate selected walls. **00_Del_RiR** can be used to delete filled regions in view.

**Contact:** 
Staffan Linné, staffan.linne@white.se


## 11_Ro_Wall_Off Axis

**Intent:**  
Rotate selected walls so they align with grids visible in view

**Input:**  
Views selected in the viewport.

**Output:**  
A rotation of the selected walls if they are off axis

**Dependencies:**  
Rhino  
Revit  
Rhino Inside Revit  

**Instructions:**
The script is best runned from the Revit Toolbar

1. Select an object (or several) in the Revit viewport  
2. Run script  
3. The script will rotate walls according to the gridline that has the most similar direction to the wall line direction  

**Limitations/Known issues** 
Long walls with hosted objects might delete some of these objects. Reason unknown. Might be resolved in the future.

**Linked scripts**
10_Rev_Off Axis_Wall can be used to reveal and select walls off axis 

**Contact:** 
Staffan Linné, staffan.linne@white.se



## 20_Check_Ceiling_Room

**Intent:**  
Review borders of ceiling objects in a reflected ceiling plan

**Input:**  
An active reflected ceiling plan

**Output:**  
Red detail lines where room and ceiling deviates

**Dependencies:**  
Rhino  
Revit  
Rhino Inside Revit  

**Instructions:**
The script is best runned from the Revit Toolbar

1. Open a reclected ceiling view  
2. Run script  
3. The script will create a line type and draw lines of that type
   
**Limitations/Known issues** 
Falting or complicated Revit room geometry can hinder the script to work properly 

**Linked scripts**
**00_Del RiR** deletes drawn lines 

**Contact:** 
Staffan Linné, staffan.linne@white.se




