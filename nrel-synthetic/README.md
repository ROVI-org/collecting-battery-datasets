# Synthetic Data of Battery Life 

Data was generated using the NREL BLAST model for NMC-Gr Kokam (2017) cell, with randomly varied degradation parameters to produce a wide variety of degradation trajectories. Degradation is simulated with both constant inputs (ex., same temperature over entire battery lifetime) and randomly varying inputs (ex., temperature varies randomly every day). Inputs are constrained by physical relationships, for instance, average daily state-of-charge and depth-of-discharge are somewhat co-dependent. The degradation model has several time- and cycling-dependent degradation states, outputs both relative capacity and relative resistance changes, and also outputs the ‘measurable’ discharge capacity and resistance, which are additionally dependent on the temperature of the battery at that moment.

There are two datasets within the collection: one where the stressors are the same each day, and a second where they are varied.

- dt: Elapsed time per cycle (units: days)
- t: Total elapsed time since start of the simulation (unit: days)
- dEFC: Number of Equivalent Full Cycles per cycle
- EFC: Total number of Equivalent Full Cycles at start of cycle
- soc: Average state of charge during cycling
- dod: Maximum depth of charge during cycling
- Ua: anode-to-reference potential (dependent on SOC) (units: V)
- UaN: normalized anode-to-reference potential (depedent on SOC), UaN = Ua / 0.123 V
- TdegC: Temperature during cycle (units: C)
- TdegK: Temperature during cycle (units: K)
- TdegKN: Temperature during cycle, normalized to 308.15K.


Each dataset includes a summary for each day (assuming one day per cycle) where the inputs are:

- Q: Measurable capacity (Ah) (temperature dependent), Q = f(q, TdegK) (units: Watt-Hr)
- q: Relative capacity (minimum of q_LLI and q_LAM)
- q_LLI: Relative capacity limited by lithium loss
- q_LAM: Relative capacity limited by loss of activte material
- R: Measurable resistance (Ohms) (temperature dependent), R = f(r, TdegK) (units: Ohms)
- r: Relative resistance (maximum of r_LLI and r_LAM)
- r_LLI: Relative resistance due to LLI
- r_LAM: Relative resistence due to LAM
- q_loss_LLI_cal: Loss of capacity due to LLI from calendar aging
- q_loss_LLI_cyc: Loss of capacity due to LLI from cycling
- q_loss_LAM: Loss of capacity due to LAM from cycling
- r_gain_LLI_cal: Increase in resistance due to LLI from calendar aging
- r_gain_LLI_cyc: Increase in resistance due to LLI from cycling
- r_gain_LAM: Increase in resistance due to LAM