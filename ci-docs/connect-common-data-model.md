---
title: Sujungti „Common Data Model“ duomenis su „Azure Data Lake“ paskyra
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
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011577"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Jungtis prie duomenų „Azure Data Lake Storage“

Duomenų naudojimasis Dynamics 365 Customer Insights " Azure Data Lake Storage Gen2" paskyra. Duomenų nurijimas gali būti pilnas arba laipsniškas.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Duomenų nurijimas palaiko Azure Data Lake Storage *tik "Gen2* " paskyras. Negalite naudoti "Data Lake Storage Gen1" paskyrų duomenims nuryti.

- Abonemente Azure Data Lake Storage turi būti [įgalinta hierarchinė vardų sritis](/azure/storage/blobs/data-lake-storage-namespace). Duomenys turi būti saugomi hierarchiniu aplanko formatu, kuris apibrėžia šakninį aplanką ir turi kiekvieno objekto poaplankius. Poaplankiai gali turėti visus duomenų arba papildomų duomenų aplankus.

- Norėdami autentifikuoti su „Azure“ pagrindinėmis paslaugomis, įsitikinkite, kad sukonfigūravote jas savo nuomotojuje. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md)

- Duomenys Azure Data Lake Storage, iš kurių norite prisijungti ir iš kurių norite prisijungti, turi būti tame pačiame "Azure" regione kaip ir Dynamics 365 Customer Insights aplinka. Ryšiai su „Common Data Model“ katalogu iš kito „Azure“ regiono duomenų telkinio nėra palaikomi. Norėdami sužinoti "Azure" aplinkos regioną, eikite į **"Customer Insights" administravimo** > **sistema** > **apie**.

