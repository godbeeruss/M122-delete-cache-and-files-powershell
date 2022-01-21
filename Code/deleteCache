# Deleting Temp files

write-Host "Temp Ordner wird gelehrt"
Set-Location “C:\Windows\Temp”
Remove-Item * -Recurse -Force -ErrorAction SilentlyContinue

Set-Location “C:\Windows\Prefetch”
Remove-Item * -Recurse -Force -ErrorAction SilentlyContinue

Set-Location “C:\Documents and Settings”
Remove-Item “.\*\Local Settings\temp\*” -Recurse -Force -ErrorAction SilentlyContinue

Set-Location “C:\Users”
Remove-Item “.\*\Appdata\Local\Temp\*” -Recurse -Force -ErrorAction SilentlyContinue