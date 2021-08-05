---
title: Eksperimentai su Mašininio mokymo studija (įprasta programa)
description: Naudokite Mašininio mokymo studiją (įprastos programos) modelius „Dynamics 365 Customer Insights“.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb44604e72b32292f971754d4f8c4fd1988c697
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555179"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Naudokite modelius pagrįstus „Azure“ Mašininio mokymo studija (įprasta programa)

Suvienodinti duomenys „Dynamics 365 Customer Insights“ yra šaltinis skirtas sukurti mašininio mokymosi modelius, kurie gali sukurti papildomas verslo įžvalgas. „Customer Insights“ integruojamos su Mašininio mokymo studija (įprasta programa) siekiant naudoti jūsų turimus tinkintus modelius. Norėdami pamatyti, kaip modeliai išvystyti „Azure“ mašininiu mokymu yra integruojami su „Customer Insights“, žr. [„Azure“ mašininio mokymo eksperimentus](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Prieiga prie „Customer Insights“
- Aktyvi „Azure Enterprise“ prenumerata
- [Sujungti klientų profiliai](data-unification.md)
- [Objekto eksportavimo į „Azure” didelių dvejetainių objektų saugyklą](export-azure-blob-storage.md) sąranka

## <a name="set-up-machine-learning-studio-classic"></a>Mašininio mokymo studijos (įprastos programos) nustatymas

Pirmajame žingsnyje mums reikia sukurti darbo aplinką ir atverti Mašininio mokymo studijos (įprastą programą).

1. Eikite į[https://www.portal.azure.com](https://www.portal.azure.com/) ir prisijunkite.

1. Pasirinkite **Sukurti išteklių**.

1. Ieškokite **Mašininio mokymo studijos darbo sritis** ir pasirinkite **Kurti**.

1. Įveskite būtiną išsamią informaciją, kad [sukurtumėte darbo sritį](/azure/machine-learning/studio/create-workspace). Pasirinkite **Žiniatinklio paslaugos plano kainyno eilė** pagrįsta duomenų, kurių planuojate importuoti, kiekiu. Geriausiam vykdymui pasirinkite **Vietą** geografiškai jums arčiausią.

1. Sukūrus išteklių bus rodoma mašininio mokymo studijos darbo srities ataskaitų sritis. Pasirinkite **Paleisti mašininio mokymo studiją**.

   ![„Azure” mašininio mokymo studijos vartotojo sąsaja.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Darbas su „Azure“ mašininio mokymo studija

Dabar galite sukurti naują bandymą arba importuoti esamą bandymo šabloną iš pavyzdžių galerijos. Esama pavyzdžių eksperimentų trims standartiniams scenarijams:

- [Klientų praradimo prognozė](#churn-analysis)

- [Ilgalaikė kliento vertė](#customer-lifetime-value-prediction)

- [Produkto rekomendacija arba kitas geriausias veiksmas](#productrecommendation-or-next-best-action)

1. Jei kuriate naują bandymą arba naudojate bandymo šabloną iš galerijos, turite sukonfigūruoti **duomenų importavimo** ypatybes. Naudokite gairių patirtį ar tiesiogiai teikite išsamią informaciją siekiant prieiti prie „Azure Blob Storage“, kuriame yra jūsų duomenys.  

   ![„Azure“ mašininio mokymo studijos bandymas.](media/azure-machine-learning-studio-experiment.png)

1. Dabar galite kurti pasirinktinį apdorojimo srautą, kad galėtumėte išvalyti ir iš anksto apdoroti duomenis, išskleisti funkcijas ir išmokyti tinkamą modelį.

1. Išbandykite ir optimizuokite modelio veikimą.

1. Kai esate patenkinti modelio kokybe, pasirinkite **Nustatyti žiniatinklio tarnybą** > **Prognozinė žiniatinklio tarnyba**. Šia parinktimi importuojami išmokomas modelis ir funkcijų rinkinių nustatymo srautas iš mokomojo bandymo į prognozinę tarnybą. Prognozinė tarnyba gali naudoti kitą įvesties duomenų rinkinį su schema, naudojama mokomajame bandyme, teikti prognozes.

   ![Prognozinės žiniatinklio tarnybos nustatymas.](media/predictive-webservice-control.png)

1. Kai prognozinės žiniatinklio tarnybos bandymas yra sėkmingas, galite jį visuotinai diegti automatiniam planavimui. Jei norite, kad žiniatinklio tarnyba veiktų su „Customer Insights”, pasirinkite **Visuotinai diegti žiniatinklio tarnybą** > **Visuotinai diegti žiniatinklio tarnybos [naują] peržiūros versiją**. [Sužinokite daugiau apie žiniatinklio tarnybos visuotinį diegimą](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Prognozinės žiniatinklio tarnybos visuotinis diegimas.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modelių pavyzdžiai iš galerijos

Šiame straipsnyje modeliams naudosime fiktyvų „Contoso Hotel” scenarijų. „Contoso Hotel” renka šiuos duomenis:

- CRM duomenis, kuriuos sudaro apsistojimo viešbutyje veikla. Į duomenų rinkinį įtraukiama informacija apie kiekvieno registruoto kliento apsistojimo datas. Jame taip pat yra informacija apie rezervavimą, kambarių tipus, išsami informacija apie išlaidas ir t. t. Duomenys apima ketverius metus, nuo 2014 m. sausio mėn. iki 2018 m. sausio mėn.
- Viešbučio svečių klientų profiliai. Šiuose profiliuose pateikiama informacija apie kiekvieną klientą, įskaitant jo vardą bei pavardę, gimimo datą, pašto adresą, lytį ir telefono numerį.
- Viešbučio siūlomų paslaugų naudojimas, pvz., spa paslaugų, skalbyklos, „Wifi“ arba kurjerio paslaugos. Ši informacija registruojama kiekvienam registruotam klientui. Paprastai paslaugų naudojimas siejamas su apsistojimu. Kai kuriais atvejais paslaugas gali naudoti klientai neapsistoję viešbutyje.

## <a name="churn-analysis"></a>Klientų praradimo analizė

Klientų praradimo analizė taikoma įvairioms verslo sritims. Šiame pavyzdyje pažvelgsime į paslaugų nutraukimą, konkrečiau, kaip aprašyta prieš tai, į viešbučio paslaugų kontekstą. Jis pateikia galutinio modelio vamzdyno darbo pavyzdį, kuris gali būti naudojamas kaip pradinis bet kokio kito nutraukimo modelio taškas.

### <a name="definition-of-churn"></a>Klientų praradimo apibrėžtis

Klientų praradimo apibrėžtis gali skirtis atsižvelgiant į scenarijų. Šiame pavyzdyje, svečias, kuris nesilankė viešbutyje paskutiniais metais turėtų būti pažymėtas kaip paslaugas nutraukęs.  

Eksperimento šablonas gali būti importuojamas iš galerijos. Pirmiausia, užsitikrinkite, kad importavote duomenis **Apsistojimo viešbutyje veiklai**, **Kliento duomenis** ir **Paslaugų naudojimo duomenys** iš „Azure Blob“ talpinimo.

   ![Importuoti klientų praradimo modelio duomenis.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Funkcijų rinkinių nustatymas

Remiantis nutraukimo sąvoka, pirmiausia nustatysime neapdorotas funkcijas, kurios paveiks žymą. Tada apdorosime šias neapdorotas funkcijas į skaitines funkcijas, kurias galima naudoti su mašininio mokymo modeliais. Duomenų integravimas vykdomas „Customer Insights“, todėl galime prisijungti prie šių lentelių naudojant *Kliento ID*.

   ![Importuotų duomenų sujungimas.](media/join-imported-data.png)

Modelio kūrimui skirtas savybių suteikimas nutraukimo analizei gali būti kiek sudėtingas. Duomenis sudaro laiko funkcija su nauja viešbučio veikla, registruojama kasdien. Funkcijų rinkinių nustatymo metu mes siekiame generuoti statines funkcijas iš dinaminių duomenų. Tokiu atveju, sukuriame keletą funkcijų iš viešbučio veiklos su slankiojančiu vienerių metų langu. Taip pat išplėsdami funkcijų grupavimą, pvz., pagal kambario tipą arba rezervavimo tipą, į atskiras funkcijas, naudodamiesi vieno vieneto bito kodavimu.  

Galutinis funkcijų sąrašas:

| **Skaičius**  | **Original_Column**          | **Išvestinės funkcijos**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Kambario tipas                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Rezervavimo tipas                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kelionės kategorija              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Išleista dolerių                | TotalDollarSpent                                                                                                                          |
| 5           | Įsiregistravimo ir išsiregistravimo datos  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Paslaugų naudojimas                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Modelio pasirinkimas

Dabar mums reikia rinktis optimalų naudojamą algoritmą. Šiuo atveju dauguma funkcijų yra rūšiuojamos pagal kategoriją. Dažniausiai sprendimų medžiu pagrįsti modeliai veikia gerai. Jei esama tik skaitinių funkcijų, nerviniai tinklai gali būti geresnis pasirinkimas. Atraminių vektorių mašina (SVM) taip pat yra puikus pasirinkimas tokiose situacijose, tačiau reikia nemažai derinti, kad būtų galima gauti geriausių rezultatų. Renkamės **Dviejų klasių pagerintą sprendimų medį** kaip pirmą pasirinkimo modelį po **Dviejų klasių SVM** kaip antrą modelį. „Azure“ mašininio mokymosi studija leidžia jums atlikti A/B testavimą, todėl yra naudinga pradėti su dviem modeliais, o ne su vienu.

Šiame vaizde pateikiamas „Azure” mašininio mokymo studijos modelio mokymas ir įvertinimo srautas:

![„Azure” mašininio mokymo studijos klientų praradimo modelis.](media/azure-machine-learning-model.png)

Mes taip pat taikome techniką pavadintą **Derinių funkcijos svarba** yra svarbus modelio optimizavimo aspektas. Įtaisytieji modeliai turi mažai arba jokių įžvalgų apie tai, kokį poveikį turi bet kokia konkreti funkcija galutinei prognozei. Funkcijos svarbos skaičiuoklė naudoja tinkintą algoritmą siekiant apskaičiuoti atskirų funkcijų įtaką konkretaus modelio išvadoms. Funkcijų svarba normalizuojama nuo +1 iki –1. Neigiam įtaka reiškia, kad atitinkama funkcija susidūrė su intuityvia įtaka išvesčiai ir turi būti pašalinta iš modelio. Teigiama įtaka nurodo, kad funkcija labai reikšminga prognozei. Šios reikšmės nėra koreliacijos koeficientai, nes jie atitinka skirtingą metriką. Dėl išsamesnės informacijos, žr. [Derinio funkcijos svarba](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Visas [nutraukimo eksperimentas yra prieinamas „Azure“ AI galerijoje](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Ilgalaikės kliento vertės prognozė

Ilgalaikės kliento vertės (CLTV) apskaičiavimas yra vieneri iš pagrindinių duomenų, kuriuos verslas gali naudoti siekiant įvertinti ir segmentuoti savo klientus. Viešbučių verslui yra gyvybiškai svarbu sužinoti savo klientus. Pavyzdžiui, faktorių supratimas, kuris sudaro gerus klientus yra gyvybiškai svarbi informacija. Ji padeda viešbučio valdybai įvertinti, ties kuriomis funkcijomis jai reikia susikoncentruoti ir pagerinti pasitenkinimą jų daug mokančiais klientais. Šie sprendimai gali turėti tiesioginės įtakos pardavimui ir pajamoms.  

### <a name="definition-of-cltv"></a>CLTV apibrėžtis

Šiame pavyzdyje, nustatėme kliento CLTV kaip bendrą dolerių sumą, kurią klientas tikėtina išleis per kitas 365 dienas. Planuojame naudoti paskutinių trijų metų duomenų vertę visiems klientams, kurie prognozuos šią vertę.

### <a name="featurization"></a>Funkcijų rinkinių nustatymas

Šiuo atveju, funkcijų rinkinių nustatymas labai primins klientų praradimo scenarijų. Nepaisant to, žymos ir prognozuotos vertės skiriasi nei nurodytos prieš tai.

### <a name="model-selection"></a>Modelio pasirinkimas

CLTV prognozavimas yra regresijos uždavinys, o prognozuojama vertė yra teigiamos vertės tęstinis kintamasis. Remiantis funkcijų ypatybėmis, pasirenkame **Pagerintų sprendimų medžio regresiją** kaip vieną algoritmą ir **Nervų žiniatinklio regresiją** kaip kitą algoritmą siekiant bandyti modelį.

## <a name="product-recommendation-or-next-best-action"></a>Gaminio rekomendacijos ar kiti gerieji veiksmai

Produktų rekomendacija pagal viešbučio scenarijų aiškinama kaip rekomenduojamos viešbučio paslaugos klientams. Tikslas – pasirinkti atitinkamas paslaugas klientams, kad jų naudojimas būtų maksimizuotas. Tai panašu į vaizdo įrašų transliacijos paslaugų vartotojų filmų rekomendacijas.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Produkto rekomendacijos arba kito geriausio veiksmo apibrėžtis

Mes apibrėžiame tikslą kaip maksimizuoti uždirbtų teikiant paslaugas dolerių sumą siūlant labiausiai atitinkančias viešbučio klientų interesus paslaugas.

### <a name="featurization"></a>Funkcijų rinkinių nustatymas

Kaip ir atsisakymo modelis, mes sujungiame viešbučio paslaugų kliento ID su kliento ID siekiant sukurti nuoseklias rekomendacijas kliento ID.

![Rekomendacijų modelio funkcijų rinkinių nustatymas.](media/azure-machine-learning-model-featurization.png)

Duomenys yra paimami iš trijų skirtingų objektų ir funkcijos yra išvedamos iš jų. Funkcijų rinkinių nustatymas rekomendacijos problemai skiriasi, palyginti su klientų praradimu arba CLTV scenarijais. Rekomendacijos modeliui reikia įvesties duomenų trijų funkcijų rinkinių forma.

### <a name="model-selection"></a>Modelio pasirinkimas

Prognozuojame produktus ir paslaugas naudojant algoritmą vadinamą **treniruoti atitikties laukelio patarėją** siekiant ištreniruoti rekomendacijos modelį.

![Produktų rekomendacijos algoritmas.](media/azure-machine-learning-model-recommendation-algorithm.png)

Trys įvesties prieigos **Treniruoti atitikties laukelio patarėją** modelis ima mokymo paslaugų naudojimo duomenis, kliento aprašą (pasirenkamas) ir paslaugų aprašą. Esama trijų skirtingų šio modelio vertinimo būdų. Vienas yra skirtas modelio įvertinimui, kuriame įprastas nukainotas kumuliatyvinio padidėjimo (NDCG) balas yra skaičiuojamas siekiant įvertinti išreitinguotus elementus. Šiame bandyme mes turime NDCG balą kaip 0,97. Kitos dvi parinktys yra modelio įvertinimas pagal visą rekomenduojamą paslaugų katalogą ar vertinimą tik elementams, kurių vartotojai anksčiau nenaudojo.

Žvelgiant toliau į rekomendacijų pasiskirstymą lyginant su visu paslaugų katalogu, pastebėjome, kad telefonas, WiFi ir vežėjas yra pagrindinės rekomenduotinos paslaugos. Tai atitinka tai, ką radome paslaugų naudojimo duomenų pasiskirstymuose:

![Rekomendacijos modelio išvestis.](media/azure-machine-learning-model-output.png)

Visas [produkto rekomendacijos eksperimentas gali būti prieinamas „Azure“ AI galerijoje.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integruoti tinkintus modelius

Siekiant naudoti šias prognozes „Customer Insights“, jums reikia **eksportuoti** prognozes kartu su kliento ID. [Eksportuokite juos į tą pačią „Azure Blob“ talpinimo vietą](/azure/storage/common/storage-import-export-data-from-blobs), į kurią eksportavote išteklių duomenis. Prognozuojama žiniatinklio tarnyba gali būti suplanuota veikti reguliariai ir naujinti balus.

Tinkinto modelio sugeneruoti duomenys gali būti naudojami tolesniam jūsų kliento duomenų praturtinimui. Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]