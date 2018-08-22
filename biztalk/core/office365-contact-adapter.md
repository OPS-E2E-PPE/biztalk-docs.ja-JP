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
# <a name="create-a-contact-using-the-office-365-outlook-contact-adapter---biztalk-server"></a>Office 365 Outlook の連絡先のアダプターの BizTalk Server を使用して連絡先を作成します。

BizTalk Server で、Office 365 Outlook の連絡先のアダプターを使用して、Office 365 Outlook の連絡先を作成します。

## <a name="create-a-contact-using-a-send-port"></a>送信ポートを使用して連絡先を作成します。

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。

    [送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。

2. 入力、**名前**します。 **トランスポート**、設定、**型**に**Office 365 Outlook の連絡先**を選択し、**構成**します。

3. 選択**にサインインしています.**、し、Office 365 アカウントにサインインします。 アカウントは、電子メール アドレスに自動的に設定されます。

4. BizTalk Server の承認にアクセスする権限を許可します。

    ![Office 365 の連絡先のアクセス許可](../core/media/office365-contact-permissions.png)

5. 選択**Ok**変更を保存します。

### <a name="test-the-send-port"></a>送信ポートをテストします。

単純なを使用するファイルの受信ポートと、Office 365 Outlook の連絡先のアダプターにイベントを作成する場所。

1. ファイル アダプターを使用して受信ポートを作成します。 内で、受信場所、設定、**受信フォルダー**に **C:\Temp\In\**、ファイル マスクを設定 **\*.xml**します。
2. 送信ポートのプロパティでは、Office 365 Outlook の連絡先のアダプターは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。
3. テキスト エディターに貼り付け、ファイルに保存します**Office365Contact.xml**します。 これは、サンプル メッセージです。

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
    **XML スキーマは、< BizTalk インストール Folder\SDK\Schemas > 内で SDK の一部として提供されます。**

4. 開始ファイルは、場所と Office 365 Outlook の連絡先のアダプターの送信ポートを受信します。
5. コピー **Office365Contact.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。 送信ポートでは、xml に基づく、Office 365 Outlook アカウントの連絡先を作成します。

## <a name="next-steps"></a>次のステップ
すべてを参照してください、 [Office 365 アダプター](office365-adapters.md)、インストールまたは[機能パック 3](https://aka.ms/bts2016fp3)します。