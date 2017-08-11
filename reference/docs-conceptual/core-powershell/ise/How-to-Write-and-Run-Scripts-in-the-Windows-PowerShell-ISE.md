---
ms.date: 2017-06-05
keywords: powershell,applet de commande
title: "Comment écrire et exécuter des scripts dans Windows PowerShell ISE"
ms.assetid: 62f916d9-b3a1-484a-bdfb-41f57112c22b
ms.openlocfilehash: 871a4b6f4575af4f823a6957dc971335497320a4
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2017
---
# <a name="how-to-write-and-run-scripts-in-the-windows-powershell-ise"></a><span data-ttu-id="2ddae-103">Comment écrire et exécuter des scripts dans Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="2ddae-103">How to Write and Run Scripts in the Windows PowerShell ISE</span></span>
<span data-ttu-id="2ddae-104">Cette rubrique décrit comment créer, modifier, exécuter et enregistrer des scripts dans le volet Script.</span><span class="sxs-lookup"><span data-stu-id="2ddae-104">This topic describes how to create, edit, run, and save scripts in the Script Pane.</span></span>

-   [<span data-ttu-id="2ddae-105">Comment créer et exécuter des scripts</span><span class="sxs-lookup"><span data-stu-id="2ddae-105">How to create and run scripts</span></span>](#bkmk_1)

-   [<span data-ttu-id="2ddae-106">Comment écrire et modifier du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-106">How to write and edit text in the Script Pane</span></span>](#bkmk_2)

-   [<span data-ttu-id="2ddae-107">Comment enregistrer un script</span><span class="sxs-lookup"><span data-stu-id="2ddae-107">How to save a script</span></span>](#bkmk_3)

## <span data-ttu-id="2ddae-108"><a name="bkmk_1"></a>Comment créer et exécuter des scripts</span><span class="sxs-lookup"><span data-stu-id="2ddae-108"><a name="bkmk_1"></a>How to create and run scripts</span></span>
<span data-ttu-id="2ddae-109">Vous pouvez ouvrir et modifier des fichiers Windows PowerShell® dans le volet Script.</span><span class="sxs-lookup"><span data-stu-id="2ddae-109">You can open and edit Windows PowerShell® files in the Script Pane.</span></span> <span data-ttu-id="2ddae-110">Les types de fichiers spécifiques particulièrement intéressants dans Windows PowerShell® sont les fichiers de script (.ps1), les fichiers de données de script (.psd1) et les fichiers de module de script (.psm1).</span><span class="sxs-lookup"><span data-stu-id="2ddae-110">Specific file types of interest in Windows PowerShell® are script files (.ps1), script data files (.psd1), and script module files (.psm1).</span></span> <span data-ttu-id="2ddae-111">Ces types de fichiers font l’objet d’une coloration de la syntaxe dans l’éditeur du volet Script.</span><span class="sxs-lookup"><span data-stu-id="2ddae-111">These file types are syntax colored in the Script Pane editor.</span></span> <span data-ttu-id="2ddae-112">D’autres types de fichiers courants que vous pouvez ouvrir dans le volet Script sont les fichiers de configuration (.ps1xml), les fichiers XML et les fichiers texte.</span><span class="sxs-lookup"><span data-stu-id="2ddae-112">Other common file types you may open in the Script Pane are configuration files (.ps1xml), XML files, and text files.</span></span>

> [!NOTE]
> <span data-ttu-id="2ddae-113">La stratégie d’exécution de Windows PowerShell détermine si vous pouvez exécuter des scripts et charger des fichiers de configuration et des profils Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ddae-113">The Windows PowerShell execution policy determines whether you can run scripts and load Windows PowerShell profiles and configuration files.</span></span> <span data-ttu-id="2ddae-114">La stratégie d’exécution par défaut, restreinte, empêche l’exécution de tous les scripts et le chargement de profils.</span><span class="sxs-lookup"><span data-stu-id="2ddae-114">The default execution policy, Restricted, prevents all scripts from running, and prevents loading profiles.</span></span> <span data-ttu-id="2ddae-115">Pour savoir comment modifier la stratégie d’exécution afin d’autoriser le chargement et l’utilisation de profils, voir [Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/en-us/library/5690a0e1-495b-4e63-8280-65ead7bf01ab) et [about_Signing [v4]](https://technet.microsoft.com/en-us/library/fcbdd3b9-0b9f-4734-b5c7-e0dcc304fa1d).</span><span class="sxs-lookup"><span data-stu-id="2ddae-115">To change the execution policy to allow profiles to load and be used, see [Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/en-us/library/5690a0e1-495b-4e63-8280-65ead7bf01ab) and [about_Signing [v4]](https://technet.microsoft.com/en-us/library/fcbdd3b9-0b9f-4734-b5c7-e0dcc304fa1d).</span></span>

### <a name="to-create-a-new-script-file"></a><span data-ttu-id="2ddae-116">Pour créer un fichier de script</span><span class="sxs-lookup"><span data-stu-id="2ddae-116">To create a new script file</span></span>
<span data-ttu-id="2ddae-117">Dans la barre d’outils, cliquez sur **Nouveau** ou, dans le menu **Fichier**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-117">On the toolbar, click **New** , or on the **File** menu, click **New**.</span></span> <span data-ttu-id="2ddae-118">Le fichier créé s’affiche dans un nouvel onglet de fichier sous l’onglet PowerShell actif.</span><span class="sxs-lookup"><span data-stu-id="2ddae-118">The created file appears in a new file tab under the current PowerShell tab.</span></span> <span data-ttu-id="2ddae-119">N’oubliez pas que les onglets PowerShell sont visibles uniquement quand il y en a plusieurs.</span><span class="sxs-lookup"><span data-stu-id="2ddae-119">Remember that the PowerShell tabs are only visible when there are more than one.</span></span> <span data-ttu-id="2ddae-120">Par défaut, un fichier de script type (.ps1) est créé, mais il peut être enregistré avec un nouveau nom et une nouvelle extension.</span><span class="sxs-lookup"><span data-stu-id="2ddae-120">By default a file of type script (.ps1) is created, but it can be saved with a new name and extension.</span></span> <span data-ttu-id="2ddae-121">Plusieurs fichiers de script peuvent être créés sous le même onglet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ddae-121">Multiple script files can be created in the same PowerShell tab.</span></span>

### <a name="to-open-an-existing-script"></a><span data-ttu-id="2ddae-122">Pour ouvrir un script existant</span><span class="sxs-lookup"><span data-stu-id="2ddae-122">To open an existing script</span></span>
<span data-ttu-id="2ddae-123">Dans la barre d’outils, cliquez sur **Ouvrir...** ou, dans le menu **Fichier**, cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-123">On the toolbar, click **Open…**, or on the **File** menu, click **Open**.</span></span> <span data-ttu-id="2ddae-124">Dans la boîte de dialogue **Ouvrir**, sélectionnez le fichier à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="2ddae-124">In the **Open** dialog box, select the file you want to open.</span></span> <span data-ttu-id="2ddae-125">Le fichier ouvert s’affiche dans un nouvel onglet.</span><span class="sxs-lookup"><span data-stu-id="2ddae-125">The opened file appears in a new tab.</span></span>

### <a name="to-close-a-script-tab"></a><span data-ttu-id="2ddae-126">Pour fermer un onglet de script</span><span class="sxs-lookup"><span data-stu-id="2ddae-126">To close a script tab</span></span>
<span data-ttu-id="2ddae-127">Cliquez sur l’onglet de script du script que vous voulez fermer, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ddae-127">Click the script tab of the script you want to close, then do one of the following:</span></span>

1.  <span data-ttu-id="2ddae-128">Cliquez sur l’icône **Fermer** (X) sous l’onglet de script.</span><span class="sxs-lookup"><span data-stu-id="2ddae-128">Click the **Close** icon (X) on the script tab.</span></span>

2.  <span data-ttu-id="2ddae-129">Dans le menu **Fichier**, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-129">On the **File** menu, click **Close**.</span></span>

<span data-ttu-id="2ddae-130">Si le fichier a été modifié depuis son dernier enregistrement, vous êtes invité à l’enregistrer ou à l’ignorer.</span><span class="sxs-lookup"><span data-stu-id="2ddae-130">If the file has been altered since it was last saved, you are prompted to save or discard it.</span></span>

### <a name="to-display-the-file-path"></a><span data-ttu-id="2ddae-131">Pour afficher le chemin d’accès du fichier</span><span class="sxs-lookup"><span data-stu-id="2ddae-131">To display the file path</span></span>
<span data-ttu-id="2ddae-132">Sous l’onglet Fichier, pointez sur le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="2ddae-132">On the file tab, point to the file name.</span></span> <span data-ttu-id="2ddae-133">Le chemin d’accès complet au fichier de script s’affiche dans une info-bulle.</span><span class="sxs-lookup"><span data-stu-id="2ddae-133">The fully qualified path to the script file appears in a tooltip.</span></span>

### <a name="to-run-a-script"></a><span data-ttu-id="2ddae-134">Pour exécuter un script</span><span class="sxs-lookup"><span data-stu-id="2ddae-134">To run a script</span></span>
<span data-ttu-id="2ddae-135">Dans la barre d’outils, cliquez sur **Exécuter le Script** ou, dans le menu **Fichier**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-135">On the toolbar, click **Run Script**, or on the **File** menu, click **Run**.</span></span>

### <a name="to-run-a-portion-of-a-script"></a><span data-ttu-id="2ddae-136">Pour exécuter une partie d’un script</span><span class="sxs-lookup"><span data-stu-id="2ddae-136">To run a portion of a script</span></span>

1.  <span data-ttu-id="2ddae-137">Dans le volet Script, sélectionnez une partie d’un script.</span><span class="sxs-lookup"><span data-stu-id="2ddae-137">In the Script Pane, select a portion of a script.</span></span>

2.  <span data-ttu-id="2ddae-138">Dans le menu **Fichier**, cliquez sur **Exécuter la sélection** ou, dans la barre d’outils, cliquez sur **Exécuter la sélection**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-138">On the **File** menu, click **Run Selection**, or on the toolbar, click **Run Selection**.</span></span>

### <a name="to-stop-a-running-script"></a><span data-ttu-id="2ddae-139">Pour arrêter un script en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="2ddae-139">To stop a running script</span></span>
<span data-ttu-id="2ddae-140">Dans la barre d’outils, cliquez sur **Arrêter l’opération**, puis appuyez sur Ctrl+Pause, ou, dans le menu **Fichier**, cliquez sur **Arrêter l’opération**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-140">On the toolbar, click **Stop Operation**, press CTRL+BREAK, or on the **File** menu, click **Stop Operation**.</span></span> <span data-ttu-id="2ddae-141">Appuyer sur **Ctrl+C** fonctionne également, sauf si du texte est sélectionné, auquel cas l’appui sur **Ctrl+C** mappe à la fonction de copie pour le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2ddae-141">Pressing **CTRL+C** also works unless some text is currently selected, in which case **CTRL+C** maps to the copy function for the selected text.</span></span>

## <span data-ttu-id="2ddae-142"><a name="bkmk_2"></a>Comment écrire et modifier du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-142"><a name="bkmk_2"></a>How to write and edit text in the Script Pane</span></span>
<span data-ttu-id="2ddae-143">Pour modifier le texte dans le volet Script, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2ddae-143">Use the following steps to edit text in the Script Pane.</span></span> <span data-ttu-id="2ddae-144">Vous pouvez copier, couper, coller, rechercher et remplacer du texte.</span><span class="sxs-lookup"><span data-stu-id="2ddae-144">You can copy, cut, paste, find, and replace text.</span></span> <span data-ttu-id="2ddae-145">Vous pouvez également annuler et rétablir la dernière action exécutée.</span><span class="sxs-lookup"><span data-stu-id="2ddae-145">You can also undo and redo the last action you just performed.</span></span> <span data-ttu-id="2ddae-146">Les raccourcis clavier pour exécuter ces actions sont les mêmes que ceux utilisés pour toutes les applications Windows.</span><span class="sxs-lookup"><span data-stu-id="2ddae-146">The keyboard shortcuts for performing these actions are the same as those used for all Windows applications.</span></span>

### <a name="to-enter-text-in-the-script-pane"></a><span data-ttu-id="2ddae-147">Pour entrer du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-147">To enter text in the Script Pane</span></span>

1.  <span data-ttu-id="2ddae-148">Déplacez le curseur vers le volet Script en cliquant n’importe où dans celui-ci, ou en cliquant sur **Atteindre le volet Script** dans le menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-148">Move the cursor to the Script Pane by clicking anywhere in the Script Pane, or by clicking **Go to Script Pane** in the **View** menu.</span></span>

2.  <span data-ttu-id="2ddae-149">Créez un script.</span><span class="sxs-lookup"><span data-stu-id="2ddae-149">Create a script.</span></span> <span data-ttu-id="2ddae-150">La coloration de la syntaxe et la saisie semi-automatique par le biais de la touche Tab enrichissent cette expérience dans Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="2ddae-150">Syntax coloring and tab completion make this a richer experience in Windows PowerShell ISE.</span></span>

3.  <span data-ttu-id="2ddae-151">Pour plus d’informations sur l’utilisation de la fonctionnalité de saisie semi-automatique via la touche Tab pour faciliter la frappe, voir [Comment utiliser la saisie semi-automatique via la touche Tab dans le volet Script et le volet Console](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md).</span><span class="sxs-lookup"><span data-stu-id="2ddae-151">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for details about using the tab completion feature to help in typing.</span></span>

### <a name="to-find-text-in-the-script-pane"></a><span data-ttu-id="2ddae-152">Pour rechercher du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-152">To find text in the Script Pane</span></span>

1.  <span data-ttu-id="2ddae-153">Pour rechercher du texte n’importe où, appuyez sur **Ctrl+F** ou, dans le menu **Modifier**, cliquez sur **Rechercher dans le script**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-153">To find text anywhere, press **CTRL+F** or, on the **Edit** menu, click **Find in Script**.</span></span>

2.  <span data-ttu-id="2ddae-154">Pour rechercher du texte situé après le curseur, appuyez sur **F3** ou, dans le menu **Modifier**, cliquez sur **Rechercher suivant dans le script**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-154">To find text after the cursor, press **F3** or, on the **Edit** menu, click **Find Next in Script**.</span></span>

3.  <span data-ttu-id="2ddae-155">Pour rechercher du texte devant le curseur, appuyez sur **Maj+F3** ou, dans le menu **Modifier**, cliquez sur **Rechercher précédent dans le script**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-155">To find text before the cursor, press **SHIFT+F3** or, on the **Edit** menu, click **Find Previous in Script**.</span></span>

### <a name="to-find-and-replace-text-in-the-script-pane"></a><span data-ttu-id="2ddae-156">Pour rechercher et remplacer du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-156">To find and replace text in the Script Pane</span></span>
<span data-ttu-id="2ddae-157">Appuyez sur **Ctrl+H** ou, dans le menu **Modifier**, cliquez sur **Remplacer dans le script**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-157">Press **CRTL+H** or, on the **Edit** menu, click **Replace in Script**.</span></span> <span data-ttu-id="2ddae-158">Entrez le texte à rechercher et le texte à y substituer, puis appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-158">Enter both the text you want to find and the text with which you want to replace it, and then press **ENTER**.</span></span>

### <a name="to-go-to-a-particular-line-of-text-in-the-script-pane"></a><span data-ttu-id="2ddae-159">Pour accéder à une ligne particulière du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-159">To go to a particular line of text in the Script Pane</span></span>

1.  <span data-ttu-id="2ddae-160">Dans le volet Script, appuyez sur **Ctrl+G** ou, dans le menu **Modifier**, cliquez sur **Atteindre la ligne**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-160">In the Script Pane, press **CTRL+G** or, on the **Edit** menu, click **Go to Line**.</span></span>

2.  <span data-ttu-id="2ddae-161">Entrez un numéro de ligne.</span><span class="sxs-lookup"><span data-stu-id="2ddae-161">Enter a line number.</span></span>

### <a name="to-copy-text-in-the-script-pane"></a><span data-ttu-id="2ddae-162">Pour copier du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-162">To copy text in the Script Pane</span></span>

1.  <span data-ttu-id="2ddae-163">Dans le volet Script, sélectionnez le texte à copier.</span><span class="sxs-lookup"><span data-stu-id="2ddae-163">In the Script Pane, select the text that you want to copy.</span></span>

2.  <span data-ttu-id="2ddae-164">Appuyez sur **Ctrl+C** ou, dans la barre d’outils, cliquez sur l’icône **Copier**, ou encore, dans le menu **Modifier**, cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-164">Press **CTRL+C** or, on the toolbar, click the **Copy** icon, or on the **Edit** menu, click **Copy**.</span></span>

### <a name="to-cut-text-in-the-script-pane"></a><span data-ttu-id="2ddae-165">Pour couper du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-165">To cut text in the Script Pane</span></span>

1.  <span data-ttu-id="2ddae-166">Dans le volet Script, sélectionnez le texte à couper.</span><span class="sxs-lookup"><span data-stu-id="2ddae-166">In the Script Pane, select the text that you want to cut.</span></span>

2.  <span data-ttu-id="2ddae-167">Appuyez sur **Ctrl+X** ou, dans la barre d’outils, cliquez sur l’icône **Couper**, ou encore, dans le menu **Modifier**, cliquez sur **Couper**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-167">Press **CTRL+X** or, on the toolbar, click the **Cut** icon, or on the **Edit** menu, click **Cut**.</span></span>

### <a name="to-paste-text-into-the-script-pane"></a><span data-ttu-id="2ddae-168">Pour coller du texte dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-168">To paste text into the Script Pane</span></span>
<span data-ttu-id="2ddae-169">Appuyez sur **Ctrl+V** ou, dans la barre d’outils, cliquez sur l’icône **Coller**, ou encore, dans le menu **Modifier**, cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-169">Press **CTRL+V** or, on the toolbar, click the **Paste** icon, or on the **Edit** menu, click **Paste**.</span></span>

### <a name="to-undo-an-action-in-the-script-pane"></a><span data-ttu-id="2ddae-170">Pour annuler une action dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-170">To undo an action in the Script Pane</span></span>
<span data-ttu-id="2ddae-171">Appuyez sur **Ctrl+Z** ou, dans la barre d’outils, cliquez sur l’icône **Annuler**, ou encore, dans le menu **Modifier**, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-171">Press **CTRL+Z** or, on the toolbar, click the **Undo** icon, or on the **Edit** menu, click **Undo**.</span></span>

### <a name="to-redo-an-action-in-the-script-pane"></a><span data-ttu-id="2ddae-172">Pour rétablir une action dans le volet Script</span><span class="sxs-lookup"><span data-stu-id="2ddae-172">To redo an action in the Script Pane</span></span>
<span data-ttu-id="2ddae-173">Appuyez sur **Ctrl+Y** ou, dans la barre d’outils, cliquez sur l’icône **Rétablir**, ou encore, dans le menu **Modifier**, cliquez sur **Rétablir**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-173">Press **CTRL+Y** or, on the toolbar, click the **Redo** icon, or on the **Edit** menu, click **Redo**.</span></span>

## <span data-ttu-id="2ddae-174"><a name="bkmk_3"></a>Comment enregistrer un script</span><span class="sxs-lookup"><span data-stu-id="2ddae-174"><a name="bkmk_3"></a>How to save a script</span></span>
<span data-ttu-id="2ddae-175">Pour enregistrer et nommer un script, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2ddae-175">Use the following steps to save and name a script.</span></span> <span data-ttu-id="2ddae-176">Un astérisque apparaît en regard du nom de script pour marquer un fichier qui n’a pas été enregistré depuis sa modification.</span><span class="sxs-lookup"><span data-stu-id="2ddae-176">An asterisk appears next to the script name to mark a file that has not been saved since it was altered.</span></span> <span data-ttu-id="2ddae-177">L’astérisque disparaît lors de l’enregistrement du fichier.</span><span class="sxs-lookup"><span data-stu-id="2ddae-177">The asterisk disappears when the file is saved.</span></span>

### <a name="to-save-a-script"></a><span data-ttu-id="2ddae-178">Pour enregistrer un script</span><span class="sxs-lookup"><span data-stu-id="2ddae-178">To save a script</span></span>
<span data-ttu-id="2ddae-179">Appuyez sur **Ctrl+S** ou, dans la barre d’outils, cliquez sur l’icône **Enregistrer**, ou encore, dans le menu **Fichier**, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-179">Press **CTRL+S** or, on the toolbar, click the **Save** icon, or on the **File** menu, click **Save**.</span></span>

### <a name="to-save-and-name-a-script"></a><span data-ttu-id="2ddae-180">Pour enregistrer et nommer un script</span><span class="sxs-lookup"><span data-stu-id="2ddae-180">To save and name a script</span></span>

1.  <span data-ttu-id="2ddae-181">Dans le menu **Fichier**, cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-181">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="2ddae-182">La boîte de dialogue **Enregistrer sous** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2ddae-182">The **Save As** dialog box will appear.</span></span>

2.  <span data-ttu-id="2ddae-183">Dans le champ **Nom de fichier**, entrez un nom pour le fichier.</span><span class="sxs-lookup"><span data-stu-id="2ddae-183">In the **File name** box, enter a name for the file.</span></span>

3.  <span data-ttu-id="2ddae-184">Dans le champ **Type de fichier**, sélectionnez un type de fichier.</span><span class="sxs-lookup"><span data-stu-id="2ddae-184">In the **Save as type** box, select a file type.</span></span> <span data-ttu-id="2ddae-185">Par exemple, dans le champ **Type de fichier**, sélectionnez « Scripts PowerShell (\* .ps1) ».</span><span class="sxs-lookup"><span data-stu-id="2ddae-185">For example, in the **Save as type** box, select “PowerShell Scripts (\* .ps1)”.</span></span>

4.  <span data-ttu-id="2ddae-186">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2ddae-186">Click **Save**.</span></span>

### <a name="to-save-a-script-in-ascii-encoding"></a><span data-ttu-id="2ddae-187">Pour enregistrer un script en encodage ASCII</span><span class="sxs-lookup"><span data-stu-id="2ddae-187">To save a script in ASCII encoding</span></span>
<span data-ttu-id="2ddae-188">Par défaut, Windows PowerShell ISE enregistre les nouveaux fichiers de script (.ps1), les fichiers de données de script (.psd1) et les fichiers de module de script (.psm1) au format Unicode (BigEndianUnicode).</span><span class="sxs-lookup"><span data-stu-id="2ddae-188">By default, Windows PowerShell ISE saves new script files (.ps1), script data files (.psd1), and script module files (.psm1) as Unicode (BigEndianUnicode) by default.</span></span> <span data-ttu-id="2ddae-189">Pour enregistrer un script dans un autre encodage, tel ASCII (ANSI), utilisez les méthodes **Save** ou **SaveAs** sur l’objet [$psISE.CurrentFile](https://technet.microsoft.com/en-us/library/bc3300e4-9c17-4f00-a621-c8867126e3b3#CurrentFile).</span><span class="sxs-lookup"><span data-stu-id="2ddae-189">To save a script in another encoding, such as ASCII (ANSI), use the **Save** or **SaveAs** methods on the [$psISE.CurrentFile](https://technet.microsoft.com/en-us/library/bc3300e4-9c17-4f00-a621-c8867126e3b3#CurrentFile) object.</span></span>

<span data-ttu-id="2ddae-190">La commande suivante enregistre un nouveau script sous MyScript.ps1 avec un encodage ASCII.</span><span class="sxs-lookup"><span data-stu-id="2ddae-190">The following command saves a new script as MyScript.ps1 with ASCII encoding.</span></span>

```
$psise.CurrentFile.SaveAs("MyScript.ps1", [System.Text.Encoding]::ASCII)
```

<span data-ttu-id="2ddae-191">La commande suivante remplace le fichier de script actuel par un fichier du même nom, mais avec un encodage ASCII.</span><span class="sxs-lookup"><span data-stu-id="2ddae-191">The following command replaces the current script file with a file with the same name, but with ASCII encoding.</span></span>

```
$psise.CurrentFile.Save([System.Text.Encoding]::ASCII)
```

<span data-ttu-id="2ddae-192">La commande suivante obtient l’encodage du fichier actuel.</span><span class="sxs-lookup"><span data-stu-id="2ddae-192">The following command gets the encoding of the current file.</span></span>

```
$psise.CurrentFile.encoding
```

<span data-ttu-id="2ddae-193">Windows PowerShell ISE prend en charge les options d’encodage suivantes : ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8 et Default.</span><span class="sxs-lookup"><span data-stu-id="2ddae-193">Windows PowerShell ISE supports the following encoding options: ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8 and Default.</span></span> <span data-ttu-id="2ddae-194">La valeur de l’option Default varie selon le système.</span><span class="sxs-lookup"><span data-stu-id="2ddae-194">The value of the Default option varies with the system.</span></span>

<span data-ttu-id="2ddae-195">Windows PowerShell ISE ne modifie pas l’encodage des scripts qui ont été créés par d’autres éditeurs, même si vous utilisez les commandes Save ou Save As dans Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="2ddae-195">Windows PowerShell ISE does not change the encoding of scripts that were created by in other editors, even when you use the Save or Save As commands in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ddae-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ddae-196">See Also</span></span>
- [<span data-ttu-id="2ddae-197">Utilisation de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="2ddae-197">Using the Windows PowerShell ISE</span></span>](Using-the-Windows-PowerShell-ISE.md)
