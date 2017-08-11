---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: gallery,powershell,cmdlet,psgallery
title: "Création et publication d’un élément"
ms.openlocfilehash: e71381d1a3efda73832fab6189bda26cee411d9e
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="creating-and-publishing-an-item"></a><span data-ttu-id="4449b-103">Création et publication d’un élément</span><span class="sxs-lookup"><span data-stu-id="4449b-103">Creating and Publishing an Item</span></span> 
<span data-ttu-id="4449b-104">PowerShell Gallery est l’emplacement auquel publier et partager des modules PowerShell stables, des scripts et des ressources DSC avec l’ensemble de la communauté des utilisateurs PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4449b-104">The PowerShell Gallery is the place to publish and share stable PowerShell modules, scripts, and DSC resources with the broader PowerShell user community.</span></span>    

<span data-ttu-id="4449b-105">Cet article décrit les mécanismes et les principales étapes de la préparation d’un script ou d’un module, et sa publication dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-105">This article covers the mechanics and important steps for preparing a script or module, and publishing it to the PowerShell Gallery.</span></span>
<span data-ttu-id="4449b-106">Nous vous encourageons vivement à consulter les [instructions de publication](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery-PublishingGuidelines) pour comprendre comment vous assurer que les éléments que vous publiez seront plus largement acceptés par les utilisateurs de PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-106">We strongly encourage that you review the [Publishing Guidelines](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery-PublishingGuidelines) to understand how to ensure that the items you publish will be more widely accepted by PowerShell Gallery users.</span></span> 

<span data-ttu-id="4449b-107">Voici les conditions minimales requises pour publier un élément sur PowerShell Gallery :</span><span class="sxs-lookup"><span data-stu-id="4449b-107">The minimum requirements to publish an item to the PowerShell Gallery are:</span></span>

* <span data-ttu-id="4449b-108">Disposer d’un compte de galerie PowerShell et d’une clé d’API associée</span><span class="sxs-lookup"><span data-stu-id="4449b-108">Have a PowerShell Gallery account, and the API Key associated with it</span></span>
* <span data-ttu-id="4449b-109">Vérifiez que les métadonnées requises se trouvent dans votre élément</span><span class="sxs-lookup"><span data-stu-id="4449b-109">Ensure Required Metadata is in your item</span></span>
* <span data-ttu-id="4449b-110">Utiliser les outils de prévalidation pour garantir que votre élément est prêt à être publié</span><span class="sxs-lookup"><span data-stu-id="4449b-110">Use the pre-validation tools to ensure your item is ready to publish</span></span>
* <span data-ttu-id="4449b-111">Publier l’élément à l’aide des commandes Publish-Module et Publish-Script de PowerShell Gallery</span><span class="sxs-lookup"><span data-stu-id="4449b-111">Publish the item to the PowerShell Gallery using the Publish-Module and Publish-Script commands</span></span>
* <span data-ttu-id="4449b-112">Réponses aux questions ou problèmes relatifs à votre élément</span><span class="sxs-lookup"><span data-stu-id="4449b-112">Responding to questions or concerns about your item</span></span>
 
<span data-ttu-id="4449b-113">PowerShell Gallery accepte les modules PowerShell et les scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4449b-113">The PowerShell Gallery accepts PowerShell modules and PowerShell scripts.</span></span> <span data-ttu-id="4449b-114">Lorsque nous faisons référence à des scripts, nous entendons un script PowerShell qui est un fichier unique et ne fait pas partie d’un module plus vaste.</span><span class="sxs-lookup"><span data-stu-id="4449b-114">When we refer to scripts, we mean a PowerShell script that is a single file, and not part of a larger module.</span></span> 

## <a name="powershell-gallery-account-and-api-key"></a><span data-ttu-id="4449b-115">Compte et clé d’API pour PowerShell Gallery</span><span class="sxs-lookup"><span data-stu-id="4449b-115">PowerShell Gallery Account and API Key</span></span>
<span data-ttu-id="4449b-116">Consultez [Création d’un compte PowerShell Gallery](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery_creating_an_account) pour savoir comment configurer votre compte de PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-116">See [Creating a PowerShell Gallery Account](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery_creating_an_account) for how to set up your PowerShell Gallery account.</span></span> 

