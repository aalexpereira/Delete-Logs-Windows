# Delete-Logs-Windows
Auto Delete Logs Windows

## commands:

```bash

erase "%TEMP%\*.*" /f /s /q
for /D %%i in ("%TEMP%\*") do RD /S /Q "%%i"

erase "%TMP%\*.*" /f /s /q
for /D %%i in ("%TMP%\*") do RD /S /Q "%%i"

erase "%ALLUSERSPROFILE%\TEMP\*.*" /f /s /q
for /D %%i in ("%ALLUSERSPROFILE%\TEMP\*") do RD /S /Q "%%i"

erase "%SystemRoot%\TEMP\*.*" /f /s /q
for /D %%i in ("%SystemRoot%\TEMP\*") do RD /S /Q "%%i"


RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 8
erase "%LOCALAPPDATA%\Microsoft\Windows\Tempor~1\*.*" /f /s /q
for /D %%i in ("%LOCALAPPDATA%\Microsoft\Windows\Tempor~1\*") do RD /S /Q "%%i"

erase "%LOCALAPPDATA%\Google\Chrome\User Data\*.*" /f /s /q
for /D %%i in ("%LOCALAPPDATA%\Google\Chrome\User Data\*") do RD /S /Q "%%i"


erase "%LOCALAPPDATA%\Mozilla\Firefox\Profiles\*.*" /f /s /q
for /D %%i in ("%LOCALAPPDATA%\Mozilla\Firefox\Profiles\*") do RD /S /Q "%%i"

RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 255
RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 1
RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 2
RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 8
RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 16
RunDll32.exe InetCpl.cpl,ClearMyTracksByProcess 32

cmd /c for /F “tokens=*” %1 in ('wevtutil.exe el') DO wevtutil.exe cl “%1”

ipconfig /flushdns

cipher /w:c

```
