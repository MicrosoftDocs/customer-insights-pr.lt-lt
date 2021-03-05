---
title: Realaus laiko duomenų suvartojimas ir apribojimai
description: Bendra informacija apie relaus laiko galimybes publikos įžvalgose.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270290"
---
# <a name="real-time-data-ingestion-preview"></a>Duomenų įtraukimas realiuoju laiku (peržiūra)

Beveik realiojo laiko funkcijos leidžia jums per kelias sekundes pamatyti naujausius klientų veiksmus su jūsų produktais ar paslaugomis.

[Suplanuoti paleidimai iš naujo](system.md#schedule-tab) įtraukiant didelius įrašų skaičius ir keletą sudėtingų veiksmų. Pirmiausia, duomenys yra įtraukiami iš duomenų šaltinio. Tada duomenys sujungiami ir papildomi papildoma informacija. Kiekvieną kartą šis procesas gali trukti nuo kelių minučių iki kelių valandų.

Realaus laiko funkcijos pateikia duomenis nedelsiant suvartojimui, kol tolesnis grafikas iš naujo paleidžia šiuos duomenis iš duomenų šaltinio.

Realiojo laiko atnaujinimai turi galiojimo pabaigos laiką, po kurio jie daugiau neperrašo reikšmės iš duomenų šaltinio.

- Profilio atnaujinimai bus saugomi 4 valandas
- Veiklos bus saugomos 30 dienų

Šios reikšmės yra API skambučių parametrai, kuriuos galite keisti. Jais siekiama užtikrinti, kad jūsų šaltinio duomenys išliktų patikimiausiu šaltiniu. Jei norite, kad realaus laiko naujinimai būtų įtraukti ilgesnį laikotarpį, jums reikia juso įtraukti į duomenų šaltinį taip, kad jie būtų paimami kito suplanuoto paleidimo iš naujo metu.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Sujungto kliento profilio laukų atnaujinimas realiuoju laiku

Naujinti profiliai bus rodomi kliento kortelės rodinyje ar bet kokioje kitoje vizualizacijoje per kelias sekundes.

Kadangi realiojo laiko operacijos vykdomos po duomenų sujungimo, jos taikomos tik sujungtiems klientų profiliams. Todėl profilio pakeitimais realiuoju laiku nebus atnaujinti matai, segmento narystė ar papildymai.

### <a name="limitations"></a>Apribojimai

- Klientų profiliai gali būti atnaujinti, bet ne sukurti ar panaikinti.
- Šiuo metu realiojo laiko atnaujinimų negalima eksportuoti į išorines sistemas, pvz., „Power BI“.

## <a name="real-time-creation-of-activities"></a>Veiklų kūrimas realiuoju laiku

Realaus laiko API leidžia jums publikuoti naują veiklą iš jūsų šaltinio sistemos (atskiro šaltinio įrašo) į suvienodintą kliento profilį. Nauja veikla po kelių sekundžių bus pasiekiama kaip sujungta veikla to sujungto kliento profilio laiko planavimo juostoje. Galite matyti laiko jusotą kliento kortelės rodinyje ar bet kokią kitą laiko juostos integravimą, kurį sukonfigūravote.

> [!NOTE]
>
> - Veiklos yra nekintamos. Sukūrus veiklas jos nekeičiamos.
> - Šiuo metu segmentai ir matai nebus atnaujinami pagal naują veiklą.
> - Veiklos, įtrauktos tik per realiojo laiko API, nėra eksportuojamos ir nebus rodomos „PowerBI“.

Yra du būdai sujungti realaus laiko API:

- [netiesiogiai](#connect-via-the-dynamics-365-customer-insights-connector), naudojant [„Dynamics 365 Customer Insights“ jungtį](https://docs.microsoft.com/connectors/customerinsights/)
- [tiesiogiai](#connect-directly-to-the-real-time-api), naudojant kodą.

Abiems būdams taikomos toliau nurodytos būtinosios sąlygos.

- „Customer Insights“ aplinka
- Sujungti klientų profiliai
- Sukonfigūruotos ir vykdytos veiklos
- Dalyvio ar administratoriaus teisės jūsų klientui autentifikuoti

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Prijungimas naudojant „Dynamics 365 Customer Insights“ jungtį

Realiojo laiko API gali gauti duomenis iš skirtosios „Power Platform“ jungties – [„Dynamics 365 Customer Insights“ jungties](https://docs.microsoft.com/connectors/customerinsights/) – ir nereikia kurti ir diegti jokio kodo.    
Jungtis gali atlikti tuos pačius realiojo laiko veiksmus kaip API. Turite turėti galiojančią aukščiausios klasės jungčių licenciją. Daugiau informacijos žr. [DUK apie „Power Apps“ ir „Power Automate“ licencijas](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- „Power Platform“ [„Power Apps“ ir (arba) „Power Automate“](https://docs.microsoft.com/connectors/)
- „Azure“ [„Logic Apps“](https://docs.microsoft.com/azure/connectors/apis-list)

Išsamią informaciją apie srautų kūrimą žr. [„Power Automate“ dokumentuose](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Tiesioginis prisijungimas prie realiojo laiko API

Galite naudoti realaus laiko ypatybes sukurdami jūsų nuosavą vamzdyną ir sujungti tiesiogiai realaus laiko API.    
Veiklą galite skelbti savo šaltinio sistemos arba „UnifiedActivity“ formatu. Formatą galite gauti atlikdami API iškvietimą į /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Šio API išsami informacija, įskaitant parametrus ir atsakymus, gali būti surasti **Objektų duomenys** skyriuje [„Customer Insights“ API ataskaitose](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Dėl išsamesnės informacijos, žr. [Darbas su „Customer Insights“ API“](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Telemetrijos naudojimo realiuoju laiku supratimas

Gaukite užklausų apimties apžvalgą realaus laiko API ir informacijai apie problemas, su kuriomis gali susidurti sistema. Galite [prieiti prie telemetrijos realiuoju laiku](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]