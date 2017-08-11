---
ms.date: 2017-06-05
keywords: powershell,applet de commande
title: Gestion des services
ms.assetid: 7a410e4d-514b-4813-ba0c-0d8cef88df31
ms.openlocfilehash: 9fd6c8bcfecc99756188409629ddf94b880aab91
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2017
---
# <a name="managing-services"></a><span data-ttu-id="8b757-103">Gestion des services</span><span class="sxs-lookup"><span data-stu-id="8b757-103">Managing Services</span></span>
<span data-ttu-id="8b757-104">Il existe huit principales applets de commande Service, conçues pour un vaste éventail de tâches de service.</span><span class="sxs-lookup"><span data-stu-id="8b757-104">There are eight core Service cmdlets, designed for a wide range of service tasks .</span></span> <span data-ttu-id="8b757-105">Nous examinons ici uniquement le listage et la modification de l’état en cours d’exécution des services, mais vous pouvez obtenir une liste des applets de commande Service à l’aide de l’applet de commande **Get-Help \&#42;-Service**. Vous pouvez également trouver des informations sur chaque applet de commande Service à l’aide de la commande **Get-Help<NomAppletDeCommande>**, par exemple, **Get-Help New-Service**.</span><span class="sxs-lookup"><span data-stu-id="8b757-105">We will look only at listing and changing running state for services, but you can get a list Service cmdlets by using **Get-Help \&#42;-Service**, and you can find information about each Service cmdlet by using **Get-Help<Cmdlet-Name>**, such as **Get-Help New-Service**.</span></span>

## <a name="getting-services"></a><span data-ttu-id="8b757-106">Obtention de services</span><span class="sxs-lookup"><span data-stu-id="8b757-106">Getting Services</span></span>
<span data-ttu-id="8b757-107">Vous pouvez obtenir les services sur un ordinateur local ou distant à l’aide de l’applet de commande **Get-Service**.</span><span class="sxs-lookup"><span data-stu-id="8b757-107">You can get the services on a local or remote computer by using the **Get-Service** cmdlet.</span></span> <span data-ttu-id="8b757-108">Comme avec la commande **Get-Process**, l’utilisation de la commande **Get-Service** sans paramètre a pour effet de retourner tous les services.</span><span class="sxs-lookup"><span data-stu-id="8b757-108">As with **Get-Process**, using the **Get-Service** command without parameters returns all services.</span></span> <span data-ttu-id="8b757-109">Vous pouvez filtrer par nom, même en utilisant un astérisque comme caractère générique :</span><span class="sxs-lookup"><span data-stu-id="8b757-109">You can filter by name, even using an asterisk as a wildcard:</span></span>

```
PS> Get-Service -Name se*
Status   Name               DisplayName
------   ----               -----------
Running  seclogon           Secondary Logon
Running  SENS               System Event Notification
Stopped  ServiceLayer       ServiceLayer
```

<span data-ttu-id="8b757-110">Comme il n’est pas toujours évident d’identifier le nom réel d’un service, il se peut que vous deviez rechercher des services par nom d’affichage.</span><span class="sxs-lookup"><span data-stu-id="8b757-110">Because it is not always obvious what the real name for the service is, you may find you need to find services by display name.</span></span> <span data-ttu-id="8b757-111">À cette fin, vous pouvez utiliser un nom spécifique, des caractères génériques ou une liste de noms d’affichage :</span><span class="sxs-lookup"><span data-stu-id="8b757-111">You can do this by specific name, using wildcards, or using a list of display names:</span></span>

```
PS> Get-Service -DisplayName se*
Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Running  SamSs              Security Accounts Manager
Running  seclogon           Secondary Logon
Stopped  ServiceLayer       ServiceLayer
Running  wscsvc             Security Center
PS> Get-Service -DisplayName ServiceLayer,Server
Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Stopped  ServiceLayer       ServiceLayer
```

