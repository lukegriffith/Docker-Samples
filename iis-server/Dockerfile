# This dockerfile utilizes components licensed by their respective owners/authors.

FROM microsoft/windowsservercore

LABEL Description="IIS" Vendor="Microsoft" Version="10"

RUN powershell -Command ni -it d     -pa C:\Docker

WORKDIR "C:/Docker/"

ADD "AutoDownloader/" "AutoDownloader/"

RUN powershell -Command Add-WindowsFeature Web-Server

CMD [ "ping", "localhost", "-t" ]   