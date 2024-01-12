# Converting to Input Files for CurtainPTM

Many program have different output format that CurtainPTM by default does not accept. This page will show you how to convert a selection of searched data format to CurtainPTM compatible input. We will mostly focus on the differential analysis files.

## Requirements

- Python 3.9 or above
- `curtainutils` package

## Installation

```bash
pip install curtainutils
```

## MSFragger PTM single site output to CurtainPTM input

Ensure that your MSFragger PTM single site output file with differential analysis result has the following columns:
- `Index` column containing the unique identifier for each ptm site that should also contain the uniprot accession id. If it does not have accession id, you will have to supply the script a fasta database that was used for the search.
- `Peptide` column containing the peptide sequence.

Without fasta database:
```bash
msf-curtainptm -f <MSFragger PTM single site output file> -i <index column with site information> -o <output file> -p <peptide column>
```

With fasta database:
```bash
msf-curtainptm -f <MSFragger PTM single site output file> -i <index column with site information> -o <output file> -p <peptide column> -a <fasta file> 
```

## Convert DIA-NN PTM output to CurtainPTM input

Ensure that your DIA-NN PTM output file with differential analysis result has the following columns from the pr report file:
- `Modified.Sequence` column containing the peptide sequence with the modification site.
- `Precursor.Id` column containing the precursor fragment.
- `Protein.Group` column containing the protein.
- `PTM.Site.Confidence` column containing the probability of the modification site.

```bash
diann-curtainptm -p <differential analysis file> -r <report file> -o <output file> -m <modification_of_interests from the Modified.Sequence column>
```

## Convert Spectronaut output to CurtainPTM input

Ensure that your Spectronaut output file with differential analysis result has the following columns:
- `PTM_collapse_key` column containing the unique identifier and modification site information.
- `PEP.StrippedSequence` column containing the peptide sequence without modification.

```bash
spn-curtainptm -f <differential analysis file> -o <output file>
```
