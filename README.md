# NeurIPS-2024
Kaggle data science competition to create a modle to predict if drug molecules will bind to proteins


Dataset Description
Overview
The examples in the competition dataset are represented by a binary classification of whether a given small molecule is a binder or not to one of three protein targets. The data were collected using DNA-encoded chemical library (DEL) technology.

We represent chemistry with SMILES (Simplified Molecular-Input Line-Entry System) and the labels as binary binding classifications, one per protein target of three targets.

Files
[train/test].[csv/parquet] - The train or test data, available in both the csv and parquet formats.

id - A unique example_id that we use to identify the molecule-binding target pair.
buildingblock1_smiles - The structure, in SMILES, of the first building block
buildingblock2_smiles - The structure, in SMILES, of the second building block
buildingblock3_smiles - The structure, in SMILES, of the third building block
molecule_smiles - The structure of the fully assembled molecule, in SMILES. This includes the three building blocks and the triazine core. Note we use a [Dy] as the stand-in for the DNA linker.
protein_name - The protein target name
binds - The target column. A binary class label of whether the molecule binds to the protein. Not available for the test set.
sample_submission.csv - A sample submission file in the correct format

Competition data
All data were generated in-house at Leash Biosciences. We are providing roughly 98M training examples per protein, 200K validation examples per protein, and 360K test molecules per protein. To test generalizability, the test set contains building blocks that are not in the training set. These datasets are very imbalanced: roughly 0.5% of examples are classified as binders; we used 3 rounds of selection in triplicate to identify binders experimentally. Following the competition, Leash will make all the data available for future use (3 targets * 3 rounds of selection * 3 replicates * 133M molecules, or 3.6B measurements).

Targets
Proteins are encoded in the genome, and names of the genes encoding those proteins are typically bestowed by their discoverers and regulated by the Hugo Gene Nomenclature Committee. The protein products of these genes can sometimes have different names, often due to the history of their discovery.

We screened three protein targets for this competition.

EPHX2 (sEH)
The first target, epoxide hydrolase 2, is encoded by the EPHX2 genetic locus, and its protein product is commonly named “soluble epoxide hydrolase”, or abbreviated to sEH. Hydrolases are enzymes that catalyze certain chemical reactions, and EPHX2/sEH also hydrolyzes certain phosphate groups. EPHX2/sEH is a potential drug target for high blood pressure and diabetes progression, and small molecules inhibiting EPHX2/sEH from earlier DEL efforts made it to clinical trials.

EPHX2/sEH was also screened with DELs, and hits predicted with ML approaches, in a recent study but the screening data were not published. We included EPHX2/sEH to allow contestants an external gut check for model performance by comparing to these previously-published results.

We screened EPHX2/sEH purchased from Cayman Chemical, a life sciences commercial vendor. For those contestants wishing to incorporate protein structural information in their submissions, the amino sequence is positions 2-555 from UniProt entry P34913, the crystal structure can be found in PDB entry 3i28, and predicted structure can be found in AlphaFold2 entry 34913. Additional EPHX2/sEH crystal structures with ligands bound can be found in PDB.

BRD4
The second target, bromodomain 4, is encoded by the BRD4 locus and its protein product is also named BRD4. Bromodomains bind to protein spools in the nucleus that DNA wraps around (called histones) and affect the likelihood that the DNA nearby is going to be transcribed, producing new gene products. Bromodomains play roles in cancer progression and a number of drugs have been discovered to inhibit their activities.

BRD4 has been screened with DEL approaches previously but the screening data were not published. We included BRD4 to allow contestants to evaluate candidate molecules for oncology indications.

We screened BRD4 purchased from Active Motif, a life sciences commercial vendor. For those contestants wishing to incorporate protein structural information in their submissions, the amino acid sequence is positions 44-460 from UniProt entry O60885-1, the crystal structure (for a single domain) can be found in PDB entry 7USK and predicted structure can be found in AlphaFold2 entry O60885. Additional BRD4 crystal structures with ligands bound can be found in PDB.

ALB (HSA)
The third target, serum albumin, is encoded by the ALB locus and its protein product is also named ALB. The protein product is sometimes abbreviated as HSA, for “human serum albumin”. ALB, the most common protein in the blood, is used to drive osmotic pressure (to bring fluid back from tissues into blood vessels) and to transport many ligands, hormones, fatty acids, and more.

Albumin, being the most abundant protein in the blood, often plays a role in absorbing candidate drugs in the body and sequestering them from their target tissues. Adjusting candidate drugs to bind less to albumin and other blood proteins is a strategy to help these candidate drugs be more effective.

ALB has been screened with DEL approaches previously but the screening data were not published. We included ALB to allow contestants to build models that might have a larger impact on drug discovery across many disease types. The ability to predict ALB binding well would allow drug developers to improve their candidate small molecule therapies much more quickly than physically manufacturing many variants and testing them against ALB empirically in an iterative process.

We screened ALB purchased from Active Motif. For those contestants wishing to incorporate protein structural information in their submissions, the amino acid sequence is positions 25 to 609 from UniProt entry P02768, the crystal structure can be found in PDB entry 1AO6, and predicted structure can be found in AlphaFold2 entry P02768. Additional ALB crystal structures with ligands bound can be found in PDB.
