# Synthetic Flow Cell Degredation Data

> Raw data are available on the DegredationV2 folder on ROVI Box: [link](https://app.box.com/folder/263565529882)

Collects data produced from a hybrid analytical model (EZBattery) simulations of flow batterys udergoing cycling with different currents, electrolyte flow rates, and rates of degredations on 6 main battery properties.

This cell is a interdigitated cell with 780 cm^2 active area. The detailed design is introduced in manuscript: [Chao Zeng et al 2022 J. Electrochem. Soc. 169 120527.](https://iopscience.iop.org/article/10.1149/1945-7111/acadad)

This synthetic data is for a 2-electron electrochemical-reaction-based electrolyte system. The electrolyte and cell properties are randomly sampled to represent various possible electrolytes. The baseline chemistries are organic dihydroxyphenazine sulfonate (DHPS) anolyte and ferro-/ferricyanide (Fe(CN)6) catholyte. 

The randomly sampled properties as the initial state of the cell:
1) Reaction transfer coefficient: 0.3 to 0.7 (unitless)
2) Electrode specific area: 1.2e4 to 1.2e5 (1/m)
3) Membrane conductivity: 0.5 to 2.0 (S/m)
4) Reaction rate constant: 1e-8 to 1.5e-3 (m/s)
5) Mass transfer coefficient: 0.5 to 50 (unitless)
6) Initial concentration: 50 to 1500 (mol/m3)
7) Active speices diffusivity in electrolyte: 4.88e-11 to 4.81e-9 (m2/s)
8) Viscosity of electrolyte: 1e-3 to 1.2e-2 (Pa.s)
9) Negative side standard potential: -1.4 to -0.1 (V) (Positive side is fixed at 0.34 V)
10) Electrolyte ionic conductivity: 10 to 100 (S/m)

There are 1024 combinations (cases) sampled for these 10 properties.

The cell operating conditions are:
Current density: 1600 A/m2, 2400 A/m2 (the total currents for the 780 cm2 cell are 124.8 A and 187.2 A)
Electrolyte flow rate: 0.4, 0.8, 1.2, 1.6, 2 L/min
Therefore, there are 10 combinations of operating conditions. 

The cell initial (at first charge/discharge cycle) performance for the 1024 combinations of properties with 10 different operating conditions were simulated in a 3-dimentional finite element model (FEM) by COMSOL, there are totally 10240 simulations. The FEM model is introduced in manuscript: [Zeng JCES (2022)](https://iopscience.iop.org/article/10.1149/1945-7111/acadad).
Because not all the combinations of properties can operate at all the 10 operating conditions physically, there are finally 8202 successful cases. The COMSOL simulation inputs are in file Comsol_Input_Matrix.pkl, and the COMSOL simulation results for the cell initial performance are in file COMSOL_Results.pkl.

The cell performance degradation simulations were done in the hybrid analytical model EZBattery. EZBattery is a highly computational efficient 2-dimentional hybrid analytical model that can predict the cell performance in less than 1 second. The detailed introduction and explanation about EZBattery model are in the manuscripts: 
- [Yunxiang Chen et al 2021 JPS 482 (15) 228817 (DOI 10.1016/j.jpowsour.2020.228817)](https://doi.org/10.1016/j.jpowsour.2020.228817)
- [Yunxiang Chen et al 2021 JPS 506 (15) 230192 (DOI 10.1016/j.jpowsour.2021.230192)](https://doi.org/10.1016/j.jpowsour.2021.230192)
- [Yunxiang Chen et al 2023 JPS 578 (15) 233210 (DOI 10.1016/j.jpowsour.2023.233210)](https://doi.org/10.1016/j.jpowsour.2023.233210)

The cell initial performance estimated by EZbattery for the 8202 cases can match the estimations from COMSOL simulations.

The 1) to 6) cell properties potentially degrade. Each of them can degrade from its initial value to a value that is between 50% and 99% of its initial value after 500 cycles. The percentage of degradation is randomly sampled. The degradation mode is one of the three options:
1) Linear: $c(n)=1-a*n$
2) Power law: $c(n)=1-a*n^2$
3) Hyperbolic tangent function: $c(n)=1-\tanh(a*n/N)$

"n" is number of cycles. "N" is the maximum number of cycles. "a" is a calibrated coefficient that can make the degradation of the property match the sampled percentage of degradation.
For each property (1 to 6), the degraded value is $p(n)=p(0)*c(n)$ for degradation mode 1 and 2. $p(n)=p(500)+(p(0)-p(500))*c(n)$ for mode 3. "p0" is the value of property at initial state, "p500" is the value of property after 500 cycles.

EZBattery model simulated the performance degradation for the 8202 cases with randomly sampled percentage of degradations and degradation modes.

