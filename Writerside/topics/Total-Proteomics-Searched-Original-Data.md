# Total Proteomics - Searched (Original) Data

![total_proteomics.searched_data.png](total_proteomics.searched_data.png)

The input searched (original) or raw file requires a tabulated text file with the same primary id column as the differential analysis file.
The rest would be sample relative intensity in wide format. 

In the example data above, the `T: Index` column was the primary id column and assigned as the value for `Select Primary ID` parameter.
The rest of the columns were sample relative intensity columns from various sample of 4 different conditions (AGB1 abd Cis at 4Hr and 24Hr).

If your data separate conditions and replicate in column name using `.`, Curtain will automatically parse the condition and assign the appropriate condition to the data. If there are multiple `.` in the name, only the last `.` will be used to separate condition and replicate.

If the data has already been log2 transformed, please tick the `Data was log2 transformed` check box.

Example table:

| T: Index | 4HrAGB1     | 4HrAGB1.1   | 4HrAGB1.2   | 4Hr-Cis.0   | 4Hr-Cis.1   | 4Hr-Cis.2   | 24HrAGB1.0  | 24HrAGB1.1  | 24HrAGB1.2 | 24Hr-Cis.0  | 24Hr-Cis.1  | 24Hr-Cis.2  |
|----------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|------------|-------------|-------------|-------------|
| Q2M2I8   | 1398743.504 | 1392166.178 | 1507472.235 | 1419252.645 | 1469608.046 | 1692588.689 | 1678452.176 | 1549530.799 | 1603841.34 | 1561498.768 | 1424969.886 | 1442160.198 |