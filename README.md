AirVideo Server
===============

AirVideo Docker (Ubuntu based image) for unRAID


It seems the path needs to be setup correctly in the run command and in the folder config since there is no config site to enter the path after it is up and running.

Copy the AirVideoServerLinux.properties file from github and save it.

just be sure to edit the folder= to include the folders you want, just be sure to follow the format.  For example, if you wanted to add a kids and documentary folder.  The folders path would look like

folders = Movies:/Movies, TVShows:/TVShows, Kids:/Kids, Documentary:/Documentary

Then pushed to Docker Hub for building and publishing.

CREDITS to eroz for getting this to work in unRAID