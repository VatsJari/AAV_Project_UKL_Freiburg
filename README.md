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

Create a folder named Cell_Count_Analysis and inside it, organize your files like this:

Cell_Count_Analysis/
│
├── data/
│   └── cell_counts.xlsx       # This is the Excel file with all your sheets (GFAP, Olig, etc.)
│
├── scripts/
│   └── GFAP_analysis.Rmd      # This is the RMarkdown script for astrocyte analysis
│   └── Olig_analysis.Rmd      # This is the RMarkdown script for oligodendrocyte analysis
│
└── README.md                  # This file
📦 Step-by-Step Instructions to Run the Analysis

✅ Step 1: Open RStudio
After installation, open RStudio.
Go to File → Open Project (optional) or open a new file.
✅ Step 2: Install Required Packages
Before running anything, run the following lines in the Console to install necessary packages:

install.packages("tidyverse")
install.packages("readxl")
install.packages("Seurat")
✅ Step 3: Open the .Rmd Script
In RStudio, go to File → Open File and select either:
GFAP_analysis.Rmd → for astrocyte data
Olig_analysis.Rmd → for oligodendrocyte data
This will open the file in the editor.
✅ Step 4: Change the File Path
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
🆘 Common Questions

❓ What if I get a "file not found" error?
Make sure the path to your Excel file is correct.
You can use file.choose() to interactively pick the file:
readxl::read_excel(file.choose(), sheet = "df_GFAP_avg")
❓ What is an .Rmd file?
It’s a Markdown + R file. You write text and R code together.
When you "Knit", it runs the R code and outputs an HTML report.
❓ How do I export the plots?
After knitting to HTML, right-click any plot → Save image.
You can also copy plots manually from RStudio’s Plots tab.
🧼 Good Practices

Don’t edit raw data. Always use the same structure (column names must match those used in the script).
Avoid spaces in file or folder names.
Keep a versioned copy of the scripts (v1, v2, etc.) if modifying.
📩 Questions?

If collaborators have any issues:

Contact: vatsaljariwala@domain.com (example address)
Or open an issue if you’re using a shared GitHub repo
