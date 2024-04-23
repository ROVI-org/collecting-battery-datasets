# Synthetic Data of Battery Life 

This data are from simulations of _Batteries_ from Paul Gasper at NREL which vary depending on the stressors that include both environmental conditions (e.g., temperature) and use (e.g. Depth of Discharge). 

There are two datasets within the collection: one where the stressors are the same each day, and a second where they are varied.

- dt: Elapsed time per cycle
- t: Total elapsed time at start of cycle
- dEFC: Number of Equivalent Full Cycles per cycle
- EFC: Total number of Equivalent Full Cycles at start of cycle
- soc: Maximum state of charge during charging
- dod: Maximum state of charge during discharge
- Ua: 
- UaN: 
- TdegC: Temperature during cycle (units: C)
- TdegK: Temperature during cycle (units: K)
- TdegKN: Temperature during cycle, normalized _to what_


Each dataset includes a summary for each day (assuming one day per cycle) where the inputs are:

- Q: Cell energy (units: Watt-Hr)
- q: Cell capacity (units: A-hr)
- q_LLI: Model state dealing with loss of Li Inventory (LLI)
- q_LAM: Model state dealing with loss of Active Material?
- R: Resistance...
- r: Resistance? 
- r_LLI: Model state dealing with LLI
- r_LAM: Model state dealing with LAM
- q_loss_LLI_cal: Loss of capacity due to LLI from calendar aging
- q_loss_LLI_cyc: Loss of capacity due to LLI from cycling
- q_loss_LAM: Loss of capacity due to LLI from cycling
- r_gain_LLI_cal: Increase in resistance due to LLI from calendar aging
- r_gain_LLI_cyc: Increase in resistance due to LLI from cycling
- r_gain_LAM: Increase in resistance due to LAM