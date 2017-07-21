---
ms.date: 2017-06-05
keywords: powershell,applet de commande
title: Objet PowerShellTab
ms.assetid: a9b58556-951b-4f48-b3ae-b351b7564360
ms.openlocfilehash: d4e9374202d352a30b3eb46bcf1e4e40dea49822
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2017
---
# <a name="the-powershelltab-object"></a><span data-ttu-id="4961d-103">Objet PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="4961d-103">The PowerShellTab Object</span></span>
  <span data-ttu-id="4961d-104">L’objet **PowerShellTab** représente un environnement d’exécution Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4961d-104">The **PowerShellTab** object represents a Windows PowerShell runtime environment.</span></span>

## <a name="methods"></a><span data-ttu-id="4961d-105">Méthodes</span><span class="sxs-lookup"><span data-stu-id="4961d-105">Methods</span></span>

###  <span data-ttu-id="4961d-106"><a name="invoke"></a> Invoke\( Script \)</span><span class="sxs-lookup"><span data-stu-id="4961d-106"><a name="invoke"></a> Invoke\( Script \)</span></span>
  <span data-ttu-id="4961d-107">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-107">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-108">Exécute le script spécifié dans l’onglet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4961d-108">Runs the given script in the PowerShell tab.</span></span>

> [!NOTE]
>  <span data-ttu-id="4961d-109">Cette méthode effectue cette action uniquement dans les onglets PowerShell autres que l’onglet PowerShell à partir duquel elle est exécutée.</span><span class="sxs-lookup"><span data-stu-id="4961d-109">This method only works on other PowerShell tabs, not the PowerShell tab from which it is run.</span></span> <span data-ttu-id="4961d-110">Elle ne renvoie pas d’objet ou de valeur.</span><span class="sxs-lookup"><span data-stu-id="4961d-110">It does not return any object or value.</span></span> <span data-ttu-id="4961d-111">Si le code modifie une variable, ces modifications s’appliquent à l’onglet pour lequel la commande a été appelée.</span><span class="sxs-lookup"><span data-stu-id="4961d-111">If the code modifies any variable, then those changes persist on the tab against which the command was invoked.</span></span>

 <span data-ttu-id="4961d-112">**Script** \- System.Management.Automation.ScriptBlock ou chaîne. Bloc de script à utiliser.</span><span class="sxs-lookup"><span data-stu-id="4961d-112">**Script** - System.Management.Automation.ScriptBlock or String The script block to run.</span></span>

```
# Manually create a second PowerShell tab before running this script.
# Return to the first PowerShell tab and type the following command
$psise.PowerShellTabs[1].Invoke({dir})
```

### <a name="invokesynchronous-script-usenewscope-millisecondstimeout-"></a><span data-ttu-id="4961d-113">InvokeSynchronous\( Script, \[useNewScope\], millisecondsTimeout \)</span><span class="sxs-lookup"><span data-stu-id="4961d-113">InvokeSynchronous\( Script, \[useNewScope\], millisecondsTimeout \)</span></span>
  <span data-ttu-id="4961d-114">Prise en charge dans Windows PowerShell ISE 3.0 et versions ultérieures, ne figure pas dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-114">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4961d-115">Exécute le script spécifié dans l’onglet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4961d-115">Runs the given script in the PowerShell tab.</span></span>

> [!NOTE]
>  <span data-ttu-id="4961d-116">Cette méthode effectue cette action uniquement dans les onglets PowerShell autres que l’onglet PowerShell à partir duquel elle est exécutée.</span><span class="sxs-lookup"><span data-stu-id="4961d-116">This method only works on other PowerShell tabs, not the PowerShell tab from which it is run.</span></span> <span data-ttu-id="4961d-117">Le bloc de script est exécuté. Les valeurs renvoyées par le script sont renvoyées à l’environnement d’exécution à partir duquel vous avez appelé la commande.</span><span class="sxs-lookup"><span data-stu-id="4961d-117">The script block is run and any value that is returned from the script is returned to the run environment from which you invoked the command.</span></span> <span data-ttu-id="4961d-118">Si la durée d’exécution de la commande dépasse la valeur **millesecondsTimeout** spécifiée, la commande échoue avec une exception : « Le délai de l’opération a expiré. »</span><span class="sxs-lookup"><span data-stu-id="4961d-118">If the command takes longer to run than the **millesecondsTimeout** value specifies, then the command fails with an exception: "The operation has timed out."</span></span>

 <span data-ttu-id="4961d-119">**Script** \- System.Management.Automation.ScriptBlock ou chaîne. Bloc de script à utiliser.</span><span class="sxs-lookup"><span data-stu-id="4961d-119">**Script** - System.Management.Automation.ScriptBlock or String The script block to run.</span></span>

 <span data-ttu-id="4961d-120">**\[useNewScope\]** : valeur booléenne facultative qui a la valeur **$true**
 par défaut Si la valeur est **$true**, une nouvelle étendue est créée pour y exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="4961d-120">**\[useNewScope\]** -  Optional Boolean that defaults to **$true**
 If set to **$true**, then a new scope is created within which to run the command.</span></span> <span data-ttu-id="4961d-121">Cela ne modifie pas l’environnement d’exécution de l’onglet PowerShell qui est spécifié par la commande.</span><span class="sxs-lookup"><span data-stu-id="4961d-121">It does not modify the runtime environment of the PowerShell tab that is specified by the command.</span></span>

 <span data-ttu-id="4961d-122">**\[millisecondsTimeout\]** - Entier facultatif qui a la valeur **500** par défaut.</span><span class="sxs-lookup"><span data-stu-id="4961d-122">**\[millisecondsTimeout\]** -  Optional integer that defaults to **500**.</span></span>
