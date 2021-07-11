# ChiaMovePlots
## Why the 'ChiaMovePlots' tool could be usefull
If you are using MadMax tool to create plots, you have to know what is [right way to move plots](https://github.com/Chia-Network/chia-blockchain/wiki/Moving-plots) to final directory.
Some people see the 'Invalid Plots' error in Chia GUI in 'Plots' tab. It's happen because to copy plot takes time and GUI check the plot file before it completed to copy it.
## About 'ChiaMovePlots'
The 'ChiaMovePlots' helps to move plots in right way. Following are implemented:
* In 'ChiaMovePlots.ini' file you will find following configuration:
1) Parameter 'Move_To' define the destination drive/folder, e.g.: Move_To=Z:\
2) Parameter 'Move_From' define the sorce drive/folder (it also could be a list of folders if you have several), e.g.: Move_From=D:\,E:\,F:\
3) Parameter 'Log_FileName' define path to log file
4) Parameter 'Log_WriteToFile' define write data to log file or not
* Following will be written to log in case of 'Log_WriteToFile=YES'
1) [DATE & TIME] - D:\plot-xxxxxxx.plot (Size = 108819861083)
2) [DATE & TIME] - Move file 'plot-xxxxxxx.plot' as 'plot-xxxxxxx.plot-mv' to 'Z:\'
3) [DATE & TIME] - Rename file 'plot-xxxxxxx.plot-mv' back to 'plot-xxxxxxx.plot' inside 'Z:\'
4) [DATE & TIME] - Operation completed (Size = 108819861083)
* Script will check all predefined folder every 15 min
* Each '*.plot' plot file will moved as '*.plot-mv' to destination folder and rename it back to '*.plot' when copy is completed. Note: In case of power supply interruption during the copy - the source file will not be deleted and on next script start, it will again proceed to the same file.
* Before move plot to destination folder it will check if there enough space, if not - script will be stoped
## Precondition
The 'ChiaMovePlots' written in [AutoIt](https://www.autoitscript.com) and to use it you will have to [install](https://www.autoitscript.com/cgi-bin/getfile.pl?autoit3/autoit-v3-setup.exe) and compile by yourself.
## Installation
1) [Download](https://github.com/GregoryGum/ChiaMovePlots/blob/main/ChiaMovePlots.zip) and unzip archive
2) To create exe file, mouse right click on 'ChiaMovePlots.au3' file and select 'Compile Script' option from menu
## Actions
During script execution you will able do use following options:
* F10 - to pause script
* F9 - stop script
