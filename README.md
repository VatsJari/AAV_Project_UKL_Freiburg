# AAV_Project_UKL_Freiburg

🧠 No prior experience with R is necessary. If you follow this guide carefully, you’ll be able to run all plots successfully.
🔧 Software Required

To run the analysis, you will need to have the following installed:

1. R (version ≥ 4.0)
Free statistical programming language.
Download and install from: https://cran.r-project.org/
2. RStudio (IDE for R)
Free and beginner-friendly.
Install after R is installed.
Download here: https://posit.co/download/rstudio-desktop/
📁 Folder Structure (Recommended)



✅ Step 1: Open RStudio
After installation, open RStudio.
Go to File → Open Project (optional) or open a new file.

✅ Step 2: Install Required Packages
Before running anything, run the following lines in the Console to install necessary packages:

install.packages("tidyverse")
install.packages("readxl")
install.packages("Seurat")
✅ Step 3: Open the .Rmd Script (R-code folder)
In RStudio, go to File → Open File and select either:
GFAP_analysis.Rmd → for astrocyte data
Olig_analysis.Rmd → for oligodendrocyte data
This will open the file in the editor.

✅ Step 4: Change the File Path (Datasheet folder)
Each .Rmd script reads data from an Excel file. You need to update this path:

readxl::read_excel("path to respective cell count file", sheet = "df_GFAP_avg")
🔁 Change "path to respective cell count file" to the actual path of your Excel file. For example:

readxl::read_excel("data/cell_counts.xlsx", sheet = "df_GFAP_avg")
Repeat the same for df_Olig_avg in the Olig script.

✅ Step 5: Run the Entire Analysis
You can now run the whole document:

Click the "Knit" button at the top of RStudio (choose "Knit to HTML").
This will:
Load the data.
Perform analysis.
Generate all plots.
Output a nicely formatted HTML report with your results.
📝 If prompted, save the script first (it must be saved before it can knit).

📊 What Will Be Generated?

Each script produces several bar plots:

For GFAP (Astrocytes):
% Astrocytes (relative to DAPI)
Astrocyte count
Astrocyte colocalization with AAV
Total DAPI count
For Olig (Oligodendrocytes):
% Oligs (relative to DAPI)
Olig count
Olig colocalization with AAV

Don’t edit raw data. Always use the same structure (column names must match those used in the script).
Avoid spaces in file or folder names.


