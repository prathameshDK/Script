NET STOP Tomcat8
SET location=G:\Tomcat\apache-tomcat-8.5.8-windows-x64\apache-tomcat-8.5.8\
SET srcfile=G:\War\

cd %location%webapps
forfiles /M *.war /C "cmd /c del @file /q"

echo f | xcopy /f /y %srcfile%*.war %location%webapps	
NET START Tomcat8
