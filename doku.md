## Code breakdown / Delete Folder

```Powershell
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
```

Mithilfe des Cmdlets "Get-ChildItem" wird der Inhalt des aktuellen Verzeichnisses angezeigt. Der Switch Parameter "–Recurse" sorgt dafür, dass ebenfalls der Inhalt aller Unterverzeichnisse angezeigt wird.

Der Switch Parameter –Recurse sorgt dafür, dass ebenfalls der Inhalt aller Unterverzeichnisse angezeigt wird.

Das Cmdlet "ForEach-Object" führt dieselbe Aktion für alle Objekte aus, die über die Pipeline an das Cmdlet übergeben werden. Es wird also eine Schleife durchlaufen, die nacheinander die Objekte bearbeitet. Die Aktion, die dabei durchgeführt wird, ist frei programmierbar. Es kann sich durchaus um einen ganzen Skriptblock handeln.

Die "If" Anweisung ist ganz einfach. Wenn die angegebene Bedingung erfüllt ist, dann wird der in geschweiften Klammern angegebene Anweisungsblock ausgeführt. Ist die Bedingung nicht erfüllt, wird der Anweisungsblock übersprungen.

"_$" bezieht sich auf das aktuelle Element in der Pipeline. Es kann als Alias für die automatische Variable betrachtet werden. "Lenght" bedeutet die länge/anzahl.

"FullName" ist der vollständige Name der Datei, einschliesslich Pfad und Erweiterung.

Der Parameter "-eq" bedeutet (gleich).

Mit dem Cmdlet "Write-Output" werden Informationen in der PowerShell-Konsole ausgegeben. 

Das Cmdelet "Remove-Item" löscht ein Element.

Der Switch-Parameter "–Force" erzwingt die Anzeige von versteckten oder Systemdateien.

"PsIsCointainer" beschreibt, ob es sich um einen Conntainer/Ordner handelt oder nicht.

## Code breakdown / Delete Cache

```Powershell
write-Host "Temp Ordner wird gelehrt"
```
Hier habe ich ein Satz eingefügt, damit man weiss was aussgeführt wird.

```Powershell
Set-Location “C:\Windows\Temp”
	Remove-Item * -Recurse -Force -ErrorAction SilentlyContinue
```
In der ersten Zeile hab ich den Pfad bestummen. Mit "Remove-Item" habe ich die Datein im Ordner gelösscht. 

## Vortführung & Verbesserung / Code

Man könnte ein GUI erstellen, damit es benutzerfreundlicher ist. Im GUI könnten zwei Knöpfe sein. In einem steht "Cache löschen" und im anderem "leere Ordner" löschen. Zudem könnte man den Code erweitern, indem man mehr Funktionen einbaut. Beispielsweise könnte er aussrechnen wie viel Speicher die Ordner haben und so entscheiden kann, ob man das löschen will oder nicht.

## Kenntnisse / Powershell

Ich kann mit meinem Wissen jetzt viele neue Dinge in Powershell. Den Syntax habe ich auch besser verstanden. Zudem weiss ich wo ich suchen muss wenn ich etwas nicht verstehe oder nicht weiter komme. Es hat mir auch geholfen alle Funktionen aufzuschreiben und zu erklären.

## Kenntnisse / Git Hub

Ich kenn viele Begriffe von Git Hub und verstehe wie das Konzept aufgebaut ist. Ich sehe auch den Vorteil von Git Hub und ich nütze ihn auch aus. Zudem habe ich auf meinem Portfolio in Github ein Projekt, was ich selber erstellt habe. 

## Ressourcen / zum löschen von leeren Ordner

[leeren Ordner Tutorial](https://www.linetwork.de/ordner-powershell-erstellen-loeschen/)

## Ressourcen / zum löschen von Caches

[Caches löschen](https://www.geekrar.com/how-to-clear-all-cache-in-windows-10/)