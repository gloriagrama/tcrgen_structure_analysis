# tcrgen_structure_analysis
Analysis pipeline for generated TCR cdr3b structural modelling and evaluation

Search the [TCR3d Database](https://tcr3d.ibbr.umd.edu/mhc1_chains) for solved TCR–pMHC structures corresponding to the generated epitopes and extract the associated PDB IDs. cdr3a and cdr3b sequence annotations can be identified in the structures drop down (alpha and beta respectively) for each PDB ID.
Run the TCR alpha and beta chains through [ANARCI](https://opig.stats.ox.ac.uk/webapps/sabdab-sabpred/sabpred/anarci/) to identify V and J gene usage.
Write all solved structure information to a compiled metadata file containing the following required columns:

`{'Peptide', 'TRAV', 'TRAJ', 'CDR3α', 'TRBV', 'TRBJ', 'CDR3β', 'PDB ID'}`
