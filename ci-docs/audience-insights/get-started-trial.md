---
title: Bandomosios „Customer Insights” versijos kūrimas ir konfigūravimas
description: Veiksmai norint gauti bandomąją „Dynamics 365 Customer Insights” prenumeratą ir sukonfigūruoti ją.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558833"
---
# <a name="set-up-a-trial-environment"></a>Bandomosios aplinkos nustatymas 

Bandomoji „Dynamics 365 Customer Insights” versija leidžia jums peržiūrėti pagrindines galimybes ir sužinoti daugiau apie įvairias funkcijas. Pasibaigus bandomosios versijos prenumeratai, ji panaikinama. Bandomosios versijos aplinkas sukuria atskiri vartotojai, kurie tampa bandomosios versijos aplinkos administratoriais. Jie gali pakviesti daugiau vartotojų į savo bandomąją versiją ir sukonfigūruoti įvairias funkcijas.

## <a name="create-a-trial-environment"></a>Bandomosios aplinkos kūrimas

Galite prisiregistruoti naudoti bandomąją versiją [bandomosios versijos registracijos puslapyje](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Pasirinkite parinktį **Prisiregistruoti nemokamai naudoti bandomąją versiją** ir pasirinkite **Prisiregistruoti dabar**.

1. Pateikite savo darbo arba mokymo įstaigos elektroninio pašto adresą, papasakokite daugiau apie save ir pasirinkite **Pradėti**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Susisiekite užsiregistruoti nemokamai bandomajai versijai gauti":::

1. Peržiūrėkite sąlygas ir pasirinkite **Tęsti** patvirtinimui.

1. Įveskite naujos aplinkos **pavadinimą**. 

1. Nustatykite aplinkos **Tipą** į **Bandomąją versiją**.

1. Lauke **Pasirinkti pramonės šakos demonstracinius duomenis** galite pasirinktinai pažymėti pramonės šakai būdingą duomenų rinkinį. Taip pat galite [pakeisti pramonės šakos demonstracinius duomenis](#use-industry-specific-demo-data-sets-in-audience-insights) vėliau ir pradėti nuo numatytojo duomenų rinkinio.

1. Pasirinkite aplinkos **sritį**.

1. Pasirinktinai, jei esate „Dynamics 365” organizacijos administratorius: Pasirinkite **Išplėstiniai parametrai** ir pateikite savo organizacijos URL, kad naudotumėte prognozės funkcijas, pavyzdžiui, klientų praradimo prognozę. 

1. Pasirinkite **Kurti**. 

Aplinkos nustatymas užtrunka kelias minutes. Jį užbaigę būsite nukreipti į demonstracinę aplinką arba pramonės šakos demonstracinę versiją, kurią pasirinkote atlikdami aukščiau pateiktą veiksmą. Dabar galite naršyti programą naudodami tik skaitomus demonstracinius duomenis. Norėdami įtraukti savo duomenis į aplinką, skaitykite [Konkrečių scenarijų demonstracinių duomenų kūrimas jūsų aplinkoje](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Naujai sukurtos bandomosios versijos aplinkos ekrano kopija.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Pramonės šakoms būdingų demonstracinių duomenų rinkinių naudojimas auditorijos įžvalgose

Realių duomenų šaltinių prijungimas yra vienas iš svarbiausių veiksmų naudojant „Customer Insights” pajėgumą. Norėdami išbandyti funkcijas nenaudodami savo duomenų, galite pasirinktinai naudoti pramonės šakoms būdingus demonstracinius duomenis. Yra keletas demonstracinių duomenų rinkinių, galimų toliau nurodytoms pramonės šakoms: 

-   Automobilių
-   Bankininkystė
-   Vartojimo Prekės
-   Valstybinė institucija
-   Sveikatos priežiūros
-   Svetingumas
-   Draudimas
-   Gamybos
-   Profesionalios Paslaugos
-   Mažmeninė prekyba

### <a name="see-industry-specific-demo-data-in-trials"></a>Peržiūrėkite pramonės šakai būdingus demonstracinius duomenis bandomosiose versijose

Tik skaitomai „Customer Insights” versijai, specialiai pritaikytai konkrečiai pramonės šakai arba scenarijui, pradėkite ją Demonstracinėje aplinkoje. 
 
1.  Auditorijos įžvalgose pasirinkite **Demonstracinę** aplinką iš aplinkų parinkiklio.

2.  Iš **Pagrindinio puslapio** išplečiamojo meniu Pasirinkti pramonės šakos demonstracinius duomenis pažymėkite parinktį.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Pasirinkite pramonės šaką bandomosios versijos aplinkai.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Scenarijui būdingų demonstracinių duomenų kūrimas jūsų aplinkoje

Norėdami sukurti naują aplinką, kaip administratorius programos antraštėje pasirinkite aplinkos parinkiklį. Naujoje aplinkoje galite konfigūruoti savo duomenų šaltinius ir nustatyti programą pagal savo reikalavimus. 

1.  Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2.  Norėdami importuoti savo duomenų šaltinius, eikite į [duomenų įtraukimo vadovą](data-sources.md).     
   Jei norite dirbti su duomenų pavyzdžiais, kurie leidžia išbandyti duomenų perkėlimą, galite perkelti pramonės šakos demonstracinius duomenis savo aplinkoje. Pasirinkite **Importuoti iš „Datahub”** parinktį ir atlikite toliau nurodytus veiksmus.

3.  Pažymėkite pramonės šakos kortelę, kuri atitinka jūsų scenarijų. 

4.  Peržiūrėkite ir pasirinktinai atnaujinkite siūlomą duomenų šaltinio pavadinimą. 

5.  Pažymėkite **Kitas**, kad perkeltumėte pavyzdinius duomenis. 

Dabar galite naudoti perkeltus duomenis, kad specialiai pritaikytumėte „Customer Insights” prie savo scenarijaus. Norėdami matyti konkrečią aplinką įtrauktiems demonstraciniams duomenims, pasirinkite **<Industry> Demonstraciniai duomenys** aplinkų parinkiklyje.

## <a name="limitations-in-trials"></a>Bandomųjų versijų apribojimai

- Pagal numatytuosius nustatymus, bandomosios versijos yra aktyvios 30 dienų. Tačiau galite jas pratęsti po 23 dienų prisijungę prie savo bandomosios versijos.
- Negalite naudoti savo „Azure Data Lake storage” paskyros išvesties duomenims saugoti bandomosios versijos metu. Tačiau duomenis galite įtraukti iš „Data Lake storage” paskyros.
- Aplinkoje, kuri automatiškai pateikiama paleidus „Customer Insights" bandomąją versiją, galite saugoti iki 3 GB „Dataverse“ duomenų.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Duomenų kopijavimas iš bandomosios versijos į mokamą prenumeratą

Paprastai rekomenduojame pradėti su naujais duomenimis atnaujinus į mokamą „Customer Insights” versiją. 

Įsigiję „Customer Insights” galite pasirinktinai kopijuoti duomenis iš bandomosios versijos aplinkos. Turite būti „Customer Insights” bandomosios versijos administratorius ir visuotinis jūsų „Microsoft 365” nuomotojo administratorius arba savo organizacijos „Dynamics 365” administratorius, kad perkeltumėte parametrus iš bandomosios aplinkos į mokamą aplinką. 

Pirmą kartą prisijungus prie savo apmokėto „Customer Insights” egzemplioriaus, jūsų bus paprašyta sukurti naują aplinką. Šiame procese jūs galite pasirinkti kopijuoti konfigūraciją iš esamos aplinkos ir perkelti daugumą parametrų. Jei jūs turite aukščiau minimas teises, šiame sąraše bus rodoma bandomosios versijos aplinka. Daugiau informacijos rasite [Aplinkos konfigūravimo kopijavimas](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Tolesni veiksmai

Peržiūrėkite šiuos straipsnius, kad galėtumėte pradėti konfigūruoti „Customer Insights”. 

- [Įtraukite daugiau vartotojų ir priskirkite teises](permissions.md).
- [Įtraukite savo duomenų šaltinius](data-sources.md) ir paleiskite juos per [duomenų suvienodinimo procesą](data-unification.md), kad gautumėte [suvienodintus klientų profilius](customer-profiles.md).
- [Papildykite vieninguosius klientų profilius](enrichment-hub.md) arba [paleiskite numatomus modelius](predictions-overview.md).
- Kurkite [segmentus](segments.md), kad sugrupuotumėte klientus ir [priemones](measures.md) KPI peržiūrai.
- Nustatykite [ryšius](connections.md) ir [eksportavimus](export-destinations.md), kad kitose taikomosiose programose būtų apdorojami antriniai duomenų rinkiniai.
