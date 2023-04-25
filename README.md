# LifeSoaksPaper_Data

This repo includes data for the publication "LifeSoaks: A tool for analyzing solvent channels in protein crystals and obstacles for soaking experiments".
(TODO: add doi when paper is published)

The relevant data sets are stored in the folder "Jupyter_GitHub/data/input_data". The folder includes:

- "WholePDBBottleneckCalculation.csv":
LifeSoaks results for all publically availabe PDB structures released by 18th of August 2022. Its analysis was performed with the provided Jupyter Notebook "LifeSoaksDataAnalysis.ipynb". Resulting plots are provided in "data/plots"
PDBID: Protein Data Base four letter code
HasCrystal: States wether a crystal arrangement exists. If no the computation is meaningless
NumberOfRestarts: How often was the computation redone with increased pertubation when it failed initially
VoronoiComputationsSuccessful: Was the computation successful
OverallBottleneckRadius: The bottleneck radius of the largest channel
RuntimeInSeconds: Run time in seconds
SolventContent: Solvent content as computed by LifeSoaks (may differ from PDB deposited value)
MatthewsCoefficient: Matthews coefficient as computed by LifeSoaks (may differ from PDB deposited value)
HeavyAtomsPerUnitCell: Number of heavy atoms in each unit cell
Classification: Structure type as stated in the PDB HEADER entry
AtomsPerComplex: Number of heavy atoms in each complex
AtomsPerComplexWithCoordinates: Number of heavy atoms in each complex with coordinates
BottleneckRadius_bc: Bottleneck radius from the bc surface (in a/x direction)
BottleneckRadius_ac: Bottleneck radius from the ac surface (in b/y direction)
BottleneckRadius_ab: Bottleneck radius from the ab surface (in c/z direction)
FirstBottleneckPosition: Coordinates of the first bottleneck position. If there are symmetries inside a unit cell there will likely exist more but they are not shown in the line output

- "lifesoaks_activesite_lig_multiconf.csv":
LifeSoaks results for the dataset of protein-ligand complexes successfully solved by soaking and the minimal projection radii of the ligand conformers as calculated with ChemAxon's cxcalc. This set includes non-oligomeric ligands with more than one predicted confromer by Conformator. 
pdb: PDB-ID, 
lig: ligand identifier, 
insiterad: radius of the largest sphere the binding site is accessible to,
outsiterad: radius of the largest sphere the space immediately in front of the binding site is accessible to, 
minrad: the minimal projection radius of the conformer with the smallest minimal projection radius, 
maxrad: the minimal projection radius of the conformer with the largest minimal projection radius, 
meanrad: the mean of the minimal projection radii of all conformers, 
medianrad: the median of the minimal projection radii of all conformers.

- "lifesoaks_activesite_lig_singleconf.csv":
LifeSoaks results for the dataset of protein-ligand complexes successfully solved by soaking and the minimal projection radii of the ligand conformers as calculated with ChemAxon's cxcalc. This set includes non-oligomeric ligands with exactly one predicted confromer by Conformator. 
pdb: PDB-ID, 
lig: ligand identifier, 
insiterad: radius of the largest sphere the binding site is accessible to, 
outsiterad: radius of the largest sphere the space immediately in front of the binding site is accessible to, 
minrad: the minimal projection radius of the conformer with the smallest minimal projection radius, 
maxrad: the minimal projection radius of the conformer with the largest minimal projection radius, 
meanrad: the mean of the minimal projection radii of all conformers, 
medianrad: the median of the minimal projection radii of all conformers.

- "lifesoaks_mapchannels_comparison.csv":
The maximum radii as calculated by LifeSoaks and MAP_CHANNELS that a sphere can have to traverse the crystal in 1D, 2D, and 3D direction. Please note that these are radii for traversing a crystal and not related to ligand binding sites. In addition, the calculated Matthews coefficient (mc) and solvent content (sc) by both methods is given. The run times (time) for LifeSoaks and MAP_CHANNELS calculations (time) are given in seconds. The number of atoms in the unit cell is given in the column "unit_cell_atoms".

- "soaking_subset_multimers.csv":
The dataset of oligo- and polymeric ligands that were successfully soaked in their corresponding target protein according to the annotations in the corresponding PDB files. 
pdb: PDB-ID of the complex, 
soaked_molecule: chain ID or residue names of the soaked molecules.