<span data-ttu-id="8b757-112">Vous pouvez utiliser le paramètre ComputerName de l’applet de commande Get-Service pour obtenir les services sur des ordinateurs distants.</span><span class="sxs-lookup"><span data-stu-id="8b757-112">You can use the ComputerName parameter of the Get-Service cmdlet to get the services on remote computers.</span></span> <span data-ttu-id="8b757-113">Le paramètre ComputerName acceptant plusieurs valeurs et caractères génériques, vous pouvez obtenir les services sur plusieurs ordinateurs à l’aide d’une seule commande.</span><span class="sxs-lookup"><span data-stu-id="8b757-113">The ComputerName parameter accepts multiple values and wildcard characters, so you can get the services on multiple computers with a single command.</span></span> <span data-ttu-id="8b757-114">Par exemple, la commande suivante obtient les services sur l’ordinateur distant Server01.</span><span class="sxs-lookup"><span data-stu-id="8b757-114">For example, the following command gets the services on the Server01 remote computer.</span></span>

```
Get-Service -ComputerName Server01
```

## <a name="getting-required-and-dependent-services"></a><span data-ttu-id="8b757-115">Obtention de services requis et dépendants</span><span class="sxs-lookup"><span data-stu-id="8b757-115">Getting Required and Dependent Services</span></span>
<span data-ttu-id="8b757-116">L’applet de commande Get-Service dispose de deux paramètres très utiles dans l’administration des services.</span><span class="sxs-lookup"><span data-stu-id="8b757-116">The Get-Service cmdlet has two parameters that are very useful in service administration.</span></span> <span data-ttu-id="8b757-117">Le paramètre DependentServices obtient les services dépendant de ce service.</span><span class="sxs-lookup"><span data-stu-id="8b757-117">The DependentServices parameter gets services that depend on the service.</span></span> <span data-ttu-id="8b757-118">Le paramètre RequiredServices obtient les services dont ce service dépend.</span><span class="sxs-lookup"><span data-stu-id="8b757-118">The RequiredServices parameter gets services upon which this service depends.</span></span>

<span data-ttu-id="8b757-119">Ces paramètres affichent simplement les valeurs des propriétés DependentServices et ServicesDependedOn (alias=RequiredServices) de l’objet System.ServiceProcess.ServiceController que l’applet de commande Get-Service retourne, mais ils simplifient les commandes et facilitent sensiblement l’obtention de ces informations.</span><span class="sxs-lookup"><span data-stu-id="8b757-119">These parameters just display the values of the DependentServices and ServicesDependedOn (alias=RequiredServices) properties of the System.ServiceProcess.ServiceController object that Get-Service returns, but they simplify commands and make getting this information much simpler.</span></span>

<span data-ttu-id="8b757-120">La commande suivante obtient les services que le service LanmanWorkstation requiert.</span><span class="sxs-lookup"><span data-stu-id="8b757-120">The following command gets the services that the LanmanWorkstation service requires.</span></span>

```
PS> Get-Service -Name LanmanWorkstation -RequiredServices
Status   Name               DisplayName
------   ----               -----------
Running  MRxSmb20           SMB 2.0 MiniRedirector
Running  bowser             Bowser
Running  MRxSmb10           SMB 1.x MiniRedirector
Running  NSI                Network Store Interface Service
```

<span data-ttu-id="8b757-121">La commande suivante obtient les services qui requièrent le service LanmanWorkstation.</span><span class="sxs-lookup"><span data-stu-id="8b757-121">The following command gets the services that require the LanmanWorkstation service.</span></span>

