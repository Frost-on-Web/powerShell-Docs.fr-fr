---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: wmf,powershell,setup
ms.openlocfilehash: 4e0c1638bf10e57580a463c46595ac9bc142a5b4
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="just-enough-administration-jea"></a><span data-ttu-id="9461d-102">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="9461d-102">Just Enough Administration (JEA)</span></span>
<span data-ttu-id="9461d-103">Just Enough Administration est une nouvelle fonctionnalité de WMF 5.0 qui autorise l’administration basée sur des rôles par le biais de l’accès distant PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9461d-103">Just Enough Administration is a new feature in WMF 5.0 that enables role-based administration through PowerShell remoting.</span></span>  <span data-ttu-id="9461d-104">Elle étend l’infrastructure de point de terminaison contrainte existante en autorisant les utilisateurs non-administrateurs à exécuter des commandes, des scripts et des exécutables spécifiques en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9461d-104">It extends the existing constrained endpoint infrastructure by allowing non-administrators to run specific commands, scripts and executables as an administrator.</span></span>  <span data-ttu-id="9461d-105">Cela vous permet de réduire le nombre d’administrateurs complets dans votre environnement et d’améliorer la sécurité.</span><span class="sxs-lookup"><span data-stu-id="9461d-105">This enables you to reduce the number of full administrators in your environment and improve your security.</span></span>  <span data-ttu-id="9461d-106">JEA fonctionne pour tout ce que vous gérez par le biais de PowerShell. Si vous pouvez gérer quelque chose avec PowerShell, JEA peut vous aider à le faire de manière plus sécurisée.</span><span class="sxs-lookup"><span data-stu-id="9461d-106">JEA works for everything you manage through PowerShell; if you can manage something with PowerShell, JEA can help you do so more securely.</span></span>  <span data-ttu-id="9461d-107">Pour découvrir Just Enough Administration de manière détaillée, consultez le [guide d’expérience](http://aka.ms/JEA).</span><span class="sxs-lookup"><span data-stu-id="9461d-107">For a detailed look at Just Enough Administration, check out the [experience guide](http://aka.ms/JEA).</span></span>

<span data-ttu-id="9461d-108">Contrairement aux anciens points de terminaison contraints, JEA est à la fois puissant et facile à configurer.</span><span class="sxs-lookup"><span data-stu-id="9461d-108">Unlike old constrained endpoints, JEA is both powerful and easy to configure.</span></span>  <span data-ttu-id="9461d-109">Les fonctionnalités utilisateur dans JEA peuvent être contrôlées de manière granulaire, jusqu’à limiter les jeux de paramètres et les valeurs qui peuvent être fournis à une commande spécifique.</span><span class="sxs-lookup"><span data-stu-id="9461d-109">User capabilities in JEA can be granularly controlled, down to restricting which parameter sets and values can be supplied to a specific command.</span></span> <span data-ttu-id="9461d-110">Les actions de l’utilisateur sont exécutées dans le contexte d’un compte virtuel ponctuel qui est autorisé à effectuer les actions d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9461d-110">The user’s actions are run in the context of a one-time virtual account that has the rights to perform the administrator actions.</span></span>  <span data-ttu-id="9461d-111">Vous pouvez enregistrer les commandes appelées par l’utilisateur dans un journal afin d’effectuer un audit de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9461d-111">The commands invoked by the user can be logged for security audits.</span></span>

<span data-ttu-id="9461d-112">JEA vous permet de créer des points de terminaison contraints spécialement configurés.</span><span class="sxs-lookup"><span data-stu-id="9461d-112">JEA works by allowing you to create specially-configured constrained endpoints.</span></span>  <span data-ttu-id="9461d-113">Ces points de terminaison ont quelques caractéristiques importantes :</span><span class="sxs-lookup"><span data-stu-id="9461d-113">These endpoints have a few important characteristics:</span></span>

1. <span data-ttu-id="9461d-114">Les utilisateurs qui s’y connectent « s’exécutent en tant que » compte privilégié virtuel qui existe uniquement pendant la durée de la session à distance.</span><span class="sxs-lookup"><span data-stu-id="9461d-114">Users connecting to them “run as” a privileged Virtual Account that exists only for the duration of this remote session.</span></span>  <span data-ttu-id="9461d-115">Par défaut, ce compte virtuel est membre du groupe Administrateurs intégré, et également administrateur de domaine sur les contrôleurs de domaine (notez que ces autorisations sont configurables).</span><span class="sxs-lookup"><span data-stu-id="9461d-115">By default, this Virtual Account is a member of the built-in Administrators group, as well as a Domain Administrators on domain controllers (note: these permissions are configurable).</span></span> <span data-ttu-id="9461d-116">Le fait de se connecter sous un utilisateur et de s’exécuter en tant qu’autre utilisateur privilégié permet aux utilisateurs sans privilèges d’effectuer des tâches administratives spécifiques sans que des droits d’administration leur soient accordés sur vos systèmes.</span><span class="sxs-lookup"><span data-stu-id="9461d-116">By connecting as one user and running as a different, privileged user, you can allow non-privileged users to perform specific administrative tasks without giving them administrative rights on your systems.</span></span>
2. <span data-ttu-id="9461d-117">Le point de terminaison est verrouillé.</span><span class="sxs-lookup"><span data-stu-id="9461d-117">The endpoint is locked down.</span></span>  <span data-ttu-id="9461d-118">Cela signifie que PowerShell s’exécute en mode sans langage.</span><span class="sxs-lookup"><span data-stu-id="9461d-118">This means PowerShell runs in No Language mode.</span></span>  <span data-ttu-id="9461d-119">Seuls des commandes, scripts et exécutables spécifiques sont visibles par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9461d-119">Only specific commands, scripts, and executables are visible to the user.</span></span>
3. <span data-ttu-id="9461d-120">Des ensembles de capacités différents sont présentés aux utilisateurs qui se connectent en fonction de l’appartenance au groupe.</span><span class="sxs-lookup"><span data-stu-id="9461d-120">Different users connecting are presented with a different set of capabilities based on group membership.</span></span>  <span data-ttu-id="9461d-121">Vous pouvez fournir différentes capacités à différents rôles sur le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="9461d-121">You can provide different roles different capabilities at the same endpoint.</span></span>
