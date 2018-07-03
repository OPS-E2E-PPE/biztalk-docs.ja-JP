---
title: Office 365 Outlook の連絡先のアダプターを使用して、|Microsoft Docs
description: BizTalk Server で Office 365 Outlook の連絡先のアダプターを使用してメッセージを送信します。 これを行うには、Outlook アダプターを使用して送信ポートを作成し、サンプルの XML メッセージを使用して、Office 365 Outlook アカウントの連絡先を作成します。
ms.custom: ''
ms.date: 06/25/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 3185e080be7a4222ac51072506eb9657eb7b1e1b
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946232"
---
# <a name="create-a-contact-using-the-office-365-outlook-contact-adapter---biztalk-server"></a><span data-ttu-id="d48d3-104">Office 365 Outlook の連絡先のアダプターの BizTalk Server を使用して連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-104">Create a contact using the Office 365 Outlook Contact adapter - BizTalk Server</span></span>

<span data-ttu-id="d48d3-105">BizTalk Server で、Office 365 Outlook の連絡先のアダプターを使用して、Office 365 Outlook の連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-105">Use the Office 365 Outlook Contact adapter in BizTalk Server to create contacts in your Office 365 Outlook.</span></span>

## <a name="create-a-contact-using-a-send-port"></a><span data-ttu-id="d48d3-106">送信ポートを使用して連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-106">Create a contact using a send port</span></span>

1. <span data-ttu-id="d48d3-107">右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="d48d3-108">[送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="d48d3-109">入力、**名前**します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-109">Enter a **Name**.</span></span> <span data-ttu-id="d48d3-110">**トランスポート**、設定、**型**に**Office 365 Outlook の連絡先**を選択し、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-110">In **Transport**, set the **Type** to **Office 365 Outlook Contact**, and select **Configure**.</span></span>

3. <span data-ttu-id="d48d3-111">選択**にサインインしています.**、し、Office 365 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d48d3-111">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="d48d3-112">アカウントは、電子メール アドレスに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d48d3-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="d48d3-113">BizTalk Server の承認にアクセスする権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 の連絡先のアクセス許可](../core/media/office365-contact-permissions.png)

5. <span data-ttu-id="d48d3-115">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-115">Select **Ok** to save your changes.</span></span>

### <a name="test-the-send-port"></a><span data-ttu-id="d48d3-116">送信ポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="d48d3-116">Test the send port</span></span>

<span data-ttu-id="d48d3-117">単純なを使用するファイルの受信ポートと、Office 365 Outlook の連絡先のアダプターにイベントを作成する場所。</span><span class="sxs-lookup"><span data-stu-id="d48d3-117">You can use a simple File receive port and location to create an event on your Office 365 Outlook Contact adapter.</span></span>

1. <span data-ttu-id="d48d3-118">ファイル アダプターを使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-118">Create a receive port using the File adapter.</span></span> <span data-ttu-id="d48d3-119">内で、受信場所、設定、**受信フォルダー**に \**C:\Temp\In\**、ファイル マスクを設定 **\*.xml**します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-119">Within your receive location,  set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="d48d3-120">送信ポートのプロパティでは、Office 365 Outlook の連絡先のアダプターは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-120">In your Office 365 Outlook Contact adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="d48d3-121">テキスト エディターに貼り付け、ファイルに保存します**Office365Contact.xml**します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-121">Paste the following into a text editor, and save the file as **Office365Contact.xml**.</span></span> <span data-ttu-id="d48d3-122">これは、サンプル メッセージです。</span><span class="sxs-lookup"><span data-stu-id="d48d3-122">This is your sample message.</span></span>

    ```xml
        <ns0:Contact xmlns:ns0="http://schemas.microsoft.com/BizTalk/Office365OutlookContacts/Send">
            <categories>categories_0</categories>
            <categories>categories_1</categories>
            <categories>categories_2</categories>
            <birthday>1999-05-31T13:20:00.000-05:00</birthday>
            <fileAs>fileAs_0</fileAs>
            <displayName>displayName_0</displayName>
            <givenName>givenName_0</givenName>
            <initials>initials_0</initials>
            <middleName>middleName_0</middleName>
            <nickName>nickName_0</nickName>
            <surname>surname_0</surname>
            <title>title_0</title>
            <yomiGivenName>yomiGivenName_0</yomiGivenName>
            <yomiSurname>yomiSurname_0</yomiSurname>
            <yomiCompanyName>yomiCompanyName_0</yomiCompanyName>
            <generation>generation_0</generation>
            <jobTitle>jobTitle_0</jobTitle>
            <companyName>companyName_0</companyName>
            <department>department_0</department>
            <officeLocation>officeLocation_0</officeLocation>
            <profession>profession_0</profession>
            <businessHomePage>businessHomePage_0</businessHomePage>
            <assistantName>assistantName_0</assistantName>
            <manager>manager_0</manager>
            <homePhones>homePhones_0</homePhones>
            <homePhones>homePhones_1</homePhones>
            <mobilePhone>mobilePhone_0</mobilePhone>
            <businessPhones>businessPhones_0</businessPhones>
            <businessPhones>businessPhones_1</businessPhones>
            <spouseName>spouseName_0</spouseName>
            <personalNotes>personalNotes_0</personalNotes>
            <children>children_0</children>
            <children>children_1</children>
            <children>children_2</children>
            <emailAddresses>
                <name>name_0</name>
                <address>address_0</address>
            </emailAddresses>
            <emailAddresses>
                <name>name_0</name>
                <address>address_0</address>
            </emailAddresses>
            <homeAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>10000</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </homeAddress>
            <businessAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>11111</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </businessAddress>
            <otherAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>21222</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </otherAddress>
        </ns0:Contact>
    ```
    <span data-ttu-id="d48d3-123">**XML スキーマは、< BizTalk インストール Folder\SDK\Schemas > 内で SDK の一部として提供されます。**</span><span class="sxs-lookup"><span data-stu-id="d48d3-123">**The XML schema is provided as part of the SDK inside < BizTalk Installation Folder\SDK\Schemas >**</span></span>

4. <span data-ttu-id="d48d3-124">開始ファイルは、場所と Office 365 Outlook の連絡先のアダプターの送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-124">Start the File receive location and the Office 365 Outlook Contact adapter send port.</span></span>
5. <span data-ttu-id="d48d3-125">コピー **Office365Contact.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-125">Copy **Office365Contact.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="d48d3-126">送信ポートでは、xml に基づく、Office 365 Outlook アカウントの連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-126">The send port creates a contact in your Office 365 Outlook account based on the xml.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d48d3-127">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d48d3-127">Next steps</span></span>
<span data-ttu-id="d48d3-128">すべてを参照してください、 [Office 365 アダプター](office365-adapters.md)、インストールまたは[機能パック 3](https://aka.ms/bts2016fp3)します。</span><span class="sxs-lookup"><span data-stu-id="d48d3-128">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>