---
title: Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas
description: Sukurkite aktyvų ryšį tarp auditorijos įžvalgų ir įtraukimo įžvalgų, kad duomenis būtų galima bendrai naudoti dvipusio naudojimo srityje.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: db38778c0da862e119f9b374e07c82ead0d3a4f2
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645592"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Įtraukimo įžvalgas ir auditorijos įžvalgos integracija susieja aplinkas su abiem galimybėmis, ir įgalina, kad duomenys gali būti bendrai naudojami abiem kryptimis.

Norėdami gauti daugiau analizės parinkčių įtraukimo įžvalgų, naudokite vieningus profilius ir segmentus iš auditorijos įžvalgų. Eksportuokite įvykius, kurių verslo reikšmė labai aukšta iš įtraukimo įžvalgų. Naudodami šiuos įvykius galite įtraukti duomenis į vieningus auditorijos įžvalgų profilius.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Auditorijos įžvalgų profiliai turi būti saugomi jūsų valdomoje Azure Data Lake Storage paskyroje arba [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash; valdomoje duomenų saugykloje. 
- Jūsų auditorijų įžvalgų aplinkoje turi būti susieta „Dataverse” aplinka. O jei ta aplinka taip pat naudoja „Dataverse” duomenų saugojimui, būtinai patikrinkite **Įgalinti duomenų bendrinimą** auditorijos įžvalgose. Daugiau informacijos žr. [Aplinkos kūrimas ir konfigūravimas auditorijos įžvalgų srityje](../audience-insights/create-environment.md).
- Jums reikia administratoriaus teisių tiek įtraukimo įžvalgų, tiek auditorijos įžvalgų aplinkose.
- Susietos aplinkos turi būti tame pačiame geografiniame regione.

> [!NOTE]
> - Jei jūsų auditorijos įžvalgų prenumerata yra bandomoji versija, naudojanti auditorijos įžvalgas viduje valdomus „data lake”, kreipkitės į [pirequest@microsoft.com](mailto:pirequest@microsoft.com) dėl pagalbos. 
> - Jei jūsų auditorijos įžvalgų aplinka naudoja jūsų nuosavą Azure Data Lake Storage duomenims saugoti, į saugyklos paskyrą turite įtraukti įtraukimo įžvalgų "Azure" pagrindinę tarnybą. Norėdami gauti daugiau informacijos, eikite [Prisijungti prie Azure Data Lake Storage paskyros su "Azure" tarnyba, kuri yra pagrindinė auditorijos įžvalgų dalis](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Aplinkos ryšio kūrimas

Galite sukurti aplinkos ryšį atnaujindami **Admin** > **Aplinkos** parametrus į įtraukimo įžvalgas.

**Sukurti aktyvią sąsają tarp auditorijos įžvalgų ir įtraukimo įžvalgų**

1. **Aplinkos administravimo** puslapyje pasirinkite **Susieti aplinkas** skirtuką.

    :::image type="content" source="media/integrate1.png" alt-text="Aplinkos nustatymas.":::

1. Viršutiniame kairiajame kampe arba ekrano apačioje pasirinkite **Susieti aplinkas**.

     :::image type="content" source="media/integrate2.png" alt-text="Pasirinkti auditorijos įžvalgų aplinką.":::

1. Pažymėkite auditorijos įžvalgų aplinką, tada pažymėkite ***Sekantis** kad užbaigtumėte. Dabar galite pasirinkti pasirinktines susietų aplinkos funkcijų parinktis.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Įjunkite auditorijos įžvalgų vieningus profilių atributus ir segmentus

Susieję aplinkas, galite pasirinkti pasirinktines susietų aplinkos funkcijų parinktis. Šios funkcijos įgalina vieningus profilio atributus ir segmentus iš auditorijos įžvalgų, kad būtų galima interaktyviai analizuoti klientų duomenis.

> [!IMPORTANT]
> Kad auditorijos įžvalgų segmentai būtų rodomi įtraukimo įžvalgoje, pirmiausia turite [paleisti suliejimo ir pasroviui procesus](../audience-insights/merge-entities.md). Pasroviniai procesai yra svarbūs, nes jie sukuria unikalią lentelę, kuri paruošia auditorijos įžvalgų segmentus, kuriuos reikia bendrai naudoti su įtraukimo įžvalgomis. (Jei sistemos naujinimas suplanuotas, jis automatiškai apims tolesnius procesus).

**Žiniatinklio duomenų analizavimas įtraukimo įžvalgose**

1. **Aplinkos admin** puslapyje įjunkite **Bendrinti duomenis iš auditorijos įžvalgų su įtraukimo įžvalgomis** jungiklį ir tada pasirinkite **Sekantis**.

    :::image type="content" source="media/integrate4.png" alt-text="Pasirinkti funkcijas.":::

1. Pažymėkite vieningų profilių atributus, kurie taps matmenimis įtraukimo įžvalgų metu. (Ne visi atributai yra naudingi matmenys. Pavyzdžiui, tikriausiai jums neprireiks  **Vardo** or **Pavardės** kaip atributų jūsų tinklalapio įvykių analizei).

    :::image type="content" source="media/integrate5.png" alt-text="Kuruoti matmenis.":::

   >[!NOTE]
   > Visi auditorijos įžvalgų profilio atributai, reiškiantys identifikatorius (pvz. **ID** ir **pakaitinė ID**) yra filtruojami iš galimų atributų ir tampa įsitraukimo įžvalgų matmenimis.

1. Baigę žymėti atributus, pasirinkite **Kitas**.
1. Įtraukite vartotojų, kurie gali peržiūrėti auditorijos įžvalgų profilio aspektus ir segmentus įtraukimo įžvalgose.

    :::image type="content" source="media/integrate6.png" alt-text="Valdyti prieigą prie kliento duomenų.":::

   > [!IMPORTANT]
   > Jei šiame žingsnyje aiškiai nepridėsite vartotojų, duomenys bus paslėpti nuo vartotojų įtraukimo įžvalgose.
   > Kad auditorijos įžvalgų segmentai būtų rodomi įtraukimo įžvalgoje, pirmiausia turite [paleisti suliejimo ir pasroviui procesus](../audience-insights/merge-entities.md). Pasroviniai procesai yra svarbūs, nes jie sukuria unikalią lentelę, kuri paruošia auditorijos įžvalgų segmentus, kuriuos reikia bendrai naudoti su įtraukimo įžvalgomis. (Jei sistemos naujinimas suplanuotas, jis automatiškai apims tolesnius procesus).

1. Peržiūrėkite savo pasirinkimą ir pasirinkite **Baigti**.

    :::image type="content" source="media/integrate7.png" alt-text="Kliento duomenų parametrų peržiūra.":::

## <a name="export-refined-events-to-audience-insights"></a>Eksportuokite patikslintus įvykius su auditorijos įžvalgomis

Sukūrę ryšį tarp aplinkų, galite eksportuoti patobulintus įvykius iš įtraukimo įžvalgų į auditorijos įžvalgas ir naudoti juos kaip naują duomenų šaltinį. 

Norėdami gauti daugiau informacijos, eikite [į Žiniatinklio duomenų integravimas iš įtraukimo įžvalgų su auditorijos įžvalgomis](../audience-insights/integrate-engagement-insights.md)

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
