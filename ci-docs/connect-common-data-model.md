---
title: Jungimasis prie „Common Data Model” aplanko naudojant „Azure Data Lake” klientą
description: Dirbkite su „Common Data Model“ duomenimis naudodami „Azure Data Lake Storage“.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082264"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Jungtis prie duomenų „Azure Data Lake Storage“

Prarykite duomenis, kad Dynamics 365 Customer Insights galėtumėte naudotis savo Azure Data Lake Storage Gen2 paskyra. Duomenų nurijimas gali būti pilnas arba laipsniškas.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Duomenų įsisavinimas palaiko Azure Data Lake Storage *tik Gen2* paskyras. Negalite naudoti "Data Lake Storage Gen1" paskyrų duomenims nuryti.

- Abonemente Azure Data Lake Storage [turi būti įgalinta hierarchinė vardų sritis](/azure/storage/blobs/data-lake-storage-namespace). Duomenys turi būti saugomi hierarchiniu aplanko formatu, kuris apibrėžia šakninį aplanką ir turi kiekvieno objekto poaplankius. Poaplankiuose gali būti pilni duomenys arba papildomi duomenų aplankai.

- Norėdami autentifikuoti su „Azure“ pagrindinėmis paslaugomis, įsitikinkite, kad sukonfigūravote jas savo nuomotojuje. Norėdami gauti daugiau informacijos, žiūrėkite [Prisijungimas Azure Data Lake Storage prie Gen2 paskyros naudojant "Azure" paslaugos vykdytoją](connect-service-principal.md).

- Norite Azure Data Lake Storage prisijungti ir praryti duomenis iš jų turi būti tame pačiame "Azure" regione kaip ir Dynamics 365 Customer Insights aplinka. Ryšiai su „Common Data Model“ katalogu iš kito „Azure“ regiono duomenų telkinio nėra palaikomi. Norėdami sužinoti aplinkos "Azure" regioną, eikite į **"Customer Insights" administravimo** > **sistemą** > **apie**.

