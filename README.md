# bootstrap files are for use with Banjo. They are complied into an banjoex.exe file to be run
for use with banjo
#haskell code written in haskell with help neil mitchell
#download isntall banjo
#download and install java

#create a folder called Emily directly on your C drive with the address C:\Emily
#put banjo.jar in that folder

#create a new folder from which you will run your analyses. e.g. BanjoWork
#put banjo.jar and banjoex.exe in this folder

#Running an analyse
#refer to the How to BNI powerpoint present for details/concepts
#to run banjoex you will need a data file consisting of discretized data and a settings file
#the settings file will need adjusting for each dataset
#key settings to change are the dataset, observationsfiles, reportfiles and fileNameForTopGraph to the file name of your dataset
#other key setting is the variableCount. This number needs to match the banjoex input and the number of variables (nodes) in your data
#the length (number of variableNames) needs to be the same as the variable count.
#once you have updated the settings file you are ready to run banjoex

#running banjoex
#open the command prompt and change directories to your working one (eg. BanjoWork)
#run the below command
#1st banjoex is the programme you are running
#2nd argument is the name of the datafile
#3rd argument is the VariableCount
#4th argument is the amount of bootstrappoing
#5th argument is the number of reptitions.

banjoex noGroup.txt 14 bootstrap=95% repeat=10 

#if you don't have a .dot file viewer set up then it will finish by outputting:

-----------------------------------------------------------------------------
(Final Checkpoint) A final check revealed the following issues that were encountered during Banjo's execution:
-----------------------------------------------------------------------------
('dot' execution) The attempted execution of 'dot' to create the graphics file 'D:\Dropbox\methods\BanjoStuff\results\noGroup_14\noGroup_38\graph_noGroup_4.png' did not succeed. No output has been produced.

banjo data=noGroup.txt maxruns=14 bootstrap=38 maxparents=3 #5
cd C:\Emily\banjo && java -Xmx200m -jar banjo.jar settingsFile=D:\Dropbox\methods\BanjoStuff\settings.txt maxProposedNetworks=14000000 inputDirectory=D:\Dropbox\methods\BanjoStuff\results\noGroup_14\noGroup_38\samples observationsFile=noGroup_5.txt outputDirectory=D:\Dropbox\methods\BanjoStuff\results\noGroup_14\noGroup_38 reportFile=report_noGroup_5.txt fileNameForTopGraph=graph_noGroup_5 maxParentCount=3 maxParentCountForRestart=3
The system cannot find the path specified.
banjoex: Banjo execution failed
CallStack (from HasCallStack):
  error, called at banjoex1.hs:176:9 in main:Main
  
 This error message doesn't impact the outputs so can be ignored.
 
#banjoex outputs two files.
#A fileName.txt_combine.txt is the key results file
#fileName.txt_combine.txt contains a list of edges, the percentage they are found in the repetitions and the Interaction Strength of the edge
#For how to process this file see the How to BNI slide.
#A fileName.txt_combine.dot file which is the results formatted to be viewed as network as a dot file with different colours for different frequencies of edges found by the repetition. 





