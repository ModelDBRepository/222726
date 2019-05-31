Code to run simulations outlined in Menon, Musial, Liu, Katz, Kath, Spruston, Nicholson (2013)

This code can be used to run two sets of simulations, each corresponding to a master .hoc file:
1. code_run_single_spine.hoc
This run places a synapse on a spine at every location along the basal dendritic tree (using 10-micron segments), and calculates the maximum deflection in voltage in the spine, local dendritic segment, and soma, as well as the peak inward current and total charge flowing through the synapse. 
The code cycles through placing a single nonperforated synapse and a single perforated synapse. The latter are run with and without the experimentally observed AMPA and NMDA scaling, in all combinations. 

2. code_run_multiple_spines_on_branch.hoc
This run sequentially places 1-20 synapses on a single basal branch, and calculates the maximum voltage deflection locally and at the soma. Because the location of these synapses is chosen stochastically, the simulation runs 50 times. The code runs multiple flavors of simulations, reflecting either uniform synapse location and strength, or experimentally observed synapse location distributions (for nonperforated synapses) and strength (for perforated synapses). Triggering of local dendritic spikes is clearly observable as a nonlinear change in the maximum voltage deflection in the dendrite of interest.

Both sets of simulations use the parallel context in NEURON, and can be run specifying the number of parallel processes to use. Since this is trivially parallelizable (each simulation runs separately), there are no concerns with optimal distribution of tasks to processers. The code will also run as-is on a single processor.