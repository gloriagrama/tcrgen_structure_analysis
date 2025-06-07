# TCRGen Structural Analysis
Analysis pipeline for generated TCR cdr3b structural modelling and evaluation using modified TCRDock pipeline

## Compile experimentally solved structures
Search the [TCR3d Database](https://tcr3d.ibbr.umd.edu/mhc1_chains) for solved TCR–pMHC structures corresponding to the generated epitopes and extract the associated PDB IDs. cdr3a and cdr3b sequence annotations can be identified in the structures drop down (alpha and beta respectively) for each PDB ID.
Run the TCR alpha and beta chains through [ANARCI](https://opig.stats.ox.ac.uk/webapps/sabdab-sabpred/sabpred/anarci/) to identify V and J gene usage.
Write all solved structure information to a compiled metadata file containing the following required columns:

`{'Peptide', 'TRAV', 'TRAJ', 'CDR3α', 'TRBV', 'TRBJ', 'CDR3β', 'PDB ID'}`

### Determine Accuracy of TCRDock Predictions

Before aligning generated CDR3β sequences to experimental counterparts, ensure that the predicted structures do not deviate significantly from the solved structures.  
Use RMSD (Root Mean Square Deviation) as the structural similarity metric, and filter out predictions with an RMSD greater than 2 Å to retain only high-confidence models. (see workflow.ipynb)

## Alphafold env
Run alphafold_env.yaml (based on Alphafold and TCRDock requirements), tensorflow-cpu had a tendency to silently upgrade and cause dependancy conflicts so ensure that you are running 2.12.0. 
Pengfei should have access to my /scratch/ggrama/download dir with the correct alphafold docker files used in predict.sh, if not, follow step 1-3 in [alphafold/docker](https://github.com/google-deepmind/alphafold/blob/main/README.md). 
