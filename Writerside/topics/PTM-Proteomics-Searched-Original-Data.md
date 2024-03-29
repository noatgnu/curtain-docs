# PTM Proteomics - Searched (Original) Data

![ptem_proteomics.searched_data.png](ptem_proteomics.searched_data.png)

Similar to the total proteomics searched (original) data, the input searched (original) or raw file requires a tabulated text file with the same primary id column as the differential analysis file.
The rest would be sample relative intensity in wide format.

In the example data above, the `T: Index` column was the primary id column and assigned as the value for `Select Primary ID` parameter.
The rest of the columns were sample relative intensity columns from various sample of 4 different conditions (AGB1 abd Cis at 4Hr and 24Hr).

If your data separate conditions and replicate in column name using `.`, Curtain will automatically parse the condition and assign the appropriate condition to the data. If there are multiple `.` in the name, only the last `.` will be used to separate condition and replicate.

If the data has already been log2 transformed, please tick the `Data was log2 transformed` check box.