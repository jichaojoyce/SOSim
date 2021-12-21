README
INSTALLATION GUIDELINES

For full instructions on how to use SOSim v2 after installation, refer to SOSim v2 User Manual 
provided with the documentation of the distribution.


HARDWARE REQUIREMENTS

SOSim v2 is publicly available via the internet and can be installed on both Macintosh and Microsoft 
Windows 32 or 64 bit. To achieve reasonable performance in terms of computational speed (hours), a 3.0 
GHz processor or better is required. SOSim is written in Python with multiprocessing, so a multicore 
processor is preferred to make the code running faster. The program is 23.8 M. SOSim uses 15 threads 
during multiprocessing. If the user does not have a multicore computer (or has a computer with fewer cores),
you will need to revise the ‘SOSimsubmerged.py’ or ‘SOSimsunken.py’ code to fit the capabilities of the 
computer. After opening the ‘SOSimsubmerged.py’ or ‘SOSimsunken.py’ code, the user can search (Ctrl+F) ‘mp.Pool(15)’. 
Then, you can change 15 to the number of cores you have or to 2 if you only have a single core computer. For 
example, if your computer is only a one core computer, then set to ‘mp.Pool(2)’. 

SOSim can run on a computer with a page file (virtual memory) of minimum 2.3 GB. Nevertheless, 
it is recommended that the memory card is of a minimum of 3.0 GB. Memory requirements of SOSim are 
determined by the fact that Python can allocate memory only up to a total of 2.3 GB, including memory 
required for all machine functions prior to running the model, when implemented on the Windows 32 bit
platform (this limitation is not expected if the model is developed in the future for the Windows 64 bit OS).
The total memory used by all processes before running SOSim is typically about 512 MB on machines not 
having many applications installed and many idle processes to run by default, except for Windows 7 and some 
editions of Windows Vista which may consume up to 1 GB when idle. Therefore, for the majority of spill 
cases to be solved with optimal resolution and including recalculations, it is estimated that a computer
would require an available memory of about 1.7 GB (that is, a difference of about 1.7 GB between the 2.3 GB
limit and the kernel memory taken up by idle processes). Indirect warning messages provided by the GUI will
guide the user in setting the best possible resolution to achieve optimal performance in terms of memory. 
 
INSTALLATION VIDEO
The installation videos named 'SOSim_mac_installation' and 'SOSim_windows_installation' are under the 'Documentation' folder. 

SOFTWARE INSTALLATION

Windows Computer:

Python and all prerequisites of SOSim are included in the OSGeo4W console, a compilation of open-source 
packages developed by the Quantum GIS project. The OSGeo4W console is distributable and therefore is 
included with the SOSim package distribution. Steps required for the installation of SOSim v2 are as follows. 
Note that additional advanced or updated installation procedures may be needed by a developer for future 
continued development of the Simulator. 

1.	Put the SOSim folder (https://data.gulfresearchinitiative.org/data/R6.x812.000:0005) in C:\Program Files\.
2.	Run the ‘execute.psi’ file by clicking right mouse and choose ‘Run with PowerShell’. The program starts to download the Python and QGIS 2.14. After the QGIS is downloaded, click ‘Next’ to finish the installation process.    
3.	Add the below environment variables to your System variables, 
‘C:\Program Files\SOSim’ to ‘Path’; 
‘C:\Python27’ to ‘Path’;
‘C:\Python27\Scripts’ to ‘Path’. 
‘C:\Program Files\QGIS 2.14\bin’ to ‘Path’;
‘C:\Program Files\QGIS 2.14\apps\qgis-ltr\bin’ to ‘Path’; 
‘C:\Program Files\QGIS 2.14\apps\grass\grass-7.2.2\lib to ‘Path’; 
‘C:\Program Files\QGIS 2.14\apps\Python27\Lib\site-packages’ to ‘PYTHONPATH’;
‘C:\Program Files\QGIS 2.14\bin’ to ‘PYTHONPATH’. 
‘C:\Python27\Lib\site-packages’ to ‘PYTHONPATH’;
‘C:\Program Files\QGIS 2.14\apps\Python27’ to ‘PYTHONPATH’;
‘C:\Program Files\QGIS 2.14\apps\Python27\lib\site-packages’ to ‘PYTHONPATH’;
‘C\Program Files\QGIS 2.14\share\gdal’ to ‘GDAL_DATA’
4.	In the terminal, under the ‘C:\Program Files\SOSim’ path type ‘pip install -r .\requirements.txt’. After running this, all required packages are automatically installed. 
NOTE: If you get an error when trying to run SOSim (e.g. an error about qgis.core), make sure to move up the variables you just created in ‘Path’ and ‘PYTHONPATH’ so they are at the top. 

Now the SOSim software is ready to run using the following steps: 
(1) type ‘execfile(‘c:\Program Files\SOSim\SOSimOPI.py’)’ in the Windows PowerShell; 
(2) or open ‘SOSimOPI.py’ in Sublime Text, and press ‘Crtl+B’ to run the code. 

Mac Computer:

1.	Download Python and QGIS 2.14. Python (>= 2.7) can be downloaded through https://www.python.org/download/releases/2.7/ 
	and QGIS 2.14 can be downloaded through http://www.kyngchaos.com/files/software/qgis/QGIS-2.14.21-1.dmg 
	and installed in the Applications folder. Install from 1 GDAL Complete.pkg to 4 Install QGIS.pkg.

2.	Put this SOSim folder (https://data.gulfresearchinitiative.org/data/R6.x812.000:0005) on your Desktop (or other directory).  

3.	Open the Terminal (which can be found in the spotlight search) and type: 

	'vim ~/.bash_profile' and then press Enter
	Then, insert the following:
	'export PYTHONPATH=/Users/(username)/Desktop/SOSim/SOSim:/Applications/Qgis.app/Contents/Resources/python'
	'export LD_LIBRARY_PATH=/Applications/Qgis.app/Contents/Resources/lib'
	'export DYLD_LIBRARY_PATH=/Applications/QGIS.app/Contents/MacOS/lib/:/Applications/QGIS.app/Contents/Frameworks/'
	'export QGIS_PREFIX_PATH=/Applications/QGIS.app/Contents/MacOS/'

	Then type ':wq' to exit. Then, still in the Terminal, type 'source ~/.bash_profile' to update the environmental variables.

Now the SOSim software is ready to run using the following steps:

(1) Open the Terminal and go to the directory of your SOSim folder. For example, if the SOSim folder is on your desktop, in the Terminal type:
    'cd Desktop/SOSim'
    Then press Enter. Now, you can type:
    'pip install -r requirements_mac.txt' to install all required packages.
After it finished, you can type:
    'python SOSimOPI_Mac.py'
    And the GUI will open.
(2) Or you can open ‘SOSimOPI_Mac.py’ in Sublime Text, and press ‘Command’ + ‘B’ to run the code.


  
---------------
Foot Note:

To change an environment variable in a Windows machine, search ‘Edit the System Environment Variable’. 
In the System Properties box, under “Advanced”, select “Environment Variables” at the bottom. System variables 
are in the lower part of the box and you only have access to then if you have administrator privileges over the machine. 
Screen the list to see of the environment variable that you need already exists; if it does, click on it and on “Edit”, 
then type a semicolon after the existing text and type the given path following, without spaces. If the environment 
variable does not exist, click on “New” and type the name in capital letters, then the given path.
----------------