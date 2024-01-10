# Total Proteomics - Differential Analysis

![total_proteomics.differential_analysis_input_form.png](total_proteomics.differential_analysis_input_form.png)

The input form for differential analysis file requires a tabulated text file with at least 3 columns with the following example.

| Primary ID | Log2 Fold Change | -log10 Significance |
|------------|------------------|---------------------|
| Q2M2I8     | 0.013686244      | 0.173648525         |
| Q9ULR3     | -1.956634649     | 5.217589407         |
| P61026     | -0.040167618     | 0.215668235         |

From the example image above the `Selected Primary ID` parameter is the `Index` column (Primary ID column), `Select Fold Change` column is the `Difference(Log2): 4HrAGB1/4Hr-Cis` column
Log2 Fold Change column)and `Select Significant` column is the `Significance(-Log10): 4HrAGB1/4Hr-Cis` column (-Log10 Significance column).

If your fold change data and/or significannce data are not appropriately log transformed, you can tick the appropriate check box underneath each parameter to have curtain perform log transformation.

If your data is in long form format where there is a column which indicates the label of the different comparisons, you can assign `Comparison` parameter as that column.
After that, you can select the label of the comparison of interests from the `Select Comparison` parameter. By default, if these two parameters are not assigned, Curtain will automatically give `Comparison` parameter `CurtainComparison` column name and `Select Comparison` parameter the value `1`.






