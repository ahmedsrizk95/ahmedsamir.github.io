# Modelling of Naturally Fractured Reservoir
Here we will explain the modeling of naturally fractured reservoirs in simple words. What is unique about this blog is that it will briefly and to-the-point explain each model, then mention it is areas of applications and the most important is to clearly mention the limitations of each model.

### NFRs models
The models of naturally fractured reservoirs in the literature can be categorized into the following three main categories:

#### 1- Equivalent medium models (Single medium models)

#### 2- Dual-Continuum models

    2.1. Dual porosity single permeability (DPSK)
    
    2.2. dual porosity dual permeability (DPDP)

    2.3. Triple porosity models

    2.4. Multi porosity/multi permeability models

    2.5. Multiple interaction continua (MINC)


#### 3- Discrete medium models
  
    3.1. Discrete fracture network models (DFNs)
    
    3.2. Embedded discrete fracture network models (EDFM)

    3.3. Discrete facture-vug network (DFVN)

-----------------------------------------------------------------------------------

##### The following table from (Poli et al. 2024)

<img width="955" alt="image" src="https://github.com/user-attachments/assets/98b6cdb9-c502-46f6-ac5b-2b8e8236716a">

##### To read more about the categories, I recommend to read the first chapter in (Yao et al. 2017)

-----------------------------------------------------------------------------------


Lets talk about each model
### Equivalent Medium Model:

The theoretical basis of equivalent medium model is the upscale theory, and its mathematical essence is to reduce the differential orders of the flow equations on fine scale. Thus, the up-scale model is macroscopic scale, and we can smooth the effect of heterogeneity and multi-scale characteristics of fractures and vugs. (Yao et al. 2017)

Different from double-and triple-porosity models, equivalent medium model regards the overall fractured reservoir as a continuous porous system. The heterogeneity is represented by the corresponding equivalent parameters. The advantages of this model are the high calculation efficiency and the simple requirement for parameters. Currently, the study on this model mainly focuses on the single phase flow in fractured porous media. Limitations of these models are pronounced in two-phase or multiple phase flow in fractured reservoirs. This is because there is no mature theory and method to calculate the corresponding equivalent parameters, such as the equivalent relative permeabilities and equivalent capillary curve (Wang et al. 2011; Zhou and Wang 2004). 

### Dual Porosity Model:

#### The history:
Barenblatt et al. (1960) first proposed the model.
Warren and Root (1963) applied the dual porosity model to well test analysis of naturally fractured reservoirs.
Kazemi (1969) extended the model to water/oil flow and developed a numerical algorithm to solve the fracture-flow equations while accounting for matrix/fracture fluid transfer by use of a multiphase transfer function. All subsequent developments in dual-continuum models have been geared towards refining and improving the accuracy of the mathematical transfer functions (Al-Kobaisi, 2010).


#### The main assumptions of this model are:

The reservoir consists of two distinct media: a matrix (low-permeability, high-porosity) and fractures (high-permeability, low-porosity). The matrix provides storage, while fractures provide flow pathways. So two sets of parameters are needed as input to the model. Usually these models are viewed as the figure below: sugar cubes represent the matrix and spaces between them represent the fracture.

<img width="609" alt="Screenshot 2024-09-16 at 9 55 52 PM" src="https://github.com/user-attachments/assets/f609e5c5-d330-495e-9aed-09a58bcb3b58">

Fluid flow occurs mainly in the fracture system. The matrix primarily stores fluid, while the fractures conduct the flow. However, flow is transferred from the matrix to the fracture (to be discussed later) . No flow occurs between the matrix blocks (this limitation will be overcome by the dual porosity dual permeability models).

The model homogenizes every thing; The fracture network is assumed to behave uniformly at the macroscopic level, with the matrix blocks assumed to be uniformly distributed. Dual porosity models are more of a homogenisation of how fractures affect flow. Generally, if we are not so certain where the fractures exactly are, so in general it works well and it has been the industry standard for so long.

#### Flow equations:

<img width="383" alt="Screenshot 2024-09-17 at 12 09 43 AM" src="https://github.com/user-attachments/assets/8f35ef64-a858-4349-b4b2-0bf75ecbc8f1">


#### Transfer function:

Transfer function should account for imbibition, gravity drainage, fluid expansion, and molecular diffusion (this is to be accounted for in compositional simulations).

Transfer function that accounts for pressure difference:

<img width="208" alt="Screenshot 2024-09-16 at 11 12 03 PM" src="https://github.com/user-attachments/assets/e574110a-b784-4815-b268-f9ae8f019d21">

Transfer function that accounts for gravity forces:

<img width="318" alt="Screenshot 2024-09-16 at 11 13 51 PM" src="https://github.com/user-attachments/assets/14053319-6b9d-4dbb-a10b-dda163ec1725">




#### Shape factor:

Shape factor is a geometric factor char- acteristic of the geometry and boundary conditions of the matrix block (Ramirez et al. 2009).
Warren and Roots (1963):

