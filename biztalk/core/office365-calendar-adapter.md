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
ms.openlocfilehash: 6787ece4af5ebdd17733dde33ae524f2c9b802e8
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752650"
---
# <a name="create-calendar-events-with-the-office-365-outlook-calendar-adapter---biztalk-server"></a><span data-ttu-id="8bae0-104">Office 365 Outlook の予定表のアダプターの BizTalk Server を使用した予定表イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-104">Create calendar events with the Office 365 Outlook Calendar adapter - BizTalk Server</span></span>

<span data-ttu-id="8bae0-105">BizTalk Server で、Office 365 Outlook カレンダー アダプターを使用して、作成から Office 365 Outlook カレンダーの予定表イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-105">Use the Office 365 Outlook Calendar adapter in BizTalk Server to create and receive calendar events from your Office 365 Outlook Calendar.</span></span>

## <a name="create-events-using-a-send-port"></a><span data-ttu-id="8bae0-106">送信ポートを使用してイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-106">Create events using a send port</span></span>

1. <span data-ttu-id="8bae0-107">右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="8bae0-108">[送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="8bae0-109">入力、**名前**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-109">Enter a **Name**.</span></span> <span data-ttu-id="8bae0-110">**トランスポート**、設定、**型**に**Office 365 Outlook の予定表**を選択し、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-110">In **Transport**, set the **Type** to **Office 365 Outlook Calendar**, and select **Configure**.</span></span>

3. <span data-ttu-id="8bae0-111">選択 **[サインイン]**、し、Office 365 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8bae0-111">Select **[Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="8bae0-112">アカウントは、電子メール アドレスに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8bae0-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="8bae0-113">BizTalk Server の承認にアクセスする権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 カレンダーのアクセス許可](../core/media/office365-calendar-permissions.png)

5. <span data-ttu-id="8bae0-115">Office 365 Outlook カレンダー既定のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-115">Configure your Office365 Outlook Calendar default properties:</span></span>

    |<span data-ttu-id="8bae0-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8bae0-116">Use this</span></span>|<span data-ttu-id="8bae0-117">目的</span><span class="sxs-lookup"><span data-stu-id="8bae0-117">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="8bae0-118">**予定表**</span><span class="sxs-lookup"><span data-stu-id="8bae0-118">**Calendar**</span></span> | <span data-ttu-id="8bae0-119">イベントの作成を予定表を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-119">Select the calendar in which events will be created.</span></span> |
    | <span data-ttu-id="8bae0-120">**[Subject]**</span><span class="sxs-lookup"><span data-stu-id="8bae0-120">**Subject**</span></span> | <span data-ttu-id="8bae0-121">作成されたイベントの既定の件名を設定します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-121">Set the default subject for events created.</span></span> <span data-ttu-id="8bae0-122">(256 文字の最大)</span><span class="sxs-lookup"><span data-stu-id="8bae0-122">(256 character max)</span></span> |
    | <span data-ttu-id="8bae0-123">**必須出席者**</span><span class="sxs-lookup"><span data-stu-id="8bae0-123">**Required Attendees**</span></span> | <span data-ttu-id="8bae0-124">区切られた、必要な既定の出席者のメール アドレスを入力 ';'。</span><span class="sxs-lookup"><span data-stu-id="8bae0-124">Enter your default required attendees email addresses separated by ';'.</span></span> <span data-ttu-id="8bae0-125">(256 文字の最大)</span><span class="sxs-lookup"><span data-stu-id="8bae0-125">(256 character max)</span></span> |
    | <span data-ttu-id="8bae0-126">**任意出席者**</span><span class="sxs-lookup"><span data-stu-id="8bae0-126">**Optional Attendees**</span></span> | <span data-ttu-id="8bae0-127">任意出席者のメール アドレスを既定値を入力します。 ';'。</span><span class="sxs-lookup"><span data-stu-id="8bae0-127">Enter your default optional attendees email addresses separated by ';'.</span></span> <span data-ttu-id="8bae0-128">(256 文字の最大)</span><span class="sxs-lookup"><span data-stu-id="8bae0-128">(256 character max)</span></span> |

6. <span data-ttu-id="8bae0-129">カレンダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-129">Select a calendar:</span></span> 

    ![Office 365 カレンダー](../core/media/office365-calendars.png)

    <span data-ttu-id="8bae0-131">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8bae0-131">When finished, your properties look similar to the following:</span></span>

    ![エンドポイントのプロパティ](../core/media/office365-calendar-send-properties.png)

7. <span data-ttu-id="8bae0-133">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-133">Select **Ok** to save your changes.</span></span>

### <a name="test-your-send-port"></a><span data-ttu-id="8bae0-134">送信ポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="8bae0-134">Test your send port</span></span>

<span data-ttu-id="8bae0-135">単純なを使用するファイルの受信ポートと、Office 365 Outlook カレンダーにイベントを作成する場所。</span><span class="sxs-lookup"><span data-stu-id="8bae0-135">You can use a simple File receive port and location to create an event on your Office 365 Outlook Calendar.</span></span>

1. <span data-ttu-id="8bae0-136">ファイル アダプターを使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-136">Create a receive port using the File adapter.</span></span> <span data-ttu-id="8bae0-137">内で、受信場所、設定、**受信フォルダー**に**c:\\Temp\\で\\**、ファイル マスクを設定 **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="8bae0-137">Within your receive location,  set the **Receive folder** to **C:\\Temp\\In\\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="8bae0-138">送信ポートのプロパティでは、Office 365 Outlook カレンダー アダプターは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-138">In your Office 365 Outlook Calendar adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="8bae0-139">テキスト エディターに貼り付け、ファイルに保存します**Office365Calendar.xml**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-139">Paste the following into a text editor, and save the file as **Office365Calendar.xml**.</span></span> <span data-ttu-id="8bae0-140">これは、サンプル メッセージです。</span><span class="sxs-lookup"><span data-stu-id="8bae0-140">This is your sample message.</span></span>

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
    <span data-ttu-id="8bae0-141">**XML スキーマは、< BizTalk インストール Folder\SDK\Schemas > 内で SDK の一部として提供されます。**</span><span class="sxs-lookup"><span data-stu-id="8bae0-141">**The XML schema is provided as part of the SDK inside < BizTalk Installation Folder\SDK\Schemas >**</span></span>

4. <span data-ttu-id="8bae0-142">開始ファイルは、場所と Office 365 Outlook カレンダー アダプターの送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-142">Start the File receive location and the Office 365 Outlook Calendar adapter send port.</span></span>
5. <span data-ttu-id="8bae0-143">コピー **Office365Calendar.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-143">Copy **Office365Calendar.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="8bae0-144">送信ポートは、xml に基づく、Office 365 Outlook カレンダーにイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-144">The send port creates an event in your Office 365 Outlook calendar based on the xml.</span></span>

## <a name="receive-events-using-a-receive-port"></a><span data-ttu-id="8bae0-145">受信ポートを使用してイベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-145">Receive events using a receive port</span></span>

1. <span data-ttu-id="8bae0-146">右クリックし、BizTalk Server 管理コンソールで**受信ポート**を選択します**新規**、選択と**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-146">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span>

    <span data-ttu-id="8bae0-147">[受信ポートを作成](../core/how-to-create-a-receive-port.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-147">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="8bae0-148">名前を入力し、選択**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-148">Enter a name, and select **Receive Locations**.</span></span>

3. <span data-ttu-id="8bae0-149">選択**新規**、および**名前**受信場所。</span><span class="sxs-lookup"><span data-stu-id="8bae0-149">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="8bae0-150">**トランスポート**を選択します**Office 365 Outlook カレンダー**から、**型**クリックしてドロップダウン リスト、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-150">In **Transport**, select **Office 365 Outlook Calendar** from the **Type** drop-down list, and then select **Configure**.</span></span>

4. <span data-ttu-id="8bae0-151">選択**にサインインしています.**、し、Office 365 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8bae0-151">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="8bae0-152">アカウントは、電子メール アドレスに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8bae0-152">The account is auto-populated with your email address.</span></span>

5. <span data-ttu-id="8bae0-153">BizTalk Server の承認にアクセスする権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-153">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 カレンダーのアクセス許可](../core/media/office365-calendar-permissions.png)

6. <span data-ttu-id="8bae0-155">構成、**エンドポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8bae0-155">Configure the **Endpoint** properties:</span></span>

    |<span data-ttu-id="8bae0-156">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8bae0-156">Use this</span></span>|<span data-ttu-id="8bae0-157">目的</span><span class="sxs-lookup"><span data-stu-id="8bae0-157">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="8bae0-158">**予定表**</span><span class="sxs-lookup"><span data-stu-id="8bae0-158">**Calendar**</span></span> | <span data-ttu-id="8bae0-159">イベントのフェッチ元となるカレンダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-159">Select the calendar from which events will be fetched.</span></span>  |
    | <span data-ttu-id="8bae0-160">**内で開始**</span><span class="sxs-lookup"><span data-stu-id="8bae0-160">**Starting within**</span></span> | <span data-ttu-id="8bae0-161">(既定値は 15 分) を BizTalk で受信するために開始する予定表イベント必要がある時間間隔を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-161">Select the time interval within which a calendar event has to start in order to be received by BizTalk (default is 15 minutes).</span></span>  |

7. <span data-ttu-id="8bae0-162">カレンダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-162">Selecting a calendar:</span></span>

    ![Office 365 カレンダー](../core/media/office365-calendars.png)

    <span data-ttu-id="8bae0-164">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8bae0-164">When finished, your properties look similar to the following:</span></span>

    ![エンドポイントのプロパティ](../core/media/office365-calendar-receive-properties.png)

8. <span data-ttu-id="8bae0-166">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-166">Select **Ok** to save your changes.</span></span>

### <a name="test-your-receive-settings"></a><span data-ttu-id="8bae0-167">テストの設定を受け取る</span><span class="sxs-lookup"><span data-stu-id="8bae0-167">Test your receive settings</span></span>

<span data-ttu-id="8bae0-168">単純な File 送信ポートを使用すると、Office 365 Outlook カレンダーからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-168">You can use a simple File send port to receive messages from your Office 365 Outlook Calendar.</span></span>

1. <span data-ttu-id="8bae0-169">ファイル アダプターを使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-169">Create a send port using the File adapter.</span></span> <span data-ttu-id="8bae0-170">送信ポートのプロパティ内で、設定、**先フォルダー**に**c:\\Temp\\アウト\\**、設定と**ファイル名**に **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-170">Within your send port properties, set the **Destination folder** to **C:\\Temp\\Out\\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="8bae0-171">ファイルの送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-171">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="8bae0-172">Office 365 Outlook の予定表の開始には、場所とファイルの送信ポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bae0-172">Start the Office 365 Outlook Calendar receive location and the File send port.</span></span>
4. <span data-ttu-id="8bae0-173">保存先フォルダー (c:\temp\out) にメッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-173">Look for messages in the destination folder (c:\temp\out).</span></span> 
<span data-ttu-id="8bae0-174">**XML スキーマが SDK に含まれる`\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`します。**</span><span class="sxs-lookup"><span data-stu-id="8bae0-174">**The XML schema is included in the SDK at `\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`.**</span></span>

### <a name="example-of-a-received-calendar-event-xml"></a><span data-ttu-id="8bae0-175">受信した予定表イベントの xml の例</span><span class="sxs-lookup"><span data-stu-id="8bae0-175">Example of a received calendar event xml</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="8bae0-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="8bae0-176">Next steps</span></span>
<span data-ttu-id="8bae0-177">すべてを参照してください、 [Office 365 アダプター](office365-adapters.md)、インストールまたは[機能パック 3](https://aka.ms/bts2016fp3)します。</span><span class="sxs-lookup"><span data-stu-id="8bae0-177">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>