- Internetinėse paslaugose saugomi duomenys gali būti saugomi kitoje vietoje nei ten, kur duomenys tvarkomi ar saugomi Dynamics 365 Customer Insights.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse paslaugose, jūs sutinkate, kad duomenys gali būti perduodami ir saugomi su Dynamics 365 Customer Insights. [Sužinokite daugiau "Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).

- "Customer Insights" paslaugos vykdytojas turi būti viename iš toliau nurodytų vaidmenų, kad galėtų pasiekti saugyklos paskyrą. Daugiau informacijos ieškokite [Teisių suteikimas paslaugos vykdytojui, kad jis galėtų pasiekti saugyklos paskyrą](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - „Storage Blob Data“ skaitytojas
  - „Storage Blob Data“ savininkas
  - „Storage Blob Data“ pildytojas

- Jūsų duomenų ežero saugykloje esantys duomenys turėtų atitikti "Common Data Model" standartą, skirtą jūsų duomenims saugoti, ir turėti bendrą duomenų modelio manifestą, kuris atspindėtų duomenų failų schemą (*.csv arba *.parketas). Manifeste turi būti pateikta išsami informacija apie objektus, pvz., objekto stulpelius ir duomenų tipus, duomenų failo vieta ir failo tipas. Daugiau informacijos ieškokite ["Common Data Model" manifeste](/common-data-model/sdk/manifest). Jei aprašo nėra, administratoriaus vartotojai, turintys "Storage Blob Data Owner" arba "Storage Blob Data Contributor" prieigą, gali apibrėžti schemą prarydami duomenis.

## <a name="connect-to-azure-data-lake-storage"></a>Prisijungimas prie „Azure Data Lake Storage“

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogo langas, skirtas įvesti &quot;Azure Data Lake&quot; ryšio informaciją." lightbox="media/data_sources_ADLS.png":::

1. **Įveskite duomenų šaltinis pavadinimą** ir pasirinktinį **aprašą**. Pavadinimas unikaliai identifikuoja duomenų šaltinis ir yra nurodomas tolesniuose procesuose ir jo negalima pakeisti.

1. Pasirinkite vieną iš šių parinkčių Prijunkite **saugyklą naudodami**. Daugiau informacijos ieškokite ["Customer Insights" prijungimas Azure Data Lake Storage prie "Gen2" paskyros su "Azure" paslaugos vykdytoju](connect-service-principal.md).

   - **Azure resource**: įveskite **išteklių ID**. Pasirinktinai, jei norite praryti duomenis iš saugyklos paskyros naudodami "Azure Private Link", pasirinkite **Įgalinti privatų saitą**. Daugiau informacijos ieškokite [Privačios nuorodos](security-overview.md#private-links-tab).
   - **"Azure" prenumerata**: pasirinkite prenumeratą **,** tada **išteklių grupę** ir **saugyklos paskyrą**. Pasirinktinai, jei norite praryti duomenis iš saugyklos paskyros naudodami "Azure Private Link", pasirinkite **Įgalinti privatų saitą**. Daugiau informacijos ieškokite [Privačios nuorodos](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Norint sukurti duomenų šaltinis, jums reikia vieno iš šių vaidmenų į konteinerį arba saugojimo paskyrą:
   >
   >  - "Storage Blob Data Reader" pakanka, kad galėtumėte skaityti iš saugyklos paskyros ir nuryti duomenis į "Customer Insights". 
   >  - Saugyklos "Blob" duomenų bendraautoris arba savininkas yra būtinas, jei norite redaguoti manifesto failus tiesiogiai "Customer Insights".  
  
1. Pasirinkite **konteinerio**, kuriame yra duomenys ir schema (model.json arba manifest.json failas), iš kurio norite importuoti duomenis, pavadinimą ir pasirinkite **Pirmyn**.
   > [!NOTE]
   > Sąraše nebus rodomas bet koks failas model.json arba jison duomenų šaltinis su kitu aplinkos sąrašu. Tačiau tą patį failą model.json arba manifest.json galima naudoti duomenų šaltiniams keliose aplinkose.

1. Norėdami sukurti naują schemą, eikite į [Kurti naują schemos failą](#create-a-new-schema-file).

1. Norėdami naudoti esamą schemą, eikite į aplanką, kuriame yra failas model.json arba manifest.cdm.json. Norėdami rasti failą, galite ieškoti kataloge.

1. Pasirinkite json failą ir pasirinkite **Pirmyn**. Rodomas galimų objektų sąrašas.

   :::image type="content" source="media/review-entities.png" alt-text="Objektų, kuriuos reikia pažymėti, sąrašo dialogo langas":::

1. Pasirinkite objektus, kuriuos norite įtraukti.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogo langas, kuriame rodomas būtinas pirminiam raktui":::

   > [!TIP]
   > Norėdami redaguoti objektus JSON redagavimo sąsajoje, pasirinkite **Rodyti daugiau** > **Redaguoti schemos failą**. Atlikite pakeitimus ir pasirinkite **Įrašyti**.

1. Pasirinktiems objektams, kuriems reikalingas laipsniškas nurijimas, **būtina** rodyti dalyje **Laipsniškas atnaujinimas**. Apie kiekvieną iš šių objektų žiūrėkite ["Azure Data Lake" duomenų šaltinių laipsniško atnaujinimo konfigūravimas](incremental-refresh-data-sources.md).

1. Pasirinktuose objektuose, kurių pirminis raktas nebuvo apibrėžtas, **privalomas** rodomas dalyje **Pirminis raktas**. Kiekvienam iš šių objektų:
   1. Pasirinkite **Būtina**. Rodomas objekto **redagavimo** skydas.
   1. Pasirinkite pagrindinį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.
   1. Pasirinktinai pakeiskite skaidinio modelį.
   1. Pasirinkite **Uždaryti**, kad išsaugotumėte ir uždarytumėte skydelį.

1. Pasirinkite kiekvieno įtraukto objekto atributų **skaičių**. Rodomas **puslapis Atributų** tvarkymas.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogo langas, skirtas duomenų profiliavimui pasirinkti.":::

   1. Kurkite naujus atributus, redaguokite arba ištrinkite esamus atributus. Galite pakeisti pavadinimą, duomenų formatą arba pridėti semantinį tipą.
   1. Norėdami įgalinti analizę ir kitas galimybes, pasirinkite **Viso objekto arba konkrečių atributų duomenų profiliavimas**. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.
   1. Pasirinkite **Atlikta**.

1. Pasirinkite **Įrašyti**. Atidaromas **puslapis Duomenų šaltiniai**, kuriame rodoma nauja atnaujinimo būsenos duomenų **šaltinis**.

### <a name="create-a-new-schema-file"></a>Naujo schemos failo kūrimas

1. Pasirinkite **Naujas schemos failas**.

1. Įveskite failo vardą ir pasirinkite **Įrašyti**.

1. Pasirinkite **Naujas objektas**. Rodomas **skydelis Naujas objektas**.

1. Įveskite objekto pavadinimą ir pasirinkite **duomenų failų vietą**.
   - **Keli .csv arba .parketo failai**: pereikite į šakninį aplanką, pasirinkite trafareto tipą ir įveskite išraišką.
   - **Vieno .csv arba .parketo failai**: pereikite prie failo .csv arba .parketo ir pasirinkite jį.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogo langas, skirtas sukurti naują objektą su paryškinta duomenų failų vieta.":::

1. Pasirinkite **Įrašyti**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogo langas atributams apibrėžti arba automatiškai generuoti.":::

1. Pasirinkite **apibrėžti atributus, kad atributai** būtų įtraukti rankiniu būdu, arba pasirinkite **automatiškai juos** generuoti. Norėdami apibrėžti atributus, įveskite pavadinimą, pasirinkite duomenų formatą ir pasirinktinį semantinį tipą. Jei atributai sugeneruoti automatiškai:

   1. Kai atributai bus sugeneruoti automatiškai, pasirinkite **Peržiūrėti atributus**. Rodomas **puslapis Atributų** tvarkymas.

   1. Įsitikinkite, kad kiekvieno atributo duomenų formatas yra teisingas.

   1. Norėdami įgalinti analizę ir kitas galimybes, pasirinkite **Viso objekto arba konkrečių atributų duomenų profiliavimas**. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogo langas, skirtas duomenų profiliavimui pasirinkti.":::

   1. Pasirinkite **Atlikta**. Rodomas **puslapis Pasirinkti objektus**.

1. Toliau įtraukite objektų ir atributų, jei taikoma.

1. Įtraukę visus objektus, pasirinkite **Įtraukti**, kad įtrauktumėte objektus į duomenų šaltinis nurijimą.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogo langas, kuriame rodomas būtinas pirminiam raktui":::

1. Pasirinktiems objektams, kuriems reikalingas laipsniškas nurijimas, **būtina** rodyti dalyje **Laipsniškas atnaujinimas**. Apie kiekvieną iš šių objektų žiūrėkite ["Azure Data Lake" duomenų šaltinių laipsniško atnaujinimo konfigūravimas](incremental-refresh-data-sources.md).

1. Pasirinktuose objektuose, kurių pirminis raktas nebuvo apibrėžtas, **privalomas** rodomas dalyje **Pirminis raktas**. Kiekvienam iš šių objektų:
   1. Pasirinkite **Būtina**. Rodomas objekto **redagavimo** skydas.
   1. Pasirinkite pagrindinį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.
   1. Pasirinktinai pakeiskite skaidinio modelį.
   1. Pasirinkite **Uždaryti**, kad išsaugotumėte ir uždarytumėte skydelį.

1. Pasirinkite **Įrašyti**. Atidaromas **puslapis Duomenų šaltiniai**, kuriame rodoma nauja atnaujinimo būsenos duomenų **šaltinis**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Duomenų šaltinis redagavimas Azure Data Lake Storage

Galite atnaujinti *parinktį Prisijungti prie saugyklos paskyros naudodami* parinktį. Daugiau informacijos ieškokite ["Customer Insights" prijungimas Azure Data Lake Storage prie "Gen2" paskyros su "Azure" paslaugos vykdytoju](connect-service-principal.md). Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-azure-data-lake-storage).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Šalia duomenų šaltinis, kurį norite atnaujinti, pasirinkite **Redaguoti**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogo langas, skirtas redaguoti &quot;Azure Data Lake duomenų šaltinis&quot;.":::

1. Pakeiskite bet kurią iš šių duomenų:

   - **Aprašymas**
   - **Prijunkite saugyklą naudodami** ir prijunkite informaciją. Negalite keisti **Talpyklos** informacijos naujinant jungtį.
      > [!NOTE]
      > Saugojimo paskyrai arba konteineriui turi būti priskirtas vienas iš šių vaidmenų:
        > - „Storage Blob Data“ skaitytojas
        > - „Storage Blob Data“ savininkas
        > - „Storage Blob Data“ pildytojas

   - **Įgalinkite "Private Link"**, jei norite nuryti duomenis iš saugyklos paskyros naudodami "Azure Private Link". Daugiau informacijos ieškokite [Privačios nuorodos](security-overview.md#private-links-tab).

1. Pasirinkite **Toliau**.
1. Pakeiskite bet kurį iš šių dalykų:
   - Eikite į kitą model.json arba manifest.json failą su kitu objektų rinkiniu iš konteinerio.
   - Norėdami įtraukti papildomų objektų į nurijimą, pasirinkite **Naujas objektas**.
   - Norėdami pašalinti jau pasirinktus objektus, jei nėra priklausomybių, pasirinkite objektą ir **Naikinti**.
      > [!IMPORTANT]
      > Jei yra esamo modelio.json arba manifest.json failo ir objektų rinkinio priklausomybių, bus rodomas klaidos pranešimas, kuriame negalite pažymėti kito modelio.json arba manifest.json failo. Pašalinkite šias priklausomybes prieš keisdami failą model.json arba manifest.json arba sukurkite naują duomenų šaltinį naudodami failą model.json arba manifest.json, kad išvengtumėte priklausomybių pašalinimo.
   - Norėdami pakeisti duomenų failo vietą arba pirminį raktą, pasirinkite **Redaguoti**.
   - Norėdami pakeisti laipsniško įsisavinimo duomenis, žiūrėkite ["Azure Data Lake" duomenų šaltinių laipsniško atnaujinimo konfigūravimas](incremental-refresh-data-sources.md)

1. Pasirinkite **Atributai**, kad įtrauktumėte ar pakeistumėte atributus arba įgalintumėte duomenų profiliavimą. Tada pasirinkite **Atlikta**.

1. Spustelėkite **Įrašyti**, kad pritaikytumėte pakeitimus ir grįžtumėte į **puslapį Duomenų šaltiniai**.
