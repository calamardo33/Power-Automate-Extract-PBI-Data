# Power-Automate-Extract-PBI-Data-Store-Csv
This flow aims to extract data from Power BI and store it in a csv.
A dataset and table have been created previous to this flow running.

<img width="400" alt="Hist_Pipe_All" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/65a62889-8cb4-4d3a-badb-a55f841e7ead">

The amount of data that can be extracted at once is limited.
I have choosen to do a dynamic loop every 15,000 rows.
We need to determine how many loops we need.
We store it in a compose action

<img width="592" alt="Hist_Pipe_Loops" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/583f32b0-2709-4030-b064-3da812b04470">

We send a dax query to the dataset filtered to 15,000 rows.
The rows will change dynamically as the loops happen

<img width="450" alt="His_Pipe_Data_Extraction" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/dcd303bf-08e1-41fd-be04-85de0e3ab0b3">


We use a condition to set the column headers in a different way depending on the loop number.
We change the name on the 1st loop but we do not on the following ones. 
This means we avoid the header row for the rest of loops.

<img width="760" alt="Hist_Pipe_Loops2" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/f8518def-941a-4672-9d2f-788977f56410">


We increment variables at every loop.

<img width="400" alt="Hist_Pipe_Variable_Increments" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/8ca39891-f775-482a-846f-3cb23f4df3f1">

The file name is dynamic with Month" and "Year" numbers.
We do a dynamic check to see if the file already exists.

<img width="450" alt="Hist_Pipe_File_filter" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/c518e2eb-d1f4-4440-92e3-9b41c85b5cf5">

We delete it if it does.
Afterwards, we create the new file.

<img width="400" alt="Hist_Pipe_Delete_Create_Files" src="https://github.com/calamardo33/Power-Automate-Extract-PBI-Data/assets/68512988/d9efdae2-f27e-4a51-849d-c6ede858678b">
