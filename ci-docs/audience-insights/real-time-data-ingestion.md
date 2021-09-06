---
title: Realaus laiko duomenų suvartojimas ir apribojimai
description: Bendra informacija apie realaus laiko galimybes publikos įžvalgose.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 897c876306a39cd9d5842487b96cb2f0a8df7e656de0fb7f10fe8c7f53e2db6b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035287"
---
# <a name="real-time-data-ingestion-preview"></a>Duomenų įtraukimas realiuoju laiku (peržiūra)

Beveik realiojo laiko funkcijos leidžia jums per kelias sekundes pamatyti naujausius klientų veiksmus su jūsų produktais ar paslaugomis.

[Suplanuoti paleidimai iš naujo](system.md#schedule-tab) įtraukiant didelius įrašų skaičius ir keletą sudėtingų veiksmų. Pirmiausia, duomenys yra įtraukiami iš duomenų šaltinio. Tada duomenys sujungiami ir papildomi papildoma informacija. Kiekvieną kartą šis procesas gali trukti nuo kelių minučių iki kelių valandų.

Realaus laiko funkcijos pateikia duomenis nedelsiant suvartojimui, kol tolesnis grafikas iš naujo paleidžia šiuos duomenis iš duomenų šaltinio.

Realiojo laiko atnaujinimai turi galiojimo pabaigos laiką, po kurio jie daugiau neperrašo reikšmės iš duomenų šaltinio.

- Profilio atnaujinimai bus saugomi 4 valandas
- Veiklos bus saugomos 30 dienų

Šios reikšmės yra API skambučių parametrai, kuriuos galite keisti. Jais siekiama užtikrinti, kad jūsų šaltinio duomenys išliktų patikimiausiu šaltiniu. Jei norite, kad realaus laiko naujinimai būtų įtraukti ilgesnį laikotarpį, jums reikia juos įtraukti į duomenų šaltinį taip, kad jie būtų paimami kito suplanuoto paleidimo iš naujo metu.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Sujungto kliento profilio laukų atnaujinimas realiuoju laiku

Naujinti profiliai bus rodomi kliento kortelės rodinyje ar bet kokioje kitoje vizualizacijoje per kelias sekundes.

Kadangi realiojo laiko operacijos vykdomos po duomenų sujungimo, jos taikomos tik sujungtiems klientų profiliams. Todėl profilio pakeitimais realiuoju laiku nebus atnaujinti matai, segmento narystė ar papildymai.

### <a name="limitations"></a>Apribojimai

- Klientų profiliai gali būti atnaujinti, bet ne sukurti ar panaikinti.
- Šiuo metu realiojo laiko atnaujinimų negalima eksportuoti į išorines sistemas, pvz., „Power BI“.

## <a name="real-time-creation-of-activities"></a>Veiklų kūrimas realiuoju laiku

Realaus laiko API leidžia jums publikuoti naują veiklą iš jūsų šaltinio sistemos (atskiro šaltinio įrašo) į suvienodintą kliento profilį. Nauja veikla po kelių sekundžių bus pasiekiama kaip sujungta veikla to sujungto kliento profilio laiko planavimo juostoje. Galite matyti laiko juostą kliento kortelės rodinyje ar bet kokią kitą laiko juostos integravimą, kurį sukonfigūravote.

> [!NOTE]
>
> - Veiklos yra nekintamos. Sukūrus veiklas jos nekeičiamos.
> - Šiuo metu segmentai ir matai nebus atnaujinami pagal naują veiklą.
> - Veiklos, įtrauktos tik per realiojo laiko API, nėra eksportuojamos ir nebus rodomos „PowerBI“.

Yra du būdai sujungti realaus laiko API:

- [netiesiogiai](#connect-via-the-dynamics-365-customer-insights-connector), naudojant [„Dynamics 365 Customer Insights connector“](/connectors/customerinsights/)
- [tiesiogiai](#connect-directly-to-the-real-time-api), naudojant kodą.

Abiems būdams taikomos toliau nurodytos būtinosios sąlygos.

- „Customer Insights“ aplinka
- Sujungti klientų profiliai
- Sukonfigūruotos ir vykdytos veiklos
- Dalyvio ar administratoriaus teisės jūsų klientui autentifikuoti

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Prijungimas naudojant „Dynamics 365 Customer Insights connector“

Realiojo laiko API gali gauti duomenis iš skirtosios „Power Platform“ jungties – [„Dynamics 365 Customer Insights connector“](/connectors/customerinsights/) – ir nereikia kurti ir diegti jokio kodo.    
Jungtis gali atlikti tuos pačius realiojo laiko veiksmus kaip API. Turite turėti galiojančią aukščiausios klasės jungčių licenciją. Daugiau informacijos žr. [DUK apie „Power Apps“ ir „Power Automate“ licencijas](/power-platform/admin/powerapps-flow-licensing-faq).

- „Power Platform“ [„Power Apps“ ir (arba) „Power Automate“](/connectors/)
- „Azure“ [„Logic Apps“](/azure/connectors/apis-list)

Išsamią informaciją apie srautų kūrimą žr. [„Power Automate“ dokumentuose](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Tiesioginis prisijungimas prie realiojo laiko API

Galite naudoti realaus laiko ypatybes sukurdami jūsų nuosavą vamzdyną ir sujungti tiesiogiai realaus laiko API.    
Veiklą galite skelbti savo šaltinio sistemos arba „UnifiedActivity“ formatu. Formatą galite gauti atlikdami API iškvietimą į /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Šio API išsami informacija, įskaitant parametrus ir atsakymus, gali būti surasti **Objektų duomenys** skyriuje [„Customer Insights“ API ataskaitose](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Dėl išsamesnės informacijos, žr. [Darbas su „Customer Insights“ API“](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Telemetrijos naudojimo realiuoju laiku supratimas

Gaukite užklausų apimties apžvalgą realaus laiko API ir informacijai apie problemas, su kuriomis gali susidurti sistema. Galite [prieiti prie telemetrijos realiuoju laiku](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]