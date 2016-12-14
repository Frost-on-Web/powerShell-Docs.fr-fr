---
title: Windows Management Framework (WMF)
ms.date: 2016-05-16
keywords: PowerShell, WMF
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: eacd33d2a0a92977a3990132e23eef9871a7f0dc
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="windows-management-framework"></a>Windows Management Framework

Windows Management Framework (WMF) est le mécanisme de remise qui fournit une interface de gestion cohérente sur les différentes versions de Windows et Windows Server.
Quand WMF est installé, les clients peuvent interagir de manière transparente entre des combinaisons de systèmes d’exploitation dans leur environnement.
WMF rend les mises à jour des fonctionnalités de gestion, dans une version donnée de Windows et Windows Server, disponibles pour installation sur des versions inférieures (en général, deux versions inférieures) de Windows et Windows Server.

L’installation de WMF ajoute ou met à jour les fonctionnalités suivantes :

- Windows PowerShell
- Configuration de l’état souhaité de Windows PowerShell (DSC)
- Windows PowerShell Integrated Script Environment (ISE)
- Windows Remote Management (WinRM)
- Infrastructure de gestion Windows (WMI, Windows Management Instrumentation)
- Windows PowerShell Web Services (Extension ISS Management OData)
- Journalisation de l’inventaire logiciel
- Fournisseur CIM de Gestionnaire de serveur

## <a name="wmf-release-notes"></a>Notes de publication de WMF
Pour en savoir plus sur les diverses améliorations apportées à PowerShell et d’autres composants d’une version donnée de WMF, consultez les liens ci-dessous pour consulter les notes de publication :


- [WMF 5.1 (préversion)](5.1/release-notes.md)
- [WMF 5.0](5.0/releasenotes.md)


## <a name="wmf-availability-across-windows-operating-systems"></a>Disponibilité de WMF sur les systèmes d’exploitation Windows

>TODO : Ajouter des liens vers des DLC WMF spécifiques sur l’en-tête de colonne

| Version du système d'exploitation | [WMF 5.1 Preview*]() | [WMF 5.0]() | [WMF 4.0]() |  [WMF 3.0]() | [WMF (2.0)]() |
| ------------------------ | ----------- | ----------- | ----------- | ------------ |  ------------- |
| Windows Server 2016 | Fourni par défaut* | Fourni par défaut* |  |  |  |
| Windows 10 | Fourni par défaut* | Fourni par défaut*  | | | |  
| Windows Server 2012 R2| ?? | Oui | Fourni par défaut |  |  |
| Windows 8.1 | ?? | Oui |  Fourni par défaut |  |  |
| Windows Server 2012 | ?? | Oui | Oui |  Fourni par défaut | |
| Windows 8 |  |  |  | Fourni par défaut | |
| Windows Server 2008 R2 SP1 | ?? | Oui | Oui |  Oui| Fourni par défaut |
| Windows 7 SP1  | ?? | Oui | Oui | Oui | Fourni par défaut |
| Windows Server 2008 SP2 | | | | Oui | Oui |
| Windows Vista | | | | | Oui |
| Windows Server 2003| | | |  | Oui |
| Windows XP | | | |  | Oui |

>TODO : Expliquer * dans le tableau ci-dessus
