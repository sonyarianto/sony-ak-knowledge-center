Suppose you have a text file contains list of files and you want to upload it to server.

The scenario is upload from Windows environment to Linux server.

First make sure WinSCP already on your system path.

This is the batch script.
```
@echo off
set SESSION=sftp://your_username@ip_address:port_number/
set REMOTE_PATH=/your/target/path/on/server/
 
setlocal enabledelayedexpansion

echo open %SESSION% >> script.tmp
 
rem Generate "put" command for each line in list file
for /F %%i in (your_text_file_that_contains_list_of_files_to_be_uploaded) do (
	set local_file=%%i
	set local_file_win_format=!local_file:/=\!
	echo put "!local_file_win_format!" "%REMOTE_PATH%" >> script.tmp
)
 
echo exit >> script.tmp
 
winscp.com /privatekey=c:\your_identity_with_ppk_format.ppk /script=script.tmp
set RESULT=%ERRORLEVEL%
 
del script.tmp
 
rem Propagating WinSCP exit code
exit /b %RESULT%
```