<span data-ttu-id="4961d-123">Si la commande ne se termine pas dans le délai spécifié, la commande génère une exception **TimeoutException** avec le message « Le délai de l’opération a expiré. »</span><span class="sxs-lookup"><span data-stu-id="4961d-123">If the command does not finish within the specified time, then the command generates a **TimeoutException** with the message "The operation has timed out."</span></span>

```
# create a new PowerShell tab and then switch back to the first
$PSise.PowerShellTabs.Add()
$psISE.PowerShellTabs.SetSelectedPowerShellTab($psISE.PowerShellTabs[0]) 

# Invoke a simple command on the other tab, in its own scope
$psISE.PowerShellTabs[1].InvokeSynchronous('$x=1',$false)
# You can switch to the other tab and type “$x” to see that the value is saved there.

# This example sets a value in the other tab (in a different scope) 
# and returns it through the pipeline to this tab to store in $a
$a=$psISE.PowerShellTabs[1].InvokeSynchronous('$z=3;$z') 
$a

# This example runs a command that takes longer than the allowed timeout value
# and measures how long it runs so that you can see the impact
measure-command {$psISE.PowerShellTabs[1].InvokeSynchronous("sleep 10",$false,5000)}

```

## <a name="properties"></a><span data-ttu-id="4961d-124">Propriétés</span><span class="sxs-lookup"><span data-stu-id="4961d-124">Properties</span></span>

###  <span data-ttu-id="4961d-125"><a name="AddOnsMenu"></a> AddOnsMenu</span><span class="sxs-lookup"><span data-stu-id="4961d-125"><a name="AddOnsMenu"></a> AddOnsMenu</span></span>
  <span data-ttu-id="4961d-126">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-126">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-127">Propriété en lecture seule qui obtient le menu complémentaire de l’onglet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4961d-127">The read-only property that gets the Add-ons menu for the PowerShell tab.</span></span>

```
# Clear the Add-ons menu if one exists.
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
# Create an AddOns menu with an accessor.
# Note the use of "_"  as opposed to the "&" for mapping to the fast key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P") 
# Add a nested menu. 
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("Parent",$null,$null) 
$parentAdded.SubMenus.Add("_Dir",{dir},"Alt+D")
# Show the Add-ons menu on the current PowerShell tab.
$psISE.CurrentPowerShellTab.AddOnsMenu
```