<span data-ttu-id="4449b-117">Une fois que vous avez créé un compte, vous pouvez obtenir la clé d’API nécessaire pour publier un élément.</span><span class="sxs-lookup"><span data-stu-id="4449b-117">Once you have created an account, you can get the API Key needed to publish an item.</span></span>
<span data-ttu-id="4449b-118">Une fois que vous vous connectez avec le compte, votre nom d’utilisateur s’affichera en haut des pages de PowerShell Gallery au lieu du Registre.</span><span class="sxs-lookup"><span data-stu-id="4449b-118">After you sign in with the account, your username will be displayed at the top of the PowerShell Gallery pages instead of Register.</span></span> <span data-ttu-id="4449b-119">Cliquer sur votre nom d’utilisateur vous redirigera vers la page Mon compte, où vous trouverez la clé d’API.</span><span class="sxs-lookup"><span data-stu-id="4449b-119">Clicking on your username will take you to the My Account page, where you will find the API Key.</span></span> 

<span data-ttu-id="4449b-120">Remarque : La clé d’API doit être traitée avec autant de soins de sécurité que votre identifiant et votre mot de passe.</span><span class="sxs-lookup"><span data-stu-id="4449b-120">Note: The API Key must be treated as securely as your login and password.</span></span> <span data-ttu-id="4449b-121">Avec cette clé, vous,ou toute autre personne pouvez mettre à jour n’importe quel élément que vous possédez dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-121">With this key you, or anyone else, can update any item you own in the PowerShell Gallery.</span></span> <span data-ttu-id="4449b-122">Nous vous recommandons de mettre à jour la clé régulièrement, ce que vous pouvez faire à l’aide de la fonction Réinitialiser la clé sur la page Mon compte.</span><span class="sxs-lookup"><span data-stu-id="4449b-122">We recommend updating the key regularly, which can be done using Reset Key on your My Account page.</span></span>

## <a name="required-metadata-for-items-published-to-the-powershell-gallery"></a><span data-ttu-id="4449b-123">Métadonnées requises pour les articles publiés sur PowerShell Gallery</span><span class="sxs-lookup"><span data-stu-id="4449b-123">Required Metadata for Items Published to the PowerShell Gallery</span></span>

<span data-ttu-id="4449b-124">PowerShell Gallery fournit des informations aux utilisateurs de la galerie tirées des champs de métadonnées qui sont inclus dans le manifeste de module ou du script.</span><span class="sxs-lookup"><span data-stu-id="4449b-124">The PowerShell Gallery provides information to gallery users drawn from metadata fields that are included in the script or module manifest.</span></span>
<span data-ttu-id="4449b-125">Créer ou modifier des éléments pour la publication dans PowerShell Gallery a un petit ensemble de d’exigences pour les informations fournies dans le manifeste de l’élément.</span><span class="sxs-lookup"><span data-stu-id="4449b-125">Creating or modifying items for publication to the PowerShell Gallery has a small set of requirements for information supplied in the item manifest.</span></span> <span data-ttu-id="4449b-126">Nous vous encourageons vivement de consulter la section de métadonnées d’élément des [instructions de publication](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery-PublishingGuidelines) pour apprendre à fournir les meilleures informations aux utilisateurs avec vos éléments.</span><span class="sxs-lookup"><span data-stu-id="4449b-126">We strongly encourage that you review the Item Metadata section of the [Publishing Guidelines](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery-PublishingGuidelines) to learn how to provide the best information to users with your items.</span></span> 

