---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: wmf,powershell,setup
ms.openlocfilehash: 403a79e17b832b5c58fd21a138fcebb8adb76d40
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="call-base-class-constructor"></a><span data-ttu-id="fb05b-102">Appeler un constructeur de classe de base</span><span class="sxs-lookup"><span data-stu-id="fb05b-102">Call Base Class Constructor</span></span>

<span data-ttu-id="fb05b-103">Pour appeler un constructeur de classe de base à partir d’une sous-classe, utilisez le mot clé **base** :</span><span class="sxs-lookup"><span data-stu-id="fb05b-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

```PowerShell
class A 
{
    [int]$a

    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

[B]::new().a # return 103
```

<span data-ttu-id="fb05b-104">Si une classe de base a un constructeur par défaut (sans paramètre), vous pouvez omettre un appel de constructeur explicite :</span><span class="sxs-lookup"><span data-stu-id="fb05b-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```PowerShell
class C : B
{
    C([int]$c) {}
}
```

