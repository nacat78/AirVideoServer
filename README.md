AirVideo Server
===============

AirVideo Server Docker (Ubuntu based image) for unRAID

It seems the path needs to be setup correctly in the run command and in the folder config since there is no config site to enter the path after it is up and running.

Copy the AirVideoServerLinux.properties file from github and save it.

just be sure to edit the folder= to include the folders you want, just be sure to follow the format.  For example, if you wanted to add a kids and documentary folder.  The folders path would look like

AirVideoServerLinux.properties 
--For Example: folders = Movies:/Movies, TV Shows:/TV Shows, Kids:/Kids, Documentaries:/Documenties

Fork into your github repo then save over the AirvideoServerLinux.properties file

Then pushed to Docker Hub for building and publishing.

Using gfjardim's Extended Docker Plugin - you can edit this XML for your setup to match properties file

Docker Plugin XML to match above properties file
--Example:

Then pushed to Docker Hub for building and publishing.

There are a couple of Devs working on an easier way, but until then - this is working for my configuration.

CREDITS to eroz for getting this to work in unRAID

