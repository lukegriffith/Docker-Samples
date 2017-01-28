# Dockerfile

See iis-server for example of a dockerfile build. items to be copied into the container should be inside that folder.

- iis-server
-- AutDownloader (submodule to 2nd project)


# Building 
+ PS C:\Users\lukem\Documents\GitHub\Docker-Samples\iis-server> docker build -t iis .
+ Sending build context to Docker daemon 394.8 kB
+ Step 1/7 : FROM microsoft/windowsservercore
+  ---> 4d83c32ad497
+ Step 2/7 : LABEL Description "IIS" Vendor "Microsoft" Version "10"
+  ---> Using cache
+  ---> 43fb95b4f642
+ Step 3/7 : RUN powershell -Command ni -it d     -pa C:\Docker
+  ---> Using cache
+  ---> 9883a8af82fa
+ Step 4/7 : WORKDIR "C:/Docker/"
+  ---> Using cache
+  ---> f08cebd16323
+ Step 5/7 : ADD "AutoDownloader/" "AutoDownloader/"
+  ---> Using cache
+  ---> c5a6371d592d
+ Step 6/7 : RUN powershell -Command Add-WindowsFeature Web-Server
+  ---> Using cache
+  ---> a78605a6c297
+ Step 7/7 : CMD ping localhost -t
+  ---> Using cache
+  ---> 8e486df4a8a5
+ Successfully built 8e486df4a8a5


# Running
+ PS C:\Users\lukem\Documents\GitHub\Docker-Samples\iis-server> docker run iis
+ 
+ Pinging b7dfeee83fa1 [::1] with 32 bytes of data:
+ Reply from ::1: time=1ms
+ Reply from ::1: time<1ms
+ Reply from ::1: time=1ms

# Enter
+ docker exec -i -t b7dfeee83fa1 powershell.exe