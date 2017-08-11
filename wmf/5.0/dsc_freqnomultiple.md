---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: wmf,powershell,configuration
ms.openlocfilehash: 30055cff87159df98029e25409782e0fe2f0bae4
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2017
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a><span data-ttu-id="69554-102">Les fréquences pour RefreshMode et ConfigurationMode ne doivent pas nécessairement être des multiples les unes des autres</span><span class="sxs-lookup"><span data-stu-id="69554-102">Frequencies for RefreshMode and ConfigurationMode don't need to be multiples of each other</span></span>

<span data-ttu-id="69554-103">Dans la version précédente de DSC, le gestionnaire de configuration local traitait `RefreshFrequencyMins` et `ConfigurationModeFrequencyMins` comme des multiples.</span><span class="sxs-lookup"><span data-stu-id="69554-103">In the previous version of DSC, the LCM would treat `RefreshFrequencyMins` and `ConfigurationModeFrequencyMins` as multiples of each other.</span></span> <span data-ttu-id="69554-104">Dans WMF 5.0 RTM, ces propriétés sont traitées indépendamment l’une de l’autre.</span><span class="sxs-lookup"><span data-stu-id="69554-104">In WMF 5.0 RTM, these properties are processed independent of each other.</span></span> 

<span data-ttu-id="69554-105">Pour plus d’informations, consultez [Configuration du Gestionnaire de configuration local](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span><span class="sxs-lookup"><span data-stu-id="69554-105">For more information, see [Configuring the Local Configuration Manager](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span></span>