<span data-ttu-id="4449b-127">Les applets de commande [New-ModuleManifest](https://msdn.microsoft.com/en-us/powershell/gallery/psget/module/ModuleManifest-Reference) et [New-ScriptFileInfo](https://msdn.microsoft.com/en-us/powershell/gallery/psget/script/psget_new-scriptfileinfo) créent le modèle de manifeste pour vous, avec des espaces réservés pour tous les éléments du manifeste.</span><span class="sxs-lookup"><span data-stu-id="4449b-127">The [New-ModuleManifest](https://msdn.microsoft.com/en-us/powershell/gallery/psget/module/ModuleManifest-Reference) and [New-ScriptFileInfo](https://msdn.microsoft.com/en-us/powershell/gallery/psget/script/psget_new-scriptfileinfo) cmdlets will create the manifest template for you, with placeholders for all the manifest elements.</span></span> 

<span data-ttu-id="4449b-128">Les deux manifestes ont deux sections qui sont importantes pour la publication, les données de clé primaire et les données PSData de PrivateData. Les données de clé primaire dans un manifeste de module PowerShell représentent tout ce qui se trouve en dehors de la section PrivateData.</span><span class="sxs-lookup"><span data-stu-id="4449b-128">Both manifests have two sections that are important for publishing, the Primary Key Data and PSData area of PrivateData The primary key data in a PowerShell module manifest is everything outside of the PrivateData section.</span></span> <span data-ttu-id="4449b-129">Le jeu de clés primaires est lié à la version de PowerShell en cours d’utilisation et la non-définition n’est donc pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4449b-129">The set of primary keys is tied to the version of PowerShell in use, and undefined are not supported.</span></span> <span data-ttu-id="4449b-130">PrivateData prend en charge l’ajout de nouvelles clés, aussi les éléments spécifiques à PowerShell Gallery se trouvent dans PSData.</span><span class="sxs-lookup"><span data-stu-id="4449b-130">PrivateData supports adding new keys, so the elements specific to the PowerShell Gallery are in PSData.</span></span>


<span data-ttu-id="4449b-131">Les éléments de manifeste les plus importants à remplir pour les éléments à publier dans PowerShell Gallery sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4449b-131">Manifest elements that are most important to fill in for item you publish to the PowerShell Gallery are:</span></span>  

* <span data-ttu-id="4449b-132">Nom du script ou du module - Ces valeurs sont extraites des noms des .PS1 dans le script, ou du .PSD1 pour un module.</span><span class="sxs-lookup"><span data-stu-id="4449b-132">Script or Module Name - Those are drawn from the names of the .PS1 for a script, or the .PSD1 for a module.</span></span>
* <span data-ttu-id="4449b-133">Version - il s’agit d’une clé primaire requise, le format doit suivre les instructions SemVer (voir Meilleures pratiques pour plus d’informations)</span><span class="sxs-lookup"><span data-stu-id="4449b-133">Version - this is a required primary key, format should follow SemVer guidelines (see Best Practices for details)</span></span>
* <span data-ttu-id="4449b-134">Auteur - il s’agit d’une clé primaire requise, elle contient le nom à associer à l’élément (voir Auteurs et Propriétaires, ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="4449b-134">Author - this is a required primary key, and contains the name to be associated with the item (see Authors and Owners, below)</span></span>
* <span data-ttu-id="4449b-135">Description - il s’agit d’une clé primaire requise, utilisée pour expliquer brièvement ce que fait cet élément et les conditions requises pour son utilisation</span><span class="sxs-lookup"><span data-stu-id="4449b-135">Description - this is a required primary key, used to briefly explain what this item does and any requirements for using it</span></span>
* <span data-ttu-id="4449b-136">ProjectURI - il s’agit d’un champ URI fortement recommandé dans PSData qui fournit un lien vers un référentiel Github ou un emplacement similaire où vous effectuez le développement sur l’élément</span><span class="sxs-lookup"><span data-stu-id="4449b-136">ProjectURI - this is a strongly recommended URI field in PSData that provides a link to a Github repo or similar location where you do development on the item</span></span>

<span data-ttu-id="4449b-137">Les Auteurs et Propriétaires d’éléments de PowerShell Gallery sont des concepts connexes, mais ils ne correspondent pas toujours.</span><span class="sxs-lookup"><span data-stu-id="4449b-137">Authors and Owners of PowerShell Gallery items are related concepts, but do not always match.</span></span>  
<span data-ttu-id="4449b-138">Les propriétaires d’élément sont des utilisateurs avec des comptes PowerShell Gallery qui sont autorisés à mettre à jour l’élément.</span><span class="sxs-lookup"><span data-stu-id="4449b-138">Item Owners are users with PowerShell Gallery accounts that have permission to maintain the item.</span></span> <span data-ttu-id="4449b-139">Il peut y avoir de nombreux propriétaires qui peuvent mettre à jour n’importe quel élément.</span><span class="sxs-lookup"><span data-stu-id="4449b-139">There may be many Owners who can update any item.</span></span> <span data-ttu-id="4449b-140">Le propriétaire est uniquement disponible à partir de PowerShell Gallery et est perdu si l’élément est copié d’un système à un autre.</span><span class="sxs-lookup"><span data-stu-id="4449b-140">The Owner is only available from the PowerShell Gallery, and is lost if the item is copied from one system to another.</span></span> <span data-ttu-id="4449b-141">Auteur est une chaîne qui se trouve dans les données de manifeste, et fait donc toujours partie de l’élément.</span><span class="sxs-lookup"><span data-stu-id="4449b-141">Author is a string that is built into the manifest data, so it is always part of the item.</span></span> <span data-ttu-id="4449b-142">Les recommandations pour les éléments des produits Microsoft sont :</span><span class="sxs-lookup"><span data-stu-id="4449b-142">The recommendations for items from Microsoft products are:</span></span>

* <span data-ttu-id="4449b-143">Avoir plusieurs propriétaires, dont au moins un porte le nom de l’équipe qui produit l’élément ;</span><span class="sxs-lookup"><span data-stu-id="4449b-143">Have multiple owners, with at least one being the name of the team that produces the item;</span></span> 
* <span data-ttu-id="4449b-144">Avoir un auteur avec un nom d’équipe connu (par exemple, Équipe du kit de développement logiciel Azure), ou Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="4449b-144">Have the Author be a well-known team name (such as Azure SDK Team), or Microsoft Corporation.</span></span>


## <a name="pre-validate-your-item"></a><span data-ttu-id="4449b-145">Prévalider votre élément</span><span class="sxs-lookup"><span data-stu-id="4449b-145">Pre-Validate Your Item</span></span>

<span data-ttu-id="4449b-146">Il existe certains outils que vous devez exécuter sur votre code avant de publier votre élément dans PowerShell Gallery :</span><span class="sxs-lookup"><span data-stu-id="4449b-146">There are a few tools you need to run against your code before publishing your item to the PowerShell Gallery:</span></span>

* <span data-ttu-id="4449b-147">[L’analyseur de script PowerShell](https://www.powershellgallery.com/packages/PSScriptAnalyzer/), qui se trouve dans PowerShell Gallery</span><span class="sxs-lookup"><span data-stu-id="4449b-147">[PowerShell Script Analyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer/), which is in the PowerShell Gallery</span></span>
* <span data-ttu-id="4449b-148">Pour les modules, Test-ModuleManifest, qui fait partie de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4449b-148">For modules, Test-ModuleManifest which is part of PowerShell</span></span>
* <span data-ttu-id="4449b-149">Pour les scripts, Test-ScriptFileInfo, qui est proposé avec PowerShell Get</span><span class="sxs-lookup"><span data-stu-id="4449b-149">For scripts, Test-ScriptFileInfo which comes with PowerShell Get</span></span>

<span data-ttu-id="4449b-150">[L’analyseur de script PowerShell](https://www.powershellgallery.com/packages/PSScriptAnalyzer/) est un outil d’analyse de code statique qui analyse votre code pour vous assurer qu’il répond aux consignes de base en matière de codage pour PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4449b-150">[PowerShell Script Analyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer/) is a static code analysis tool that will scan your code to ensure it meets basic PowerShell coding guidelines.</span></span> <span data-ttu-id="4449b-151">Cet outil identifie les problèmes courants et critiques dans votre code, et doit être exécuté régulièrement pendant le développement pour vous aider à préparer votre élément pour la publication.</span><span class="sxs-lookup"><span data-stu-id="4449b-151">This tool will identify common and critical issues in your code, and should be run regularly during development to help you get your item ready to publish.</span></span> <span data-ttu-id="4449b-152">L’analyseur de script PowerShell fournit la liste des problèmes identifiés en tant qu’erreurs, avertissements et informations.</span><span class="sxs-lookup"><span data-stu-id="4449b-152">PowerShell Script Analyzer will provide list of issues identified as Errors, Warning, and Information.</span></span> <span data-ttu-id="4449b-153">Toutes les erreurs doivent être traitées avant de publier dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-153">All errors must be addressed before you publish to the PowerShell Gallery.</span></span> <span data-ttu-id="4449b-154">Les avertissements doivent être passés en revue, et la plupart doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="4449b-154">Warnings need to be reviewed, and most should be addressed.</span></span>
<span data-ttu-id="4449b-155">L’analyseur de script PowerShell est exécuté chaque fois qu’un article est publié ou mis à jour dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-155">PowerShell Script Analyzer is run every time an item is published or updated in the PowerShell Gallery.</span></span> <span data-ttu-id="4449b-156">L’équipe des opérations de PowerShell Gallery contacte les propriétaires de l’élément pour corriger les erreurs qui ont été identifiées.</span><span class="sxs-lookup"><span data-stu-id="4449b-156">The Gallery Operations team will contact item owners to address errors that are found.</span></span> 

<span data-ttu-id="4449b-157">Si les informations de manifeste dans votre élément ne peuvent pas être lues par l’infrastructure de PowerShell Gallery, vous ne pourrez pas publier.</span><span class="sxs-lookup"><span data-stu-id="4449b-157">If the manifest information in your item cannot be read by the PowerShell Gallery infrastructure, you will not be able to publish.</span></span> 
<span data-ttu-id="4449b-158">[Test-ModuleManifest](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/test-modulemanifest) intercepte les problèmes courants qui rendraient le module inutilisable lorsqu’il est installé.</span><span class="sxs-lookup"><span data-stu-id="4449b-158">[Test-ModuleManifest](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/test-modulemanifest) will catch common problems that would cause the module to not be usable when it is installed.</span></span> <span data-ttu-id="4449b-159">Il doit être exécuté pour chaque module avant sa publication dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-159">It must be run for every module prior to publishing it to the PowerShell Gallery.</span></span> 

<span data-ttu-id="4449b-160">De même, [Test-ScriptFileInfo](https://msdn.microsoft.com/en-us/powershell/gallery/psget/script/psget_test-scriptfileinfo) valide les métadonnées dans un script et doit être exécuté sur chaque script (publié séparément à partir d’un module) avant sa publication dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-160">Likewise, [Test-ScriptFileInfo](https://msdn.microsoft.com/en-us/powershell/gallery/psget/script/psget_test-scriptfileinfo) validates the metadata in a script, and must be run on every script (published separate from a module) prior to publishing it to the Powershell Gallery.</span></span> 


## <a name="publishing-items"></a><span data-ttu-id="4449b-161">Publication d’éléments</span><span class="sxs-lookup"><span data-stu-id="4449b-161">Publishing Items</span></span>

<span data-ttu-id="4449b-162">Vous devez utiliser [Publish-Script](https://msdn.microsoft.com/en-us/powershell/gallery/psget/script/psget_publish-script) ou [Publish-Module](https://msdn.microsoft.com/en-us/powershell/gallery/psget/module/psget_publish-module) pour publier des éléments dans la PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-162">You must use the [Publish-Script](https://msdn.microsoft.com/en-us/powershell/gallery/psget/script/psget_publish-script) or [Publish-Module](https://msdn.microsoft.com/en-us/powershell/gallery/psget/module/psget_publish-module) to publish items to the PowerShell Gallery.</span></span>
<span data-ttu-id="4449b-163">Ces commandes requièrent</span><span class="sxs-lookup"><span data-stu-id="4449b-163">These commands both require</span></span> 

* <span data-ttu-id="4449b-164">Le chemin d’accès à l’élément que vous allez publier.</span><span class="sxs-lookup"><span data-stu-id="4449b-164">The path to the item you will publish.</span></span> <span data-ttu-id="4449b-165">Pour un module, utilisez le dossier nommé pour votre module.</span><span class="sxs-lookup"><span data-stu-id="4449b-165">For a module, use the folder named for your module.</span></span> <span data-ttu-id="4449b-166">Si vous spécifiez un dossier qui contient plusieurs versions du même module, vous devez spécifier RequiredVersion.</span><span class="sxs-lookup"><span data-stu-id="4449b-166">If you specify a folder that contains multiple versions of the same module, you must specify RequiredVersion.</span></span>
* <span data-ttu-id="4449b-167">Une clé de l’API Nuget.</span><span class="sxs-lookup"><span data-stu-id="4449b-167">A Nuget API key.</span></span> <span data-ttu-id="4449b-168">Il s’agit de la clé d’API qui se trouve sur la page Mon compte dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-168">This is the API key found in the My Account page on the PowerShell Gallery.</span></span>

<span data-ttu-id="4449b-169">La plupart des autres options de la ligne de commande doivent se trouver dans les données de manifeste pour l’élément que vous publiez, il ne devrait donc pas être nécessaire de les spécifier dans la commande.</span><span class="sxs-lookup"><span data-stu-id="4449b-169">Most of the other options in the command line should be in the manifest data for the item you are publishing, so you should not need to specify them in the command.</span></span> 

<span data-ttu-id="4449b-170">Pour éviter les erreurs, il est fortement recommandé d’essayer les commandes avec -Whatif -Verbose avant la publication.</span><span class="sxs-lookup"><span data-stu-id="4449b-170">To avoid errors, it is strongly recommended that you try the commands using -Whatif -Verbose, before publishing.</span></span> <span data-ttu-id="4449b-171">Cela vous fera gagner beaucoup de temps, car vous devez mettre à jour le numéro de version dans la section du manifeste de l’élément chaque fois que vous publiez dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-171">This will seave considerable time, since every time you publish to the PowerShell Gallery, you must update the version number in the manifest section of the item.</span></span> 

<span data-ttu-id="4449b-172">Voici des exemples : 'Publish-Module -Path ".\MonModule" -RequiredVersion "0.0.1" -NugetAPIKey "GUID" -Whatif -Verbose' 'Publish-Script -Path ".\MonScript.PS1" -NugetAPIKey "GUID" -Whatif -Verbose'</span><span class="sxs-lookup"><span data-stu-id="4449b-172">Examples would be: 'Publish-Module -Path ".\MyModule" -RequiredVersion "0.0.1" -NugetAPIKey "GUID" -Whatif -Verbose' 'Publish-Script -Path ".\MyScriptFile.PS1" -NugetAPIKey "GUID" -Whatif -Verbose'</span></span>

<span data-ttu-id="4449b-173">Examinez la sortie avec soin et si vous ne voyez aucune erreur ou avertissement, répétez la commande sans -Whatif.</span><span class="sxs-lookup"><span data-stu-id="4449b-173">Review the output carefully, and if you see no errors or warnings, repeat the command without -Whatif.</span></span>

<span data-ttu-id="4449b-174">Tous les éléments qui sont publiés dans PowerShell Gallery font l’objet d’une analyse antivirus et sont analysés à l’aide de l’analyseur de script PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4449b-174">All items that are published to the PowerShell Gallery will be scanned for viruses, and will be analyzed using the PowerShell Script Analyzer.</span></span> <span data-ttu-id="4449b-175">Les problèmes qui surviennent à ce moment-là sont envoyés à l’éditeur pour résolution.</span><span class="sxs-lookup"><span data-stu-id="4449b-175">Any issues that arise at that time will be sent back to the publisher for resolution.</span></span>  

<span data-ttu-id="4449b-176">Une fois que vous avez publié un élément dans PowerShell Gallery, vous devez consulter les commentaires sur votre élément.</span><span class="sxs-lookup"><span data-stu-id="4449b-176">Once you have published an item to the PowerShell Gallery, you will need to watch for feedback on your item.</span></span>

* <span data-ttu-id="4449b-177">Veillez à surveiller l’adresse de messagerie associée au compte utilisé pour publier.</span><span class="sxs-lookup"><span data-stu-id="4449b-177">Ensure you monitor the email address associated with the account used to publish.</span></span>
<span data-ttu-id="4449b-178">Les utilisateurs et l’équipe des opérations de PowerShell Gallery fournissent des commentaires via ce compte, y compris sur les problèmes de la PSSA ou des analyses antivirus.</span><span class="sxs-lookup"><span data-stu-id="4449b-178">Users, and the PowerShell Gallery Operations team will provide feedback via that account, including issues from the PSSA or antivirus scans.</span></span>
<span data-ttu-id="4449b-179">Si le compte de messagerie n’est pas valide, ou si des problèmes graves sont signalés pour le compte sans être résolus pendant un certain temps, les éléments peuvent être considérés comme abandonnés et être supprimés de PowerShell Gallery comme décrit dans nos [conditions d’utilisation](https://www.powershellgallery.com/policies/Terms).</span><span class="sxs-lookup"><span data-stu-id="4449b-179">If the email account is invalid, or if serious issues are reported to the account and left unresolved for a long time, items can be considered abandoned and will be removed from the PowerShell Gallery as described in our [Terms of Use](https://www.powershellgallery.com/policies/Terms).</span></span>  
* <span data-ttu-id="4449b-180">Nous vous recommandons de vous abonner aux commentaires pour chaque élément de PowerShell Gallery que vous publiez.</span><span class="sxs-lookup"><span data-stu-id="4449b-180">We recommend you subscribe to Comments for each PowerShell Gallery item you publish.</span></span> <span data-ttu-id="4449b-181">Cela vous permet d’être averti si quelqu’un publie des commentaires sur vos éléments dans PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="4449b-181">This allows you to be notified if anyone comments on your items in the PowerShell Gallery.</span></span> <span data-ttu-id="4449b-182">Cela est facultatif, car cela nécessite la création d’un compte avec LiveFyre.</span><span class="sxs-lookup"><span data-stu-id="4449b-182">This is optional, as it requires creating an account with LiveFyre.</span></span>     
