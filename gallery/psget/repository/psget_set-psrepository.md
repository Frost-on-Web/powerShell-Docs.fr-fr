---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: gallery,powershell,cmdlet,psget
title: Set-PSRepository
ms.openlocfilehash: 2e850947b67d43254ee9d1b3c1c571167435234c
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="set-psrepository"></a><span data-ttu-id="59007-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="59007-103">Set-PSRepository</span></span>

<span data-ttu-id="59007-104">Set-PSRepository définit des valeurs pour un référentiel enregistré.</span><span class="sxs-lookup"><span data-stu-id="59007-104">Set-PSRepository sets values for a registered repository.</span></span>

## <a name="description"></a><span data-ttu-id="59007-105">Description</span><span class="sxs-lookup"><span data-stu-id="59007-105">Description</span></span>

<span data-ttu-id="59007-106">L’applet de commande Set-PSRepository définit des valeurs pour un référentiel de modules enregistré.</span><span class="sxs-lookup"><span data-stu-id="59007-106">The Set-PSRepository cmdlet sets values for a registered module repository.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="59007-107">Syntaxe de l’applet de commande</span><span class="sxs-lookup"><span data-stu-id="59007-107">Cmdlet syntax</span></span>

```powershell
Get-Command -Name Set-PSRepository -Module PowerShellGet -Syntax
```
## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="59007-108">Référence de l’aide en ligne de l’applet de commande</span><span class="sxs-lookup"><span data-stu-id="59007-108">Cmdlet online help reference</span></span>

[<span data-ttu-id="59007-109">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="59007-109">Set-PSRepository</span></span>](http://go.microsoft.com/fwlink/?LinkID=517128)

## <a name="example-commands"></a><span data-ttu-id="59007-110">Exemples de commandes</span><span class="sxs-lookup"><span data-stu-id="59007-110">Example commands</span></span>

```powershell
PS C:\> Register-PSRepository -Name myRepository -SourceLocation "https://www.myget.org/F/powershellgetdemo/api/v2" -InstallationPolicy Trusted
PS C:\> Get-PSRepository
Name                      InstallationPolicy   SourceLocation
----                      ------------------   --------------
myRepository              Trusted              https://www.myget.org/F/powershellgetdemo/api/v2

# Set installation Policy for a repository
PS C:\> Set-PSRepository -Name myRepository -InstallationPolicy Untrusted
PS C:\> Get-PSRepository

Name                      InstallationPolicy   SourceLocation
----                      ------------------   --------------
myRepository              Untrusted            https://www.myget.org/F/powershellgetdemo/api/v2
```


### <a name="set-psrepository-cmdlet-with-script-sharing-support"></a><span data-ttu-id="59007-111">Applet de commande Set-PSRepository avec prise en charge du partage de script</span><span class="sxs-lookup"><span data-stu-id="59007-111">Set-PSRepository cmdlet with script sharing support</span></span>

<span data-ttu-id="59007-112">Les applets de commande Set-PSRepository permettent d’ajouter **ScriptSourceLocation** et **ScriptPublishLocation** à PSRepository.</span><span class="sxs-lookup"><span data-stu-id="59007-112">Use Set-PSRepository cmdlets to add the **ScriptSourceLocation** and **ScriptPublishLocation** to the PSRepository.</span></span>
```powershell
# Add script sharing locations to an existing PSRepository using Set-PSRepository object.
Set-PSRepository -Name MyGallery `
                 -ScriptSourceLocation https://MyGallery.com/api/v2/items/psscript/ `
                 -ScriptPublishLocation https://MyGallery.com/api/v2/package/

Get-PSRepository -Name GalleryINT | Format-List * -Force

Name : GalleryINT
SourceLocation : https://MyGallery.com/api/v2/
Trusted : True
Registered : True
InstallationPolicy : Trusted
PackageManagementProvider : NuGet
PublishLocation : https://MyGallery.com/api/v2/package/
ScriptSourceLocation : https://MyGallery.com/api/v2/items/psscript/
ScriptPublishLocation : https://MyGallery.com/api/v2/package/
ProviderOptions : {}

```
