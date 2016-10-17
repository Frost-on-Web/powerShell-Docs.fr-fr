# Save-Script

L’applet de commande Save-Script permet d’examiner le fichier de script en l’enregistrant à un emplacement spécifié.

## Description

L’applet de commande Save-Script enregistre le script spécifié.

## Syntaxe de l’applet de commande

```powershell
Get-Command -Name Save-Script -Module PowerShellGet -Syntax
```
## Référence de l’aide en ligne de l’applet de commande

[Save-Script](http://go.microsoft.com/fwlink/?LinkId=619786)

## Exemples de commandes

### Exemple 1 : Enregistrer un script à partir d’un référentiel
Cette commande enregistre la dernière version du script Fabrikam-ClientScript à partir du référentiel GalleryINT dans le dossier local C:\ScriptSharingDemo

```powershell
Save-Script -Name Fabrikam-ClientScript -Repository GalleryINT -Path C:\ScriptSharingDemo
```

### Exemple 2 : Enregistrer une version d’un script par envoi à partir de l’applet de commande Find-Script

La première commande recherche la version 1.5 de Fabrikam-ClientScript à partir du référentiel GalleryINT et l’enregistre dans le dossier C:\ScriptSharingDemo

La deuxième commande valide les métadonnées du script enregistré.

```powershell
Find-Script -Name Fabrikam-ClientScript -Repository GalleryINT -RequiredVersion 1.5 | Save-Script -Path C:\\ScriptSharingDemo
Test-ScriptFileInfo C:\\ScriptSharingDemo\\Fabrikam-ClientScript.ps1

Version Name Author Description
------- ---- ------ -----------
1.5 Fabrikam-ClientScript manikb Description for the Fabrikam-ClientScript script
```


<!--HONumber=Aug16_HO3-->


