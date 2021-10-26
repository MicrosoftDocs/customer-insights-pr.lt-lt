---
title: Vaidmenys ir teisės
description: Galimų darbo srities narių vaidmenų ir teisių apžvalga.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645547"
---
# <a name="roles-and-permissions"></a>Vaidmenys ir teisės

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tai Darbo sritis yra vieta įvykiams ir ataskaitoms saugoti ir valdyti. Daugiau informacijos žr. dalyje [Darbo srities kūrimas ir narių įtraukimas](create-workspace.md). 

Darbo srityje gali būti šie vaidmenys ir teisės:

- *Narių* vaidmenys yra vartotojai, galintiems pasiekti darbo sritį. Galite priskirti narius savo darbo vietai ir apibrėžti jų vaidmenis bei teises. 
- *Administratoriaus* vaidmenys valdo darbo sritis ir aplinkas bei konfigūruoja įtraukimo įžvalgas kitiems vartotojams. 
- *Bendradarbių* vaidmenys yra orientuoti į analitus, kuriems nereikia konfigūruoti įtraukimo įžvalgų, bet kurie nori kurti savo ataskaitas, piltuvėlio ar segmentų.

## <a name="permissions"></a>Teisės
  
Toliau esančioje lentelėje nustatomos kiekvieno vaidmens teisės. 

| Teisė | Aplinkos administratorius | Darbo srities administratorius | Aplinkos bendraautorius | Darbo srities bendraautorius | 
|--|--|--|--|--|
| Aplinkos kūrimas (kūrėjas automatiškai tampa aplinkos administratoriumi) | X* | X* | X* | X* |  
| Konfigūruoti aplinką (aplinkos narius, naikinti aplinką) | X |  |  |  |  
| Kurti darbo sritis | X |  |  |  |  
| Darbo sričių konfigūravimas (darbo srities nariai, darbo srities naikinimas) | X | X |  |  |  
| Konfigūruokite įvykius ir patobulinkite įvykius | X | X | |  |  
| Darbo srities įvykių ir tikslinių įvykių rodinys | X | X | |  |  
| Darbo srities išteklių (ataskaitų, segmentų ir metrikos) peržiūra| X | X | X | X |  
| Kurti pasirinktines ataskaitas ir piltuvėlius | X | X | X | X |  
| Kurkite pagrindinę metriką ir dimensijas| X | X |  |  |  
| Kurti segmentus| X | X | X | X |  

*Gali kurti tik bandomosios versijos aplinkas. 

## <a name="add-members"></a>Įtraukti narių

Galite įtraukti arba pašalinti narius iš darbo sričių ir aplinkos. Daugiau informacijos žr. [Aplinkų ir darbo sričių valdymas](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
