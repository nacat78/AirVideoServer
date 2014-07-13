AirVideo Server
===============

AirVideo Server Docker (Ubuntu based image) for unRAID

It seems the path needs to be setup correctly in the run command and in the folder config since there is no config site to enter the path after it is up and running.

Copy the AirVideoServerLinux.properties file from github and save it.

just be sure to edit the folder= to include the folders you want, just be sure to follow the format.  For example, if you wanted to add a kids and documentary folder.  The folders path would look like

AirVideoServerLinux.properties Example:
```
folders = Movies:/Movies, TV Shows:/TV Shows, Kids:/Kids, Documentaries:/Documentaries
```
Fork into your github repo then save over the AirvideoServerLinux.properties file

Then pushed to Docker Hub for building and publishing.

Using gfjardim's Extended Docker Plugin - you can edit this XML for your setup to match properties file and save in /boot/config/plugins/Docker folder as my-AirVideoServer.xml

Docker Plugin XML to match above properties file
```
<?xml version="1.0" encoding="utf-8"?>
<Container>
  <Name>AirVideo</Name>
  <Repository>nacat78/airvideo:latest</Repository>
  <BindTime>true</BindTime>
  <Privileged>false</Privileged>
  <Environment>
    <Variable>
      <Name></Name>
      <Value></Value>
    </Variable>
  </Environment>
  <Networking>
    <Mode>bridge</Mode>
    <Publish>
      <Port>
        <HostPort></HostPort>
        <ContainerPort></ContainerPort>
        <Protocol>tcp</Protocol>
      </Port>
      <Port>
        <HostPort>45631</HostPort>
        <ContainerPort>45631</ContainerPort>
        <Protocol>tcp</Protocol>
      </Port>
    </Publish>
  </Networking>
  <Data>
    <Volume>
      <HostDir>/mnt/user/Movies/</HostDir>
      <ContainerDir>/Movies</ContainerDir>
      <Mode>ro</Mode>
    </Volume>
    <Volume>
      <HostDir>/mnt/user/TV Shows/</HostDir>
      <ContainerDir>/TV Shows</ContainerDir>
      <Mode>ro</Mode>
    </Volume>
    <Volume>
      <HostDir>/mnt/user/Kids/</HostDir>
      <ContainerDir>/Kids</ContainerDir>
      <Mode>ro</Mode>
    </Volume>
    <Volume>
      <HostDir>/mnt/user/Documentaries/</HostDir>
      <ContainerDir>/Documentaries</ContainerDir>
      <Mode>ro</Mode>
    </Volume>
  </Data>
</Container>

```
Then Add and Enjoy...

There are a couple of Devs working on an easier way, but until then - this is working for my configuration.

CREDITS to eroz for getting this to work in unRAID