<img width="110" alt="Screenshot 2024-09-16 at 11 31 21 PM" src="https://github.com/user-attachments/assets/d6424193-8eb0-4f16-a9ab-20b02f17cfef">

Kazemi et al. (1976):

<img width="150" alt="Screenshot 2024-09-16 at 11 31 55 PM" src="https://github.com/user-attachments/assets/1a82cab4-4e82-4a67-b7ab-c98f70e5eafb">

Kazemi et al. (1992) and Morrow et al. (1995):

<img width="95" alt="Screenshot 2024-09-16 at 11 32 29 PM" src="https://github.com/user-attachments/assets/fb756720-39e5-4527-88f1-1bbfc64f2457">

which reduces to the previous equation for sugar cube or match-stick models.

Ramirez et al. (2009) proposed that the shape factor is generally phase- sensitive. For instance, for the same reservoir, in single-phase flow, the effective matrix-block dimensions are generally smaller, while for multiphase flow, the effective matrix-block dimensions are larger because a displacing fluid, such as gas, tends to finger through larger fractures to surround more of the matrix rock. Similar arguments can be applied to the effective block height because of film flow between blocks in the vertical direction and vertical reinfiltration of oil from one block to another.

#### The main limitations of these models are:

Simplified Geometry: Fractures are often idealized as planar, orthogonal, or evenly distributed, which is rarely the case in real geological formations. This can lead to inaccuracies in predicting reservoir behavior. Lets say we are so so certain about the position and orientation of a fracture then yes dual porosity might not be able to track local changes because it homogenises everything. Dual porosity is generally used with naturally fractured reservoirs were its highly possible we have so many small fractures all over the reservoir.

The model neglects Complex Fracture Networks; Complex fracture networks with varying aperture, length, and orientation are hard to represent accurately in dual porosity models. So the general production performance could be matched but the local saturation distribution will not be captured correctly. I will show this by comparing these two models in the figure below:

![image](https://github.com/user-attachments/assets/7d385ba2-1993-4e72-8f4a-d376f201cf9b)


**The pseudo-steady state assumption: ** This assumption may underestimate the early time recovery and mismatch the final recovery for some special systems such as gravity drainage systems (XU, 2015 after Abushaikha and Gosselin 2008)

In most dual porosity models, “lumped parameters” are given to matrix and fracture blocks by taking averages of the properties over the block volume. (XU, 2015)


### References for each category:
I have sorted the references in the way I see one should read to build his knowledge in the subject.

#### 1- Dual porosity models:

Ramirez, B., Kazemi, H., Al-Kobaisi, M., Ozkan, E. and Atan, S., 2009. A critical review for proper use of water/oil/gas transfer functions in dual-porosity naturally fractured reservoirs: Part I. SPE Reservoir Evaluation & Engineering, 12(02), pp.200-210.
Vancouver	

Al-Kobaisi, M., Kazemi, H., Ramirez, B., Ozkan, E. and Atan, S., 2009. A critical review for proper use of water/oil/gas transfer functions in dual-porosity naturally fractured reservoirs: part II. SPE Reservoir Evaluation & Engineering, 12(02), pp.211-217.

Gilman, J.R., 2003, June. Practical aspects of simulation of fractured reservoirs. In International Forum on Reservoir Simulation, Buhl, Baden-Baden, Germany (pp. 23-27).

Al-Kobaisi, M.S., 2010. Control volume mixed finite element and finite difference simulation of water-oil flow in naturally fractured reservoirs. 2010-Mines Theses & Dissertations.

Alruwayi, S., 2021. Numerical Model Sensitivity to Matrix Grid Refinement in Dual Porosity Fractured Reservoirs Application To: Improved Oil Recovery in Waterflooding (Master's thesis, Colorado School of Mines).



#### 2- EDFM
Sepehrnoori, K., Xu, Y. and Yu, W., 2020. Embedded discrete fracture modeling and application in reservoir simulation. Elsevier.

Xu, Y., 2015. Implementation and application of the embedded discrete fracture model (EDFM) for reservoir simulation in fractured reservoirs (Doctoral dissertation).

Moinfar, A., Varavei, A., Sepehrnoori, K. and Johns, R.T., 2014. Development of an efficient embedded discrete fracture model for 3D compositional reservoir simulation in fractured reservoirs. SPE Journal, 19(02), pp.289-303.

Shakiba, M., 2014. Modeling and simulation of fluid flow in naturally and hydraulically fractured reservoirs using embedded discrete fracture model (EDFM) (Doctoral dissertation).

Poli, R.E.B., Barbosa Machado, M.V. and Sepehrnoori, K., 2024. Advancements and perspectives in embedded discrete fracture models (EDFM). Energies, 17(14), p.3550.

#### 3- Triple porosity
Yao, J. and Huang, Z.Q., 2017. Fractured vuggy carbonate reservoir simulation. Berlin/Heidelberg, Germany: Springer.
Vancouver	




