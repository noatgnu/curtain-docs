# Protein Search and Selection

Curtain provides a simple way to search for your protein or selection of proteins of interests from the differential analysis.

## Basic Protein Search

![basic_protein_search.png](basic_protein_search.png)

Curtain index all the protein from the differential analysis file and use it to provide a typeahead search function. You can search by Gene Names (UniProt data) or Primary IDs (supplied in primary id column).
If the typeahead does not display your protein, that means the identifier that you typed could not be found.

Upon clicking the `Search` button or pressing `Enter` key, Curtain will process and create a new selection group. The selection group will appear in the volcano plot as a different color data point or group of data points with the legend title of the protein.

## Batch Protein Search

![batch_protein_search.png](batch_protein_search.png)

If you have a list of proteins that you want to search for, you can do so by clicking `Batch Search` button. This will show a prompt as above where you can paste in a list of proteins separated by new line.
You can select whether the input list includes gene names or primary ids.

You should type in a title for the selection group that will be created. If you leave it blank, Curtain will automatically generate a title for you.

If you want to use one of our built-in protein lists, you can type in the `Protein/Category search` text input of the protein or category you are interested in.
This will show a list of categories with that you can select from. Title field will be automatically filled in with the category name  and the textbox will also be filled with all the protein from the list.

If you want to browse the built-in protein lists rather than using typeahead, you can click the `Builtin category` to select an general `Category`. Then followed by the `Builtin sub-category` to select a more specific protein group that you are interests in.

If you are logged in, you can also save the selection group to your account by pressing the `Save` button after entering the protein list and the title of the protein group.

## Selection Group Management

If you want to modify the selection group or delete it, you can do so by clicking the `Session` -> `Data Selection Management`.

![data_selection_management.png](data_selection_management.png)

Here you can choose to merge selection groups together, delete, edit, or rename selection.

- Checking the Remove boxes and then clicking `Save` will remove the selection group from your selection.
- Checking the Merge boxes and then clicking `Save` will merge the selection groups together. The merged selection group will have the title of both selection groups separated by `-`.

To edit the selection content of a group, you will need to click on the `Edit Selection` button.
This will expand the prompt and show the group's content (example below).

Total Proteomics:

![total_proteomics.data_selection_management.content.png](total_proteomics.data_selection_management.content.png)

PTM Proteomics:

![ptm_proteomics.data_selection_management.content.png](ptm_proteomics.data_selection_management.content.png)

By checking the Remove from selection boxes and then save, you can remove the PTMs or proteins from the selection.

Any changes made to the selection group will need the volcano plot to be redrawn to reflect the changes in the visualization.