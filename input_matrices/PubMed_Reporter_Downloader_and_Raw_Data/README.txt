====File Descriptions===
1. Output Dataframes folder contains all completed output files in the form of an excel table. Output dataframes contain all publication and grant information used in the manuscript and figures

2. RawData folder contains the stored results for each search that is performed as part of generating the output files. Each search folder contains .txt files of the actual text returned from each individual gene search. 
	Also included are the manual grant searches for TP53 from datasets with >10k grants under that gene

3. ManualvsAPI.ppt is a small powerpoint presentation which compares the results of searches performed using the API vs using a manual search through a respective database website

4. PubMed_and_NIH_data_downloader_master.ipynb is a jupyter notebook which is designed to retrieve grant and publication data and store it in an Output Dataframe for all searches and controls included in our results.

5. PubMed_and_NIH_data_Methods is a 3-page document explainging all functions and features of the above notebook in more depth, as well as the differences between each of the 7 searches

6. Synonyms_filtered_v3 is an excel file containing a list of 570 COSMIC Tier 1 genes and their most common aliases as found on the Uniprot Database. Also included are a list of synonyms which are excluded for any reason.

===Installation===

A. Running source code - PubMed_and_NIH_data_downloader_master.ipynb:

The source code was written in python 3.8.5 using Jupyter notebook format. 
The authors recommend installing Anaconda or similar package where the libraries required are conveniently obtained: https://www.anaconda.com/

Jupyter notebook is required to open the source code. This package is installed with Anaconda and can be started using Anaconda Navigator. 

If not using Anaconda, Jupyter can be independently installed at the following link. https://jupyter.org

The source code is present in the file, PubMed_and_NIH_data_downloader_master.ipynb. To open the file, initiate Jupyter notebook from Anaconda Navigator. 
	The software opens up in the default browser application. Now, change the current working directory to the folder where the zipped file has been unzipped. 
	It is important that the whole zipped file is unzipped in the same location preserving the sub-folder structure and files. 
	Once within the folder, clicking on the source code PubMed_and_NIH_data_downloader_master.ipynb opens the main processing notebook. 
	The commands are divided into blocks, with each block after the first being a different search. Each block can be run independently after the intial block. 
	The whole notebook can be run by scrolling the notebook menu and clicking the tab 'Cell' and then 'Run All'.
	This file performs searches to both NIH and PubMed databases and stores the results for later use. 
	It then collects data corresponding to figures and tables in the manuscript and saves them in a Output Dataframes folder.

A full description of the functions and results of the code can be found in PubMed_and_NIH_data_Methods file

B. Dependencies Required to run the source code:

The following libraries were used in compiling the source code.
1. pandas 1.1.3
2. urllib 3.8
3. requests 2.24.0

The libraries may be installed/updated using pip command or conda command or Anaconda navigator GUI. Anaconda by default installs the latest version of these three libraries.

C. Updating NIH RePORTER and NCBI PubMed Data: 
	The stored search data is up to date in as of late May 2022, and the stored search files are already present in RawData/ folder.
	As long as the appropriately named .txt file is stored in the appropriate location, search information will be retrieved from the stored file instead of actually querying a new search from thr databases
	The data may be updated in the future by removing the correpsinding text file of a search from its folder, either deleting the file or storing it somewhere else.
	Upon running the code, if a .txt file is missing, a full search will be passed to the respective database and stored as a new .txt file under the apporpriate name, along with a timestamp
	If all .txt files are removed, the entire data set will be re-downloaded and stored

D. Manaul searches for genes with 10k+ grants
	when querying NIH RePORTER, grant funding data can only be retrieved for the first 10000 results, with any grants after those first 10k needing to be manually searched using the database website
	In order to accurately calculate grant funding data for highly publicized genes like TP53, a manual search must be performed and totaled in order to find the true value of grant funding for said genes
	As of May 2022, three of the seven searches have over 10k grants for TP53. Manual searches of TP53 for all three search criteria have been stored as excel files under the RawData/ folder, and these searches are used to find the actual Award Amount for TP53
	If a new manual search is required, you can perform a new manual search by going to the NIH RePORTER website and selecting the Advanced Search under the search bar.
	Copy and paste the search keywords (the string stored after "searchtext", before "includefields") from the gene's search JSON (the code will automatically print this when calculating for TP53).
	Make sure to mark Advanced under "Text Search Logic", select all years under the Fiscal Year dropdown menu, and change "Limit Project search to:" to either "Project Title" and/or "Project Abstracts", depending on which search is being made
	Once all the parameters are defined, perform the search and find the option in the upper right to "Export". Select the .csv format, make sure that the option to export search criteria is unchecked. The only values needed are application ID, fiscal year, and total cost, but other values can also be exported if desired
	Finally, change the name of the excel to reflect one of the corresponding searches stored in the RawData/ folder, and save to said folder, and the manual search should be used for finding TP53 Award Amount

It should be noted that even the manual search function of NIH RePORTER can only retrieve up to a max of 15000 results, so if you have a gene with 15k+ genes, it will likely need to be broken into multiple searches by year or some other differentiator