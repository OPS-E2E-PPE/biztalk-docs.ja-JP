---
title: Office 365 Outlook カレンダー アダプターを使用して、|Microsoft Docs
description: BizTalk Server、Office 365 Outlook カレンダー アダプターを使用してメッセージを送受信します。 アダプターを使用して作成し、受信ポートを使用して予定表イベントを受信し、送信ポート、およびサンプル XML メッセージを使用して、カレンダー イベントを作成します。
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
ms.openlocfilehash: ab724870e9c75a60119e86f7f62d6823f1db9873
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946220"
---
# <a name="create-calendar-events-with-the-office-365-outlook-calendar-adapter---biztalk-server"></a>Office 365 Outlook の予定表のアダプターの BizTalk Server を使用した予定表イベントを作成します。

BizTalk Server で、Office 365 Outlook カレンダー アダプターを使用して、作成から Office 365 Outlook カレンダーの予定表イベントを受信します。

## <a name="create-events-using-a-send-port"></a>送信ポートを使用してイベントを作成します。

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。

    [送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。

2. 入力、**名前**します。 **トランスポート**、設定、**型**に**Office 365 Outlook の予定表**を選択し、**構成**します。

3. 選択 **[サインイン]**、し、Office 365 アカウントにサインインします。 アカウントは、電子メール アドレスに自動的に設定されます。

4. BizTalk Server の承認にアクセスする権限を許可します。

    ![Office 365 カレンダーのアクセス許可](../core/media/office365-calendar-permissions.png)

5. Office 365 Outlook カレンダー既定のプロパティを構成します。

    |プロパティ|目的|  
    |---|---|  
    | **予定表** | イベントの作成を予定表を選択します。 |
    | **[Subject]** | 作成されたイベントの既定の件名を設定します。 (256 文字の最大) |
    | **必須出席者** | 区切られた、必要な既定の出席者のメール アドレスを入力 ';'。 (256 文字の最大) |
    | **任意出席者** | 任意出席者のメール アドレスを既定値を入力します。 ';'。 (256 文字の最大) |

6. カレンダーを選択します。 

    ![Office 365 カレンダー](../core/media/office365-calendars.png)

    完了したらのプロパティは、次のようになります。

    ![エンドポイントのプロパティ](../core/media/office365-calendar-send-properties.png)

7. 選択**Ok**変更を保存します。

### <a name="test-your-send-port"></a>送信ポートをテストします。

単純なを使用するファイルの受信ポートと、Office 365 Outlook カレンダーにイベントを作成する場所。

1. ファイル アダプターを使用して受信ポートを作成します。 内で、受信場所、設定、**受信フォルダー**に **C:\Temp\In\**、ファイル マスクを設定 **\*.xml**します。
2. 送信ポートのプロパティでは、Office 365 Outlook カレンダー アダプターは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。
3. テキスト エディターに貼り付け、ファイルに保存します**Office365Calendar.xml**します。 これは、サンプル メッセージです。

    ```xml
    <Event xmlns="http://schemas.microsoft.com/BizTalk/Office365OutlookCalendar/Send"> 
        <subject>Test event 1</subject> 
        <body> 
        <contentType>html</contentType> 
        <content>&lt;html&gt; 
        &lt;head&gt; 
        &lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt; 
        &lt;meta content="text/html; charset=us-ascii"&gt; 
        &lt;/head&gt; 
        &lt;body&gt; 
        Test body for event Test event 1 
        &lt;/body&gt; 
        &lt;/html&gt; 
        </content> 
        </body> 
    </Event> 
    ```
    **XML スキーマは、< BizTalk インストール Folder\SDK\Schemas > 内で SDK の一部として提供されます。**

4. 開始ファイルは、場所と Office 365 Outlook カレンダー アダプターの送信ポートを受信します。
5. コピー **Office365Calendar.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。 送信ポートは、xml に基づく、Office 365 Outlook カレンダーにイベントを作成します。

## <a name="receive-events-using-a-receive-port"></a>受信ポートを使用してイベントを受信します。

1. 右クリックし、BizTalk Server 管理コンソールで**受信ポート**を選択します**新規**、選択と**一方向受信ポート**します。

    [受信ポートを作成](../core/how-to-create-a-receive-port.md)いくつかのガイダンスを提供します。

2. 名前を入力し、選択**受信場所**します。

3. 選択**新規**、および**名前**受信場所。 **トランスポート**を選択します**Office 365 Outlook カレンダー**から、**型**クリックしてドロップダウン リスト、**構成**します。

4. 選択**にサインインしています.**、し、Office 365 アカウントにサインインします。 アカウントは、電子メール アドレスに自動的に設定されます。

5. BizTalk Server の承認にアクセスする権限を許可します。

    ![Office 365 カレンダーのアクセス許可](../core/media/office365-calendar-permissions.png)

6. 構成、**エンドポイント**プロパティ。

    |プロパティ|目的|  
    |---|---|  
    | **予定表** | イベントのフェッチ元となるカレンダーを選択します。  |
    | **内で開始** | (既定値は 15 分) を BizTalk で受信するために開始する予定表イベント必要がある時間間隔を選択します。  |

7. カレンダーを選択します。

    ![Office 365 カレンダー](../core/media/office365-calendars.png)

    完了したらのプロパティは、次のようになります。

    ![エンドポイントのプロパティ](../core/media/office365-calendar-receive-properties.png)

8. 選択**Ok**変更を保存します。

### <a name="test-your-receive-settings"></a>テストの設定を受け取る

単純な File 送信ポートを使用すると、Office 365 Outlook カレンダーからメッセージを受信します。

1. ファイル アダプターを使用して送信ポートを作成します。 送信ポートのプロパティ内で次のように設定します、**先フォルダー**に **C:\Temp\Out\**、設定、および**ファイル名**に **%MessageID%.xml**。
2. ファイルの送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。
3. Office 365 Outlook の予定表の開始には、場所とファイルの送信ポートが表示されます。
4. 保存先フォルダー (c:\temp\out) にメッセージを探します。 
**XML スキーマが SDK に含まれる`\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`します。**

### <a name="example-of-a-received-calendar-event-xml"></a>受信した予定表イベントの xml の例

```xml
<ns0:Event xmlns:ns0="http://schemas.microsoft.com/BizTalk/Office365OutlookCalendar/Receive"> 
<reminderMinutesBeforeStart>20160</reminderMinutesBeforeStart> 
<importance>normal</importance> 
<subject>Let's meet</subject> 
<id>AQMkADAwATNiZmYAZC0xMQBlOC0yODQ1LTA</id> 
<body> 
<contentType>html</contentType> 
<content>&lt;html&gt; 
&lt;head&gt; 
&lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt; 
&lt;meta content="text/html; charset=us-ascii"&gt; 
&lt;meta name="ProgId" content="Word.Document"&gt; 
&lt;meta name="Generator" content="Microsoft Word 15"&gt; 
&lt;meta name="Originator" content="Microsoft Word 15"&gt; 
&lt;link rel="File-List" href="cid:filelist.xml@01D40724.27036CE0"&gt;&lt;style&gt; 
&lt;!-- 
@font-face 
  {font-family:"Cambria Math"} 
@font-face 
  {font-family:Calibri} 
p.MsoNormal, li.MsoNormal, div.MsoNormal 
  {margin:0in; 
  margin-bottom:.0001pt; 
  font-size:11.0pt; 
  font-family:"Calibri",sans-serif} 
a:link, span.MsoHyperlink 
  {color:#0563C1; 
  text-decoration:underline} 
a:visited, span.MsoHyperlinkFollowed 
  {color:#954F72; 
  text-decoration:underline} 
span.EmailStyle17 
  {font-family:"Calibri",sans-serif; 
  color:windowtext} 
.MsoChpDefault 
  {font-family:"Calibri",sans-serif} 
@page WordSection1 
  {margin:1.0in 1.0in 1.0in 1.0in} 
div.WordSection1 
  {} 
--&gt; 
&lt;/style&gt; 
&lt;/head&gt; 
&lt;body lang="EN-US" link="#0563C1" vlink="#954F72" style=""&gt; 
&lt;div class="WordSection1"&gt; 
&lt;p class="MsoNormal"&gt;Let’s sync up.&lt;/p&gt; 
&lt;/div&gt; 
&lt;/body&gt; 
&lt;/html&gt; 
</content> 
</body> 
<bodyPreview>Let’s sync up.</bodyPreview> 
<attendees> 
<type>required</type> 
<status> 
<response>none</response> 
<time>0001-01-01T00:00:00Z</time> 
</status> 
<emailAddress> 
<name>someone@contoso.com</name> 
<address>someone@contoso.com</address> 
</emailAddress> 
</attendees> 
<start> 
<dateTime>2018-06-25T17:00:00</dateTime> 
<timeZone>UTC</timeZone> 
</start> 
<end> 
<dateTime>2018-06-25T17:30:00</dateTime> 
<timeZone>UTC</timeZone> 
</end> 
<location> 
<displayName>Your office</displayName> 
<locationType>default</locationType> 
<uniqueId>Your office</uniqueId> 
<uniqueIdType>private</uniqueIdType> 
</location> 
<responseRequested>true</responseRequested> 
<seriesMasterId /> 
<isCancelled>false</isCancelled> 
<isOrganizer>true</isOrganizer> 
<createdDateTime>2018-06-18T23:48:35.0164728Z</createdDateTime> 
<lastModifiedDateTime>2018-06-18T23:48:22.178Z</lastModifiedDateTime> 
<hasAttachments>false</hasAttachments> 
<responseStatus> 
<response>none</response> 
<time>0001-01-01T00:00:00Z</time> 
</responseStatus> 
<changeKey>SFa3sLJfdiDEIpfwAAIAU=</changeKey> 
<originalStartTimeZone>Pacific Standard Time</originalStartTimeZone> 
<originalEndTimeZone>Pacific Standard Time</originalEndTimeZone> 
<isReminderOn>false</isReminderOn> 
<sensitivity>normal</sensitivity> 
<isAllDay>false</isAllDay> 
<showAs>busy</showAs> 
<type>singleInstance</type> 
<onlineMeetingUrl /> 
<recurrence /> 
<locations> 
<displayName>Your office</displayName> 
<locationType>default</locationType> 
<uniqueId>Your office</uniqueId> 
<uniqueIdType>private</uniqueIdType> 
</locations> 
<organizer> 
<emailAddress> 
<name>someone@contoso.com</name> 
<address>/O=FIRST ORGANIZATION/OU=EXCHANGE ADMINISTRATIVE GROUP(FYDIBOH3SPDLT)/CN=RECIPIENTS/CN=0003B11E8245</address> 
</emailAddress> 
</organizer> 
</ns0:Event> 
```

## <a name="next-steps"></a>次のステップ
すべてを参照してください、 [Office 365 アダプター](office365-adapters.md)、インストールまたは[機能パック 3](https://aka.ms/bts2016fp3)します。