```
PS> Get-Service -Name LanmanWorkstation -DependentServices
Status   Name               DisplayName
------   ----               -----------
Running  SessionEnv         Terminal Services Configuration
Running  Netlogon           Netlogon
Stopped  Browser            Computer Browser
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="8b757-122">Vous pouvez même obtenir tous les services qui ont des dépendances.</span><span class="sxs-lookup"><span data-stu-id="8b757-122">You can even get all services that have dependencies.</span></span> <span data-ttu-id="8b757-123">C’est précisément ce que fait la commande suivante. Ensuite, elle utilise l’applet de commande Format-Table pour afficher les propriétés State, Name, RequiredServices et DependentServices des services sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8b757-123">The following command does just that, and then it uses the Format-Table cmdlet to display the Status, Name, RequiredServices and DependentServices properties of the services on the computer.</span></span>

```
Get-Service -Name * | where {$_.RequiredServices -or $_.DependentServices} | Format-Table -Property Status, Name, RequiredServices, DependentServices -auto
```

## <a name="stopping-starting-suspending-and-restarting-services"></a><span data-ttu-id="8b757-124">Arrêt, démarrage, interruption et redémarrage de services</span><span class="sxs-lookup"><span data-stu-id="8b757-124">Stopping, Starting, Suspending, and Restarting Services</span></span>
<span data-ttu-id="8b757-125">Les applets de commande Service ont toutes la même forme générale.</span><span class="sxs-lookup"><span data-stu-id="8b757-125">The Service cmdlets all have the same general form.</span></span> <span data-ttu-id="8b757-126">Les services peuvent être spécifiés par un nom commun ou nom d’affichage, et prennent des listes et des caractères génériques pour valeurs.</span><span class="sxs-lookup"><span data-stu-id="8b757-126">Services can be specified by common name or display name, and take lists and wildcards as values.</span></span> <span data-ttu-id="8b757-127">Pour arrêter le spouleur d’impression, utilisez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8b757-127">To stop the print spooler, use:</span></span>

```
Stop-Service -Name spooler
```

<span data-ttu-id="8b757-128">Pour démarrer le spouleur d’impression suite à un arrêt, utilisez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8b757-128">To start the print spooler after it is stopped, use:</span></span>

```
Start-Service -Name spooler
```

<span data-ttu-id="8b757-129">Pour interrompre le spouleur d’impression, utilisez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8b757-129">To suspend the print spooler, use:</span></span>

```
Suspend-Service -Name spooler
```

<span data-ttu-id="8b757-130">L’applet de commande **Restart-Service** fonctionne de la même manière que les autres applets de commande Service, mais nous allons présenter quelques exemples plus complexes pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="8b757-130">The **Restart-Service** cmdlet works in the same manner as the other Service cmdlets, but we will show some more complex examples for it.</span></span> <span data-ttu-id="8b757-131">Dans le cas d’utilisation le plus simple, vous spécifiez le nom du service :</span><span class="sxs-lookup"><span data-stu-id="8b757-131">In the simplest use, you specify the name of the service:</span></span>

```
PS> Restart-Service -Name spooler
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
PS>
```

<span data-ttu-id="8b757-132">Vous pouvez remarquer que vous obtenez un message d’avertissement répété sur le démarrage du spouleur d’impression.</span><span class="sxs-lookup"><span data-stu-id="8b757-132">You will notice that you get a repeated warning message about the Print Spooler starting up.</span></span> <span data-ttu-id="8b757-133">Lorsque vous effectuez une opération de service qui prend un certain temps, Windows PowerShell vous informe qu’il tente toujours d’effectuer la tâche.</span><span class="sxs-lookup"><span data-stu-id="8b757-133">When you perform a service operation that takes some time, Windows PowerShell will notify you that it is still attempting to perform the task.</span></span>

<span data-ttu-id="8b757-134">Si vous souhaitez redémarrer plusieurs services, vous pouvez obtenir la liste des services, filtrer ceux-ci, puis effectuer le redémarrage :</span><span class="sxs-lookup"><span data-stu-id="8b757-134">If you want to restart multiple services, you can get a list of services, filter them, and then perform the restart:</span></span>

```
PS> Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service
WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
Restart-Service : Cannot stop service 'Logical Disk Manager (dmserver)' because
 it has dependent services. It can only be stopped if the Force flag is set.
