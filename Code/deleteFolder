# Path 
Get-Childitem "C:\Users\athes\Desktop\Demo” -Recurse | ForEach-Object {
    # Deleting Files
    if ($_.Length -eq 0) {
        Write-Output "Removing Empty Files $(S_.FullNname)”
        $_.FullName | Remove-Item -Force
    }
    # Deleting Folder
    if ($_.PsIsContainer -eq $true) {
        if ((Get-Childitem $_.FullName) -eq $null) {
            Write-Output "Removing Empty Folder $($_.FullName)”
            $_.FullName | Remove-Item -Force 
        }
    } 
}