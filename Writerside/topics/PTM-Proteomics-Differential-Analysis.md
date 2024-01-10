# PTM Proteomics - Differential Analysis

![ptm_proteomics.differential_analysis.png](ptm_proteomics.differential_analysis.png)

The input form for differential analysis file requires a tabulated text file with at least 9 columns with the following example.

| Primary ID | Log2 Fold Change | -log10 Significance | UniProt Accession ID | Sequence Window | Peptide Sequence | PTM Position in Protein | PTM Position in Peptides | Probability Score |
|------------|------------------|---------------------|----------------------|-----------------|------------------|-------------------------|--------------------------|-------------------|
| Q9ULR3_K50 | -1.956634649     | 5.217589407         | Q9ULR3               | LKVGPAIkDRRLSEE | VGPAIkDR         | 50                      | 6                        | 1                 |

Different to the total proteomics differential analysis file, a separate UniProt Accession ID column is required since the primary id.
- In the example image above, the `Index` column contains the primary id and was assigned as the `Select Primary IDs` parameter.
- For `Select UniProt Accession IsD` parameter, the `ProteinID` column was assigned which contains the acc id, including isoform information.
- The `Select Probability Score` parameter was assigned the `MaxPepProb` column which contains the probability score given to the PTM site should only contain 1 single value.
- The `Select Fold Change` parameter was assigned the `Welch's T-test Difference AO_UT` column (Log2 Fold Change column) and `Select Significant` parameter was assigned the `-Log Welch's T-test p-value AO_UT` column (-Log10 Significance column).
- The `Sequence Window` parameter was assigned the `SequenceWindow` column should only contain 1 value. 
- The `Peptide sequences` parameter was assigned the `Peptide` column should only contain 1 value.
- The `PTM positions` parameter was assigned the `Positions` column with the position of the PTM within the protein sequence; should only contain 1 value.
- The `PTM positions in peptides` parameter was assigned the `Position.in.peptide` column with the position of the PTM within the peptide sequence; should only contain 1 value.

An aspect similar to the total proteomics differential analysis file is the `Comparison` parameter. If your data is in long form format where there is a column which indicates the label of the different comparisons, you can assign `Comparison` parameter as that column.
After that, you can select the label of the comparison of interests from the `Select Comparison` parameter. By default, if these two parameters are not assigned, Curtain will automatically give `Comparison` parameter `CurtainSetComparison` column name and `Select Comparison` parameter the value `1`.

If your fold change data and/or significannce data are not appropriately log transformed, you can tick the appropriate check box underneath each parameter to have curtain perform log transformation.