At line:1 char:57
+ Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service <<<<
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
```

<span data-ttu-id="8b757-135">Ces applets de commande Service ne dispose pas de paramètre ComputerName, mais vous pouvez les exécuter sur un ordinateur distant à l’aide de l’applet de commande Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="8b757-135">These Service cmdlets do not have a ComputerName parameter, but you can run them on a remote computer by using the Invoke-Command cmdlet.</span></span> <span data-ttu-id="8b757-136">Par exemple, la commande suivante redémarre le service Spouleur sur l’ordinateur distant Server01.</span><span class="sxs-lookup"><span data-stu-id="8b757-136">For example, the following command restarts the Spooler service on the Server01 remote computer.</span></span>

```
Invoke-Command -ComputerName Server01 {Restart-Service Spooler}
```

## <a name="setting-service-properties"></a><span data-ttu-id="8b757-137">Définition des propriétés d’un service</span><span class="sxs-lookup"><span data-stu-id="8b757-137">Setting Service Properties</span></span>
<span data-ttu-id="8b757-138">L’applet de commande de Set-Service modifie les propriétés d’un service sur un ordinateur local ou distant.</span><span class="sxs-lookup"><span data-stu-id="8b757-138">The Set-Service cmdlet changes the properties of a service on a local or remote computer.</span></span> <span data-ttu-id="8b757-139">Étant donné que l’état d’un service est une propriété, vous pouvez utiliser cette applet de commande pour démarrer, arrêter et suspendre un service.</span><span class="sxs-lookup"><span data-stu-id="8b757-139">Because the service status is a property, you can use this cmdlet to start, stop, and suspend a service.</span></span> <span data-ttu-id="8b757-140">L’applet de commande Set-Service dispose également d’un paramètre StartupType qui permet de modifier le type de démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="8b757-140">The Set-Service cmdlet also has a StartupType parameter that lets you change the service startup type.</span></span>

<span data-ttu-id="8b757-141">Pour utiliser l’applet de commande Set-Service sur Windows Vista et des versions ultérieures de Windows, ouvrez Windows PowerShell avec l’option Exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="8b757-141">To use Set-Service on Windows Vista and later versions of Windows, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="8b757-142">Pour plus d’informations, voir [Set-Service [m2]](https://technet.microsoft.com/en-us/library/b71e29ed-372b-4e32-a4b7-5eb6216e56c3)</span><span class="sxs-lookup"><span data-stu-id="8b757-142">For more information, see [Set-Service [m2]](https://technet.microsoft.com/en-us/library/b71e29ed-372b-4e32-a4b7-5eb6216e56c3)</span></span>

## <a name="see-also"></a><span data-ttu-id="8b757-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b757-143">See Also</span></span>
- [<span data-ttu-id="8b757-144">Get-Service [m2]</span><span class="sxs-lookup"><span data-stu-id="8b757-144">Get-Service [m2]</span></span>](https://technet.microsoft.com/en-us/library/0a09cb22-0a1c-4a79-9851-4e53075f9cf6)
- [<span data-ttu-id="8b757-145">Set-Service [m2]</span><span class="sxs-lookup"><span data-stu-id="8b757-145">Set-Service [m2]</span></span>](https://technet.microsoft.com/en-us/library/b71e29ed-372b-4e32-a4b7-5eb6216e56c3)
- [<span data-ttu-id="8b757-146">Restart-Service [m2]</span><span class="sxs-lookup"><span data-stu-id="8b757-146">Restart-Service [m2]</span></span>](https://technet.microsoft.com/en-us/library/45acf50d-2277-4523-baf7-ce7ced977d0f)
- [<span data-ttu-id="8b757-147">Suspend-Service [m2]</span><span class="sxs-lookup"><span data-stu-id="8b757-147">Suspend-Service [m2]</span></span>](https://technet.microsoft.com/en-us/library/c8492b87-0e21-4faf-8054-3c83c2ec2826)
