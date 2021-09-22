---
title: Žiniatinklio įvykių atpažinimas iš anksčiau autentifikuotų lankytojų su funkcija „Nuo nežinomo iki žinomo”
description: Funkcija „Nuo nežinomo iki žinomo” leidžia jums susieti įvykius žiniatinklio svetainėje su anksčiau autentifikuotais lankytojais.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036793"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Žiniatinklio įvykių atpažinimas iš anksčiau autentifikuotų lankytojų

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Įtraukimo įžvalgų pajėgumo funkcija **„Nuo nežinomo iki žinomo”** leidžia susieti žiniatinklio įvykius su anksčiau autentifikuotais lankytojais. Jei funkcija išjungta, lankytojai, kurie autentifikavosi ankstesnio vizito metu, o tada išėjo iš svetainės, nėra identifikuojami, jeigu jie vėl nesiautentifikuoja sugrįžę. 

Pavyzdžiui, praėjusią savaitę asmuo lankėsi žiniatinklio svetainėje, prisijungė prie savo vartotojo paskyros ir naršė produktų katalogą. Kitą savaitę asmuo sugrįžta ir naršo daugiau produktų neprisijungęs prie savo paskyros. Svetainės savininkas, naudojantis **„Nuo nežinomo iki žinomo”** funkciją, žinos, kad tas pats asmuo grįžo ir tai, ką jis atliko svetainėje. Tai leidžia tiksliau teikti ataskaitas ir analizuoti svetainės veiklas.

## <a name="enable-unknown-to-known"></a>„Nuo nežinomo iki žinomo” įgalinimas

Turite būti [darbo srities administratorius](user-roles.md), kad įjungtumėte šią funkciją. 

1. Įtraukimo įžvalgose eikite į **Administratorius** > **Darbo sritis**. 
2. Pasirinkite **Parametrų** skirtuką.
3. Skyriuje **„Nuo nežinomo iki žinomo”** nustatykite perjungiklį į **Įgalinta**.

![„Nuo nežinomo iki žinomo” įgalinimas](media/U2Ktoggle.png "„Nuo nežinomo iki žinomo” įgalinimas")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>„JavaScript” kodo įtraukimas į jūsų svetainės sekimo fragmentą

Žiniatinklio svetainėje galima užfiksuoti **vartotojo „authId”** su toliau pateiktu „JavaScript” pavyzdžiu naudojant [įtraukimo įžvalgų žiniatinklio SDK](advanced-SDK-implementation.md). Tam, kad funkcija **„Nuo nežinomo iki žinomo”** veiktų, jūs turite užfiksuoti „authId” *ir* įgalinti „userMapping:True” savo „JavaScript” fragmente, kaip nurodyta toliau pateiktame pavyzdyje.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
