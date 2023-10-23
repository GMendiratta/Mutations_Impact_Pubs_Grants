====File Descriptions===
1. Results/ folder contains figures and all the data tables presented in the manuscript.

2. input_matrices/ folder contains aggregated data tables from different databases included in our work.

3. Analysis_Source_Code*.ipynb are a Jupyter notebook python code designed for visual and logical representation of our pipeline and is capable of generating all of our results.

4. Analysis_Source_Code*.pdf are a pdf copies of the respective jupyter notebooks above so the algorithm may be viewed without installing python and jupyter.

===Installation Guide===

A. Running source code - Analysis_Source_Code.ipynb:

The source code was written in python 3.8.5 using Jupyter notebook format. 
The authors recommend installing Anaconda or similar package where the libraries required are conveniently obtained: https://www.anaconda.com/

Jupyter notebook is required to open the source code. This package is installed with Anaconda and can be started using Anaconda Navigator. 

If not using Anaconda, Jupyter can be independently installed at the following link. https://jupyter.org

The source code is present in the file, Analysis_Source_Code.ipynb. To open the file, initiate Jupyter notebook from Anaconda Navigator. 
	The software opens up in the default browser application. Now, change the current working directory to the folder where the has been unzipped. 
	It is important that the whole zipped file is unzipped in the same location preserving the sub-folder structure and files. 
	Once within the folder, clicking on the source code Analysis_Source_Code.ipynb opens the main processing notebook. 
	The commands are divided into blocks which can be run independently by pressing the play button. 
	The whole notebook can be run by scrolling the notebook menu and clicking the tab 'Cell' and then 'Run All'.
	This file generates data and plots corresponding to figures and tables in the manuscript and saves them in a Results folder. 
	Running time is under 20 mins for a processor with a >2Ghz clock and >=8GB RAM. 


B. Dependencies Required to run the source code:

The following libraries were used in compiling the source code.
1. NumPy 1.21.0
2. pandas 1.3.0
3. matplotlib 3.4.2
4. seaborn 0.11.1
5. statsmodels 0.13.0
6. scipy 1.7.0
The libraries may be installed/updated using pip command or conda command or Anaconda navigator GUI. Anaconda by default installs the latest version of these three libraries.
*Note that while the location within a computer is not important, the relative folder structure of the contents of this package are important and must be extracted as-is from the provided zipped file.