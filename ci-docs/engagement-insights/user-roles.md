---
title: Vaidmenys ir teisės
description: Galimų darbo srities narių vaidmenų ir teisių apžvalga.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036703"
---
# <a name="roles-and-permissions"></a>Vaidmenys ir teisės

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Darbo sritis yra tai, kaip valdote ir talpinate įvykius ir ataskaitas. Darbo srities narys yra vartotojas, kuris gali pasiekti darbo sritį. Galite priskirti narius savo darbo vietai ir apibrėžti jų vaidmenis bei teises. Administratoriaus vaidmenys valdo darbo sritis ir aplinkas bei konfigūruoja įtraukimo įžvalgas kitiems vartotojams. Bendradarbių vaidmenys yra orientuoti į analitikus, kuriems nereikia konfigūruoti įtraukimo įžvalgų, bet kurie nori kurti savo ataskaitas, piltuvėlius ar segmentus.

## <a name="permissions"></a>Teisės
  
Šioje diagramoje nustatomos kiekvieno vaidmens teisės. 

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