###  <span data-ttu-id="4961d-128"><a name="CanExecute"></a> CanInvoke</span><span class="sxs-lookup"><span data-stu-id="4961d-128"><a name="CanExecute"></a> CanInvoke</span></span>
  <span data-ttu-id="4961d-129">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-129">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-130">Propriété booléenne en lecture seule qui renvoie la valeur **$true** si un script peut être appelé avec la méthode [Invoke( Script )](#invoke).</span><span class="sxs-lookup"><span data-stu-id="4961d-130">The read-only Boolean property that returns a **$true** value if a script can be invoked with the [Invoke( Script )](#invoke) method.</span></span>

```
# CanInvoke will be false if the PowerShell
# tab is running a script that takes a while, and you
# check its properties from another PowerShell tab. It is
# always false if checked on the current PowerShell tab. 
# Manually create a second PowerShell tab before running this script.
# Return to the first tab and type
$secondTab = $psise.PowerShellTabs[1] 
$secondTab.CanInvoke 
$secondTab.Invoke({sleep 20})
$secondTab.CanInvoke

```

###  <span data-ttu-id="4961d-131"><a name="Commandpane"></a> Consolepane</span><span class="sxs-lookup"><span data-stu-id="4961d-131"><a name="Commandpane"></a> Consolepane</span></span>
  <span data-ttu-id="4961d-132">Prise en charge dans Windows PowerShell ISE 3.0 et versions ultérieures, ne figure pas dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-132">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>  <span data-ttu-id="4961d-133">Dans Windows PowerShell ISE 2.0, cette propriété s’appelait **CommandPane**.</span><span class="sxs-lookup"><span data-stu-id="4961d-133">In Windows PowerShell ISE 2.0 this was named **CommandPane**.</span></span>

 <span data-ttu-id="4961d-134">Propriété en lecture seule qui obtient l’objet [editor](../ise/The-ISEEditor-Object.md) du volet de la console.</span><span class="sxs-lookup"><span data-stu-id="4961d-134">The read-only property that gets the Console pane [editor](../ise/The-ISEEditor-Object.md) object.</span></span>

```
# Gets the Console Pane editor.
$psISE.CurrentPowerShellTab.ConsolePane

```

###  <span data-ttu-id="4961d-135"><a name="Displayname"></a> DisplayName</span><span class="sxs-lookup"><span data-stu-id="4961d-135"><a name="Displayname"></a> DisplayName</span></span>
  <span data-ttu-id="4961d-136">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-137">Propriété en lecture seule qui obtient ou définit le texte affiché dans l’onglet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4961d-137">The read-write property that gets or sets the text that is displayed on the PowerShell tab.</span></span> <span data-ttu-id="4961d-138">Par défaut, les onglets sont nommés « PowerShell # », où # est un nombre.</span><span class="sxs-lookup"><span data-stu-id="4961d-138">By default, tabs are named "PowerShell #", where the # represents a number.</span></span>

```
$newTab = $psise.PowerShellTabs.Add()
# Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="Brand New Tab"
```

###  <span data-ttu-id="4961d-139"><a name="ExpandedScript"></a> ExpandedScript</span><span class="sxs-lookup"><span data-stu-id="4961d-139"><a name="ExpandedScript"></a> ExpandedScript</span></span>
  <span data-ttu-id="4961d-140">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-141">Propriété booléenne en lecture\-écriture qui détermine si le volet de script est développé ou masqué.</span><span class="sxs-lookup"><span data-stu-id="4961d-141">The read-write Boolean property that determines whether the Script pane is expanded or hidden.</span></span>

```
# Toggle the expanded script property to see its effect.
$PSise.CurrentPowerShellTab.ExpandedScript=!$PSise.CurrentPowerShellTab.ExpandedScript

```

###  <span data-ttu-id="4961d-142"><a name="Files"></a> Files</span><span class="sxs-lookup"><span data-stu-id="4961d-142"><a name="Files"></a> Files</span></span>
  <span data-ttu-id="4961d-143">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-144">Propriété en lecture seule qui obtient la [collection des fichiers de script](../ise/The-ISEFileCollection-Object.md) qui sont ouverts dans l’onglet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4961d-144">The read-only property that gets the [collection of script files](../ise/The-ISEFileCollection-Object.md) that are open in the PowerShell tab.</span></span>

```
$newFile = $psISE.CurrentPowerShellTab.Files.Add()
$newFile.Editor.Text = "a`r`nb" 
# Gets the line count
$newFile.Editor.LineCount
```

###  <span data-ttu-id="4961d-145"><a name="Output"></a> Output</span><span class="sxs-lookup"><span data-stu-id="4961d-145"><a name="Output"></a> Output</span></span>
  <span data-ttu-id="4961d-146">Cette fonctionnalité est présente dans Windows PowerShell ISE 2.0, mais a été supprimée ou renommée dans les versions ultérieures de l'environnement ISE.</span><span class="sxs-lookup"><span data-stu-id="4961d-146">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="4961d-147">Dans les versions ultérieures de Windows PowerShell ISE, vous pouvez utiliser l’objet **ConsolePane** à la place.</span><span class="sxs-lookup"><span data-stu-id="4961d-147">In later versions of Windows PowerShell ISE, you can use the **ConsolePane** object for the same purposes.</span></span>

 <span data-ttu-id="4961d-148">Propriété en lecture seule qui obtient le volet de sortie de l’objet [editor](../ise/The-ISEEditor-Object.md) actuel.</span><span class="sxs-lookup"><span data-stu-id="4961d-148">The read-only property that gets the Output pane of the current [editor](../ise/The-ISEEditor-Object.md).</span></span>

```
# Clears the text in the Output pane.
$psise.CurrentPowerShellTab.output.clear()
```

###  <span data-ttu-id="4961d-149"><a name="Prompt"></a> Prompt</span><span class="sxs-lookup"><span data-stu-id="4961d-149"><a name="Prompt"></a> Prompt</span></span>
  <span data-ttu-id="4961d-150">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-150">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-151">Propriété en lecture seule qui obtient le texte d’invite actuel.</span><span class="sxs-lookup"><span data-stu-id="4961d-151">The read-only property that gets the current prompt text.</span></span> <span data-ttu-id="4961d-152">Remarque : la fonction **Prompt** peut être remplacée par le profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4961d-152">Note: the **Prompt** function can be overridden by the user’s profile.</span></span> <span data-ttu-id="4961d-153">Si le résultat n’est pas une chaîne simple, cette propriété ne renvoie rien.</span><span class="sxs-lookup"><span data-stu-id="4961d-153">If the result is other than a simple string, then this property returns nothing.</span></span>

```
# Gets the current prompt text.
$psISE.CurrentPowerShellTab.Prompt
```

###  <span data-ttu-id="4961d-154"><a name="ShowCommands"></a> ShowCommands</span><span class="sxs-lookup"><span data-stu-id="4961d-154"><a name="ShowCommands"></a> ShowCommands</span></span>
  <span data-ttu-id="4961d-155">Prise en charge dans Windows PowerShell ISE 3.0 et versions ultérieures, ne figure pas dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-155">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4961d-156">Propriété en lecture\-écriture qui indique si le volet de commandes est actuellement affiché.</span><span class="sxs-lookup"><span data-stu-id="4961d-156">The read-write property that indicates if the Commands pane is currently displayed.</span></span>

```
# Gets the current status of the Commands pane and stores it in the $a variable
$a = $psISE.CurrentPowerShellTab.ShowCommands
# if $a is $false, then turn the Commands pane on by changing the value to $True
if (!$a) {$psISE.CurrentPowerShellTab.ShowCommands=$True}
```

###  <span data-ttu-id="4961d-157"><a name="StatusText"></a> StatusText</span><span class="sxs-lookup"><span data-stu-id="4961d-157"><a name="StatusText"></a> StatusText</span></span>
  <span data-ttu-id="4961d-158">Prise en charge dans Windows PowerShell ISE 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-158">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="4961d-159">Propriété en lecture seule qui obtient le texte d’état **PowerShellTab**.</span><span class="sxs-lookup"><span data-stu-id="4961d-159">The read-only property that gets the **PowerShellTab** status text.</span></span>

```
# Gets the current status text,
$psISE.CurrentPowerShellTab.StatusText
```

###  <span data-ttu-id="4961d-160"><a name="HorizontalAddOnToolsPaneOpened"></a> HorizontalAddOnToolsPaneOpened</span><span class="sxs-lookup"><span data-stu-id="4961d-160"><a name="HorizontalAddOnToolsPaneOpened"></a> HorizontalAddOnToolsPaneOpened</span></span>
  <span data-ttu-id="4961d-161">Prise en charge dans Windows PowerShell ISE 3.0 et versions ultérieures, ne figure pas dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-161">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4961d-162">Propriété en lecture seule qui indique si le volet des outils complémentaires horizontal est actuellement ouvert.</span><span class="sxs-lookup"><span data-stu-id="4961d-162">The read-only property that indicates whether the horizontal Add-Ons tool pane is currently open.</span></span>

```
# Gets the current state of the horizontal Add-ons tool pane. 
$psISE.CurrentPowerShellTab.HorizontalAddOnToolsPaneOpened
```

###  <span data-ttu-id="4961d-163"><a name="VerticalAddOnToolsPaneOpened"></a> **VerticalAddOnToolsPaneOpened**</span><span class="sxs-lookup"><span data-stu-id="4961d-163"><a name="VerticalAddOnToolsPaneOpened"></a> **VerticalAddOnToolsPaneOpened**</span></span>
  <span data-ttu-id="4961d-164">Prise en charge dans Windows PowerShell ISE 3.0 et versions ultérieures, ne figure pas dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="4961d-164">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="4961d-165">Propriété en lecture seule qui indique si le volet des outils complémentaires vertical est actuellement ouvert.</span><span class="sxs-lookup"><span data-stu-id="4961d-165">The read-only property that indicates whether the vertical Add-Ons tool pane is currently open.</span></span>

```
# Turns on the Commands pane
$psISE.CurrentPowerShellTab.ShowCommands=$True
# Gets the current state of the vertical Add-ons tool pane. 
$psISE.CurrentPowerShellTab.HorizontalAddOnToolsPaneOpened
```

## <a name="see-also"></a><span data-ttu-id="4961d-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4961d-166">See Also</span></span>
- [<span data-ttu-id="4961d-167">Objet PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="4961d-167">The PowerShellTabCollection Object</span></span>](The-PowerShellTabCollection-Object.md) 
- [<span data-ttu-id="4961d-168">Modèle objet de script Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="4961d-168">The Windows PowerShell ISE Scripting Object Model</span></span>](../ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="4961d-169">Informations de référence sur le modèle objet Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="4961d-169">Windows PowerShell ISE Object Model Reference</span></span>](../ise/Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="4961d-170">Hiérarchie du modèle objet ISE</span><span class="sxs-lookup"><span data-stu-id="4961d-170">The ISE Object Model Hierarchy</span></span>](../ise/The-ISE-Object-Model-Hierarchy.md)

  
