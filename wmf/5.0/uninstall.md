---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: wmf,powershell,setup
ms.openlocfilehash: 3392db954c22030bb64ae5093619d23952e1fcdb
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="b8177-102">Instructions de désinstallation</span><span class="sxs-lookup"><span data-stu-id="b8177-102">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="b8177-103">Utilisation de l’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="b8177-103">Using Command Prompt</span></span>
1.  <span data-ttu-id="b8177-104">Ouvrez une **invite de commandes.**</span><span class="sxs-lookup"><span data-stu-id="b8177-104">Open **Command Prompt.**</span></span>
2.  <span data-ttu-id="b8177-105">Exécutez le [Lanceur autonome Windows Update](https://support.microsoft.com/en-us/kb/934307) comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="b8177-105">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="b8177-106">Sur Windows Server 2012 R2 et Windows 8.1 :</span><span class="sxs-lookup"><span data-stu-id="b8177-106">On Windows Server 2012 R2 and Windows 8.1:</span></span>
```powershell
wusa /uninstall /kb:3134758
```
<span data-ttu-id="b8177-107">Sur Windows Server 2012 :</span><span class="sxs-lookup"><span data-stu-id="b8177-107">On Windows Server 2012:</span></span>
```powershell
wusa /uninstall /kb:3134759
```
<span data-ttu-id="b8177-108">Sur Windows Server 2008 R2 SP1 et Windows 7 SP1 :</span><span class="sxs-lookup"><span data-stu-id="b8177-108">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>
```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="b8177-109">Utilisation du Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="b8177-109">Using Control Panel</span></span>
1.  <span data-ttu-id="b8177-110">Ouvrez le **Panneau de configuration.**</span><span class="sxs-lookup"><span data-stu-id="b8177-110">Open **Control Panel.**</span></span>
2.  <span data-ttu-id="b8177-111">Ouvrez **Programmes**, puis **Désinstaller un programme.**</span><span class="sxs-lookup"><span data-stu-id="b8177-111">Open **Programs**, then open **Uninstall a program.**</span></span>
3.  <span data-ttu-id="b8177-112">Cliquez sur **Afficher les mises à jour installées.**</span><span class="sxs-lookup"><span data-stu-id="b8177-112">Click **View installed updates.**</span></span>
4.  <span data-ttu-id="b8177-113">Sélectionnez **Windows Management Framework 5.0** dans la liste des mises à jour installées.</span><span class="sxs-lookup"><span data-stu-id="b8177-113">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="b8177-114">Cela correspond à *KB3134758*, *KB3134759* ou *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="b8177-114">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="b8177-115">Cliquez sur **Désinstaller.**</span><span class="sxs-lookup"><span data-stu-id="b8177-115">Click **Uninstall.**</span></span>