- Internetinėse paslaugose saugomi duomenys gali būti saugomi kitoje vietoje nei ten, kur duomenys tvarkomi ar saugomi Dynamics 365 Customer Insights.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse paslaugose, jūs sutinkate, kad duomenys gali būti perduodami ir saugomi su Dynamics 365 Customer Insights. [Sužinokite daugiau "Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).

- Norint pasiekti saugyklos abonementą, "Customer Insights" tarnybos vykdytojas turi atlikti vieną iš šių vaidmenų. Daugiau informacijos ieškokite [Grant permissions to service principal, kad galėtų pasiekti saugyklos abonementą](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - „Storage Blob Data“ skaitytojas
  - „Storage Blob Data“ savininkas
  - „Storage Blob Data“ pildytojas

- Jūsų duomenų saugyklos duomenys turėtų atitikti "Common Data Model" standartą jūsų duomenims saugoti ir turėti bendrą duomenų modelio manifestą, kuris atspindėtų duomenų failų schemą (*.csv arba *.parketas). Deklaracijoje turi būti pateikta išsami informacija apie objektus, pvz., objekto stulpelius ir duomenų tipus, taip pat duomenų failo vietą ir failo tipą. Daugiau informacijos ieškokite [The Common Data Model manifest](/common-data-model/sdk/manifest). Jei deklaracijos nėra, administratoriaus vartotojai, turintys saugyklos BLOB duomenų savininko arba saugyklos BLOB duomenų bendraautoriaus prieigą, gali apibrėžti schemą vartodami duomenis.

## <a name="connect-to-azure-data-lake-storage"></a>Prisijungimas prie „Azure Data Lake Storage“

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogo langas, kuriame įvedama &quot;Azure Data Lake&quot; ryšio informacija." lightbox="media/data_sources_ADLS.png":::

1. Įveskite **duomenų šaltinis pavadinimą** ir pasirinktinį **aprašą**. Pavadinimas unikaliai identifikuoja duomenų šaltinis ir yra nurodytas tolesniuose procesuose ir negali būti pakeistas.

1. Pasirinkite vieną iš šių saugyklos **prijungimo parinkčių**. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md)

   - **"Azure" išteklius**: įveskite ištekliaus **ID**. Pasirinktinai, jei norite nuryti duomenis iš saugyklos abonemento naudodami "Azure Private Link", pasirinkite **Įgalinti privatų saitą**. Daugiau informacijos ieškokite [Private Links](security-overview.md#private-links-tab).
   - **"Azure" prenumerata**: pasirinkite **prenumeratą**, **tada išteklių grupę** ir **saugyklos abonementą**. Pasirinktinai, jei norite nuryti duomenis iš saugyklos abonemento naudodami "Azure Private Link", pasirinkite **Įgalinti privatų saitą**. Daugiau informacijos ieškokite [Private Links](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Norėdami sukurti duomenų šaltinis, turite atlikti vieną iš šių konteinerio arba saugyklos abonemento vaidmenų:
   >
   >  - "Storage Blob Data Reader" pakanka skaityti iš saugyklos abonemento ir nuryti duomenis "Customer Insights". 
   >  - Saugyklos BLOB duomenų ruošiklis arba savininkas reikalingas, jei deklaracijos failus norite redaguoti tiesiogiai "Customer Insights".  
  
1. Pasirinkite **konteinerio**, kuriame yra duomenys ir schema (model.json arba manifest.json failas), iš kurio norite importuoti duomenis, pavadinimą ir pasirinkite **Pirmyn**.
   > [!NOTE]
   > Sąraše nebus rodomas bet koks failas model.json arba jison duomenų šaltinis su kitu aplinkos sąrašu. Tačiau tą patį failą model.json arba manifest.json galima naudoti duomenų šaltiniams keliose aplinkose.

1. Norėdami sukurti naują schemą, eikite į [Kurti naują schemos failą](#create-a-new-schema-file).

1. Norėdami naudoti esamą schemą, eikite į aplanką, kuriame yra failas model.json arba manifest.cdm.json. Galite ieškoti kataloge, kad rastumėte failą.

1. Pasirinkite json failą ir pasirinkite **Pirmyn**. Rodomas galimų objektų sąrašas.

   :::image type="content" source="media/review-entities.png" alt-text="Pasirinktinų objektų sąrašo dialogo langas":::

1. Pasirinkite objektus, kuriuos norite įtraukti.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogo langas, kuriame rodomas būtinas pirminis raktas":::

   > [!TIP]
   > Norėdami redaguoti objektus JSON redagavimo sąsajoje, pasirinkite **Rodyti daugiau** > **Redaguoti schemos failą**. Atlikite keitimus ir pasirinkite **Įrašyti**.

1. Pasirinktiems objektams, kuriems reikia papildomo nurijimo, **būtini** ekranai dalyje **Papildomas atnaujinimas**. Apie kiekvieną iš šių objektų žr [.](incremental-refresh-data-sources.md)

1. Pasirinktų objektų, kuriuose pirminis raktas nenustatytas, **dalyje** Pirminis raktas **rodomas Būtinas**. Kiekvienam iš šių subjektų:
   1. Pasirinkite **Būtina**. Rodomas **objektų redagavimo** skydas.
   1. Pasirinkite pirminį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.
   1. Pasirinktinai pakeiskite skaidinio šabloną.
   1. Pasirinkite **Uždaryti**, kad įrašytumėte ir uždarytumėte skydelį.

1. Pasirinkite kiekvieno įtraukto objekto **atributų** skaičių. Rodomas **puslapis Tvarkyti atributus**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogo langas duomenų profiliavimui pasirinkti.":::

   1. Kurti naujus atributus, redaguoti arba naikinti esamus atributus. Galite pakeisti pavadinimą, duomenų formatą arba pridėti semantinį tipą.
   1. Norėdami įgalinti analizę ir kitas galimybes, pasirinkite **Viso objekto arba konkrečių atributų duomenų profiliavimas**. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.
   1. Pasirinkite **Atlikta**.

1. Pasirinkite **Įrašyti**. Atsidarys **puslapis Duomenų šaltiniai**, kuriame rodoma nauja duomenų šaltinis atnaujinimo **būsenoje**.

### <a name="create-a-new-schema-file"></a>Kurti naują schemos failą

1. Pasirinkite **Naujas schemos failas**.

1. Įveskite failo vardą ir pasirinkite **Įrašyti**.

1. Pasirinkite **Naujas objektas**. Rodomas **skydas Naujas objektas**.

1. Įveskite objekto pavadinimą ir pasirinkite **duomenų failų vietą**.
   - **Keli .csv arba .parketo failai**: raskite šakninį aplanką, pasirinkite šablono tipą ir įveskite išraišką.
   - **Vieno .csv arba .parketo failai**: raskite .csv arba .parketo failą ir pasirinkite jį.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogo langas naujam objektui, kuriame pažymėta duomenų failų vieta, sukurti.":::

1. Pasirinkite **Įrašyti**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogo langas atributams apibrėžti arba automatiškai generuoti.":::

1. Pasirinkite **nurodyti atributus, kad atributus** įtrauktumėte neautomatiniu būdu, arba pasirinkite **automatiškai juos** generuoti. Norėdami apibrėžti atributus, įveskite pavadinimą, pasirinkite duomenų formatą ir pasirinktinį semantinį tipą. Automatiškai sugeneruotiems atributams:

   1. Kai atributai bus sugeneruoti automatiškai, pasirinkite **Peržiūrėti atributus**. Rodomas **puslapis Tvarkyti atributus**.

   1. Įsitikinkite, kad kiekvieno atributo duomenų formatas yra teisingas.

   1. Norėdami įgalinti analizę ir kitas galimybes, pasirinkite **Viso objekto arba konkrečių atributų duomenų profiliavimas**. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogo langas duomenų profiliavimui pasirinkti.":::

   1. Pasirinkite **Atlikta**. Rodomas **puslapis Pasirinkti objektus**.

1. Jei taikoma, toliau įtraukite objektų ir atributų.

1. Įtraukę visus objektus, pasirinkite **Įtraukti**, kad įtrauktumėte objektus į duomenų šaltinis nurijimą.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogo langas, kuriame rodomas būtinas pirminis raktas":::

1. Pasirinktiems objektams, kuriems reikia papildomo nurijimo, **būtini** ekranai dalyje **Papildomas atnaujinimas**. Apie kiekvieną iš šių objektų žr [.](incremental-refresh-data-sources.md)

1. Pasirinktų objektų, kuriuose pirminis raktas nenustatytas, **dalyje** Pirminis raktas **rodomas Būtinas**. Kiekvienam iš šių subjektų:
   1. Pasirinkite **Būtina**. Rodomas **objektų redagavimo** skydas.
   1. Pasirinkite pirminį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.
   1. Pasirinktinai pakeiskite skaidinio šabloną.
   1. Pasirinkite **Uždaryti**, kad įrašytumėte ir uždarytumėte skydelį.

1. Pasirinkite **Įrašyti**. Atsidarys **puslapis Duomenų šaltiniai**, kuriame rodoma nauja duomenų šaltinis atnaujinimo **būsenoje**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Duomenų šaltinis redagavimas Azure Data Lake Storage

Galite atnaujinti *parinktį Prisijungti prie saugyklos abonemento naudodami* parinktį Prisijungti prie saugyklos. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md) Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-azure-data-lake-storage).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Šalia duomenų šaltinis, kurį norite atnaujinti, pasirinkite **Redaguoti**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogo langas, skirtas redaguoti &quot;Azure Data Lake&quot; duomenų šaltinis.":::

1. Pakeiskite bet kurią iš šių informacijos:

   - **Aprašymas**
   - **Prijunkite saugyklą naudodami** ir ryšio informaciją. Negalite keisti **Talpyklos** informacijos naujinant jungtį.
      > [!NOTE]
      > Saugojimo sąskaitai arba konteineriui turi būti priskirtas vienas iš šių vaidmenų:
        > - „Storage Blob Data“ skaitytojas
        > - „Storage Blob Data“ savininkas
        > - „Storage Blob Data“ pildytojas

   - **Įjunkite privačią nuorodą**, jei norite nuryti duomenis iš saugyklos abonemento naudodami "Azure Private Link". Daugiau informacijos ieškokite [Private Links](security-overview.md#private-links-tab).

1. Pasirinkite **Toliau**.
1. Pakeiskite bet kurį iš šių dalykų:
   - Eikite į kitą model.json arba manifest.json failą su kitu objektų rinkiniu iš konteinerio.
   - Norėdami į nurijimą įtraukti papildomų objektų, pasirinkite **Naujas objektas**.
   - Norėdami pašalinti visus jau pasirinktus objektus, jei nėra priklausomybių, pasirinkite objektą ir **Naikinti**.
      > [!IMPORTANT]
      > Jei yra esamo modelio.json arba manifest.json failo ir objektų rinkinio priklausomybių, bus rodomas klaidos pranešimas, kuriame negalite pažymėti kito modelio.json arba manifest.json failo. Pašalinkite šias priklausomybes prieš keisdami failą model.json arba manifest.json arba sukurkite naują duomenų šaltinį naudodami failą model.json arba manifest.json, kad išvengtumėte priklausomybių pašalinimo.
   - Norėdami pakeisti duomenų failo vietą arba pirminį raktą, pasirinkite **Redaguoti**.
   - Norėdami pakeisti papildančius nurijimo duomenis, žr.[...](incremental-refresh-data-sources.md)

1. Pasirinkite **Atributai**, kad įtrauktumėte arba pakeistumėte atributus arba įgalintumėte duomenų profiliavimą. Tada pasirinkite **Atlikta**.

1. Spustelėkite **Įrašyti**, kad pritaikytumėte keitimus ir grįžtumėte į **puslapį Duomenų šaltiniai**.
