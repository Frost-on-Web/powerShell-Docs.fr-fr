---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: gallery,powershell,cmdlet,psget
title: Get-InstalledModule
ms.openlocfilehash: 6f485d04503ea6d9a51a68ae7ec3d0dc2e6facab
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="get-installedmodule"></a><span data-ttu-id="5309f-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="5309f-103">Get-InstalledModule</span></span>

<span data-ttu-id="5309f-104">Obtient les modules installés sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5309f-104">Gets installed modules on a computer.</span></span>

## <a name="description"></a><span data-ttu-id="5309f-105">Description</span><span class="sxs-lookup"><span data-stu-id="5309f-105">Description</span></span>

<span data-ttu-id="5309f-106">L’applet de commande Get-InstalledModule obtient les modules PowerShell qui ont été installés sur un ordinateur à l’aide de l’applet de commande Install-Module.</span><span class="sxs-lookup"><span data-stu-id="5309f-106">The Get-InstalledModule cmdlet gets installed PowerShell modules on a computer which were installed using Install-Module cmdlet.</span></span>

<span data-ttu-id="5309f-107">Pour chaque module installé, Get-InstalledModule retourne un objet PSRepositoryItemInfo qui peut éventuellement être transmis à Uninstall-Module pour désinstaller les modules installés.</span><span class="sxs-lookup"><span data-stu-id="5309f-107">For each installed module, Get-InstalledModule returns a PSRepositoryItemInfo object which can optionally be piped to Uninstall-Module for uninstalling the installed modules.</span></span>

- <span data-ttu-id="5309f-108">Get-InstalledModule peut filtrer les modules installés selon le nom ou les paramètres de version.</span><span class="sxs-lookup"><span data-stu-id="5309f-108">Get-InstalledModule can filter installed modules based on name, version parameters.</span></span>
- <span data-ttu-id="5309f-109">Get-InstalledModule permet de filtrer avec des paramètres de version : MinimumVersion, MaximumVersion, RequiredVersion, AllVersions.</span><span class="sxs-lookup"><span data-stu-id="5309f-109">Get-InstalledModule can filter with version parameters: MinimumVersion, MaximumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="5309f-110">Ces paramètres sont mutuellement exclusifs, sauf MinmimumVersion et MaximumVersion.</span><span class="sxs-lookup"><span data-stu-id="5309f-110">These parameters are mutually exclusive, except MinmimumVersion and MaximumVersion.</span></span>
  - <span data-ttu-id="5309f-111">Ces paramètres de version sont autorisés uniquement avec le nom de module unique sans les caractères génériques.</span><span class="sxs-lookup"><span data-stu-id="5309f-111">These version parameters are allowed only with the single module name without any wildcards.</span></span>
  - <span data-ttu-id="5309f-112">Si le paramètre RequiredVersion n’est pas spécifié, Get-InstalledModule retourne la dernière version du module installé qui est supérieure ou égale à la version minimale spécifiée ou la dernière version du module si aucune version minimale n’est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5309f-112">If the RequiredVersion parameter is not specified, Get-InstalledModule returns the latest version of the installed module that is equal to or greater than the minimum version specified or the latest version of the module if no minimum version is specified.</span></span> 
  - <span data-ttu-id="5309f-113">Si le paramètre RequiredVersion est spécifié, Get-InstalledModule retourne uniquement la version du module installé qui correspond exactement à la version spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5309f-113">If the RequiredVersion parameter is specified, Get-InstalledModule only returns the version of installed module that exactly matches the specified version.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="5309f-114">Syntaxe de l’applet de commande</span><span class="sxs-lookup"><span data-stu-id="5309f-114">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Get-InstalledModule -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="5309f-115">Référence de l’aide en ligne de l’applet de commande</span><span class="sxs-lookup"><span data-stu-id="5309f-115">Cmdlet online help reference</span></span>

[<span data-ttu-id="5309f-116">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="5309f-116">Get-InstalledModule</span></span>](http://go.microsoft.com/fwlink/?LinkId=526863)

## <a name="example-commands"></a><span data-ttu-id="5309f-117">Exemples de commandes</span><span class="sxs-lookup"><span data-stu-id="5309f-117">Example commands</span></span>

```powershell

# Get all modules installed using PowerShellGet cmdlets
Get-InstalledModule

# Get a specific installed module
Get-InstalledModule DJoin

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0        DJoin                               PSGallery            This is a PowerShell frontend to the DJOIN.exe c...

# Get installed module with wildcards
Get-InstalledModule -Name AzureRM*

# Get all versions of an installed module
Get-InstalledModule -Name AzureRM.Automation -AllVersions

# Get installed module with MinimumVersion
Get-InstalledModule -Name AzureRM.Automation -MinimumVersion 1.0.0

# Get installed module with MaximumVersion
Get-InstalledModule -Name AzureRM.Automation -MaximumVersion 1.0.8

# Get installed module with version range
Get-InstalledModule -Name AzureRM.Automation -MinimumVersion 1.0.0 -MaximumVersion 1.0.8

# Get installed module with RequiredVersion
Get-InstalledScript -Name AzureRM.Automation -RequiredVersion 1.0.3

# Properties of Get-InstalledModule returned object
Get-InstalledModule DJoin | Format-List * -Force

Name                       : DJoin
Version                    : 1.0
Type                       : Module
Description                : This is a PowerShell frontend to the DJOIN.exe command which provides better
                             discoverability and usability.
Author                     : Jeffrey Snover
CompanyName                : jsnover
Copyright                  : (C) Microsoft Corporation. All rights reserved.
PublishedDate              : 2/15/2016 7:12:37 PM
InstalledDate              : 4/5/2016 4:13:39 PM
UpdatedDate                :
LicenseUri                 :
ProjectUri                 :
IconUri                    :
Tags                       : {Nano, PSModule}
Includes                   : {Function, RoleCapability, Command, DscResource...}
PowerShellGetFormatVersion :
ReleaseNotes               :
Dependencies               : {}
RepositorySourceLocation   : https://www.powershellgallery.com/api/v2/
Repository                 : PSGallery
PackageManagementProvider  : NuGet
AdditionalMetadata         : {description, installeddate, tags, PackageManagementProvider...}
InstalledLocation          : C:\Program Files\WindowsPowerShell\Modules\DJoin\1.0

```



## <a name="installeddate-and-updateddate-properties-in-psgetrepositoryiteminfo-object"></a><span data-ttu-id="5309f-118">Propriétés InstalledDate et UpdatedDate dans l’objet PSGetRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="5309f-118">InstalledDate and UpdatedDate properties in PSGetRepositoryItemInfo object</span></span>

    During the install operation:
        InstalledDate: current DateTime (Get-Date) value
        UpdatedDate: null

    During the Update operation:
        InstalledDate: InstalledDate from the previous installation otherwise current DateTime (Get-Date) value
        UpdatedDate: current DateTime (Get-Date) value

```powershell
Install-Module -Name ContosoServer -RequiredVersion 1.0 -Repository INT
Get-InstalledModule -Name ContosoServer | Format-Table Name, InstalledDate, UpdatedDate

Name          InstalledDate         UpdatedDate
----          -------------         -----------
ContosoServer 2/29/2016 11:59:14 AM


\Update-Module -Name ContosoServer
Get-InstalledModule -Name ContosoServer | Format-Table Name, InstalledDate, UpdatedDate

Name          InstalledDate         UpdatedDate
----          -------------         -----------
ContosoServer 2/29/2016 11:59:14 AM 2/29/2016 12:00:15 PM
```
