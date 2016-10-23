---
title: Objet ISESnippetCollection
ms.date: 2016-05-11
keywords: powershell,applet de commande
description: 
ms.topic: article
author: jpjofre
manager: dongill
ms.prod: powershell
ms.assetid: ae974955-4282-4cbc-8c42-0fff1904ef32
translationtype: Human Translation
ms.sourcegitcommit: 6c666e2e23cb74818e37293410dafc9033057733
ms.openlocfilehash: 410cd4503883ea2cc02936044d7357b9cb029274

---

# Objet ISESnippetCollection
  L’objet **ISESnippetCollection** est une collection d’objets **ISESnippet**. La collection de fichiers qui est associée à un objet **PowerShellTab** est un membre de cette classe. La collection **$psISE.CurrentPowerShellTab.Files** en est un exemple.

## Méthodes

### Load\( FilePathName \)
  Prise en charge dans Windows PowerShell ISE 3.0 et versions ultérieures, ne figure pas dans les versions antérieures. 

 Charge un fichier .snippets.ps1xml qui contient des extraits de code défini par l’utilisateur. L’applet de commande New-IseSnippet est le moyen le plus simple de créer des extraits de code, car elle les stocke automatiquement dans votre dossier de profil pour qu’ils se chargent à chaque démarrage de Windows PowerShell ISE.

 **FilePathName** : chaîne Chemin et nom d’un fichier .snippets.ps1xml qui contient les définitions des extraits de code.

```
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) “Snippets\MySnips.snippets.ps1xml” $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)

```

## Voir aussi
- [Objet ISESnippet](The-ISESnippetObject.md) 
- [Modèle objet de script Windows PowerShell ISE](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [Référence de modèle objet Windows PowerShell ISE](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [Hiérarchie du modèle objet ISE](The-ISE-Object-Model-Hierarchy.md)

  



<!--HONumber=Oct16_HO3-->


