---
title: Office 365 Outlook メール アダプターを使用して、|Microsoft Docs
description: BizTalk Server での Office 365 Outlook メール アダプターを使用して電子メール メッセージを送受信します。 これを行うには、受信ポートを作成し、送信ポート、電子メール アダプターを使用してサンプル メッセージを使用して、ポートをテストします。
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
ms.openlocfilehash: 58183ce30236ccca39b9c8345959c4785de46ae9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752637"
---
# <a name="send-and-receive-email-with-office-365-outlook-email-adapter---biztalk-server"></a><span data-ttu-id="bf431-104">Office 365 Outlook メールのアダプターの BizTalk Server で電子メールの送受信</span><span class="sxs-lookup"><span data-stu-id="bf431-104">Send and receive email with Office 365 Outlook Email adapter - BizTalk Server</span></span>

<span data-ttu-id="bf431-105">Office 365 Outlook メール アダプターを使用すると、BizTalk からは、Office 365 Outlook メールからメールを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="bf431-105">The Office 365 Outlook Email Adapter allows you to send and receive mails from your Office 365 Outlook Email from BizTalk.</span></span>

## <a name="send-mail-using-a-send-port"></a><span data-ttu-id="bf431-106">送信ポートを使用してメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="bf431-106">Send mail using a send port</span></span>

1. <span data-ttu-id="bf431-107">右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="bf431-108">[送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf431-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="bf431-109">入力、**名前**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-109">Enter a **Name**.</span></span> <span data-ttu-id="bf431-110">**トランスポート**、設定、**型**に**Office 365 Outlook メール**を選択し、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-110">In **Transport**, set the **Type** to **Office 365 Outlook Email**, and select **Configure**.</span></span>

3. <span data-ttu-id="bf431-111">選択**にサインインしています.**、し、Office 365 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="bf431-111">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="bf431-112">アカウントは、電子メール アドレスに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bf431-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="bf431-113">BizTalk Server の承認にアクセスする権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="bf431-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 のメールのアクセス許可](../core/media/office365-mail-permissions.png)

5. <span data-ttu-id="bf431-115">Office 365 Outlook メール既定のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bf431-115">Configure your Office 365 Outlook Email default properties:</span></span>

    |<span data-ttu-id="bf431-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf431-116">Use this</span></span>|<span data-ttu-id="bf431-117">目的</span><span class="sxs-lookup"><span data-stu-id="bf431-117">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="bf431-118">**変換先**</span><span class="sxs-lookup"><span data-stu-id="bf431-118">**To**</span></span> | <span data-ttu-id="bf431-119">区切られたメール アドレスを既定値を指定します ';'。(256 文字の最大)</span><span class="sxs-lookup"><span data-stu-id="bf431-119">Specify your default To mail addresses separated by ';' (256 character max)</span></span>|
    | <span data-ttu-id="bf431-120">**Cc**</span><span class="sxs-lookup"><span data-stu-id="bf431-120">**CC**</span></span> | <span data-ttu-id="bf431-121">区切られた、既定 CC メール アドレスを指定します ';'。(256 文字の最大)</span><span class="sxs-lookup"><span data-stu-id="bf431-121">Specify your default CC mail addresses separated by ';' (256 character max)</span></span>|
    | <span data-ttu-id="bf431-122">**[Subject]**</span><span class="sxs-lookup"><span data-stu-id="bf431-122">**Subject**</span></span> | <span data-ttu-id="bf431-123">既定メールの件名を説明します。</span><span class="sxs-lookup"><span data-stu-id="bf431-123">Mention your default mail subject.</span></span> <span data-ttu-id="bf431-124">(256 文字の最大)</span><span class="sxs-lookup"><span data-stu-id="bf431-124">(256 character max)</span></span> |
    | <span data-ttu-id="bf431-125">**重要度**</span><span class="sxs-lookup"><span data-stu-id="bf431-125">**Importance**</span></span> | <span data-ttu-id="bf431-126">重要度の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf431-126">Select your value of Importance.</span></span> <span data-ttu-id="bf431-127">ドロップダウン リストには、値が含まれています。**低**、**標準**と**高**で**標準**既定。</span><span class="sxs-lookup"><span data-stu-id="bf431-127">Dropdown contains values **Low**, **Normal** and **High** with **Normal** being the default.</span></span> |

    <span data-ttu-id="bf431-128">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bf431-128">When finished, your properties look similar to the following:</span></span>

    ![エンドポイントのプロパティ](../core/media/office365-mail-send-properties.png)

6. <span data-ttu-id="bf431-130">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bf431-130">Select **Ok** to save your changes.</span></span>

### <a name="important-details"></a><span data-ttu-id="bf431-131">重要な詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf431-131">Important details</span></span>

1. <span data-ttu-id="bf431-132">送信アダプターを使用してテキスト形式のメッセージのみ送信できます。</span><span class="sxs-lookup"><span data-stu-id="bf431-132">You can only send plain text messages using the send adapter.</span></span>
2. <span data-ttu-id="bf431-133">昇格させたプロパティを使用して、既定のプロパティを更新も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf431-133">The default properties may also be updated using promoted properties:</span></span>

|<span data-ttu-id="bf431-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf431-134">Property</span></span>|<span data-ttu-id="bf431-135">昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="bf431-135">Promoted property</span></span>|
|---|---|
| <span data-ttu-id="bf431-136">**変換先**</span><span class="sxs-lookup"><span data-stu-id="bf431-136">**To**</span></span> | <span data-ttu-id="bf431-137">OfficeMail.To</span><span class="sxs-lookup"><span data-stu-id="bf431-137">OfficeMail.To</span></span> |
| <span data-ttu-id="bf431-138">**Cc**</span><span class="sxs-lookup"><span data-stu-id="bf431-138">**CC**</span></span> | <span data-ttu-id="bf431-139">OfficeMail.CC</span><span class="sxs-lookup"><span data-stu-id="bf431-139">OfficeMail.CC</span></span> |
| <span data-ttu-id="bf431-140">**[Subject]**</span><span class="sxs-lookup"><span data-stu-id="bf431-140">**Subject**</span></span> | <span data-ttu-id="bf431-141">OfficeMail.Subject</span><span class="sxs-lookup"><span data-stu-id="bf431-141">OfficeMail.Subject</span></span> |
| <span data-ttu-id="bf431-142">**重要度**</span><span class="sxs-lookup"><span data-stu-id="bf431-142">**Importance**</span></span> | <span data-ttu-id="bf431-143">OfficeMail.Importance</span><span class="sxs-lookup"><span data-stu-id="bf431-143">OfficeMail.Importance</span></span> |

### <a name="test-your-send-port"></a><span data-ttu-id="bf431-144">送信ポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="bf431-144">Test your send port</span></span>

<span data-ttu-id="bf431-145">単純なを使用するファイルの受信ポートと場所、Office 365 Outlook メールにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bf431-145">You can use a simple File receive port and location to send messages to your Office 365 Outlook Email.</span></span>

1. <span data-ttu-id="bf431-146">ファイル アダプターを使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf431-146">Create a receive port using the File adapter.</span></span> <span data-ttu-id="bf431-147">内で、受信場所、設定、**受信フォルダー**に**c:\\Temp\\で\\**、ファイル マスクを設定 **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="bf431-147">Within your receive location, set the **Receive folder** to **C:\\Temp\\In\\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="bf431-148">送信ポートのプロパティでは、Office 365 Outlook メール アダプターは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。</span><span class="sxs-lookup"><span data-stu-id="bf431-148">In your Office 365 Outlook Email adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="bf431-149">テキスト エディターに貼り付け、ファイルに保存します**Office365Mail.xml**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-149">Paste the following into a text editor, and save the file as **Office365Mail.xml**.</span></span> <span data-ttu-id="bf431-150">これは、サンプル メッセージです。</span><span class="sxs-lookup"><span data-stu-id="bf431-150">This is your sample message.</span></span>

    ```xml
    <ns0:Root xmlns:ns0="http://BizTalk_Server_Project1.Schema1"> 
        <Record> 
            <Name>BizTalk User</Name> 
            <ID>001</ID> 
        </Record> 
    </ns0:Root> 
    ```

4. <span data-ttu-id="bf431-151">開始ファイルは、場所と Office 365 Outlook メール アダプターの送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="bf431-151">Start the File receive location and the Office 365 Outlook Email adapter send port.</span></span>
5. <span data-ttu-id="bf431-152">コピー **Office365Mail.xml**受信フォルダーにサンプル メッセージ (c:\\Temp\\で\\)。</span><span class="sxs-lookup"><span data-stu-id="bf431-152">Copy **Office365Mail.xml** sample message into the receive folder (C:\\Temp\\In\\).</span></span> <span data-ttu-id="bf431-153">送信ポートでは、XML ファイルを電子メールの本文として、Office 365 Outlook メールに送信されます。</span><span class="sxs-lookup"><span data-stu-id="bf431-153">The send port sends the XML file as mail body to your Office 365 Outlook Email.</span></span>

## <a name="receive-email-using-a-receive-port"></a><span data-ttu-id="bf431-154">受信ポートを使用して電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="bf431-154">Receive email using a receive port</span></span>

1. <span data-ttu-id="bf431-155">右クリックし、BizTalk Server 管理コンソールで**受信ポート**を選択します**新規**、選択と**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-155">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span>

    <span data-ttu-id="bf431-156">[受信ポートを作成](../core/how-to-create-a-receive-port.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf431-156">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="bf431-157">名前を入力し、選択**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-157">Enter a name, and select **Receive Locations**.</span></span>

3. <span data-ttu-id="bf431-158">選択**新規**、および**名前**受信場所。</span><span class="sxs-lookup"><span data-stu-id="bf431-158">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="bf431-159">**トランスポート**を選択します**Office 365 Outlook メール**から、**型**クリックしてドロップダウン リスト、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-159">In **Transport**, select **Office 365 Outlook Email** from the **Type** drop-down list, and then select **Configure**.</span></span>

4. <span data-ttu-id="bf431-160">選択 **[サインイン]**、し、Office 365 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="bf431-160">Select **[Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="bf431-161">アカウントは、電子メール アドレスに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bf431-161">The account is auto-populated with your email address.</span></span>

5. <span data-ttu-id="bf431-162">BizTalk Server の承認にアクセスする権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="bf431-162">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 のメールのアクセス許可](../core/media/office365-mail-permissions.png)

6. <span data-ttu-id="bf431-164">構成、**エンドポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bf431-164">Configure the **Endpoint** properties:</span></span>

    |<span data-ttu-id="bf431-165">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf431-165">Use this</span></span>|<span data-ttu-id="bf431-166">目的</span><span class="sxs-lookup"><span data-stu-id="bf431-166">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="bf431-167">**フォルダー**</span><span class="sxs-lookup"><span data-stu-id="bf431-167">**Folder**</span></span> | <span data-ttu-id="bf431-168">電子メールを取得するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf431-168">Select the folder to get email.</span></span> <span data-ttu-id="bf431-169">既定のフォルダーでは、受信トレイです。</span><span class="sxs-lookup"><span data-stu-id="bf431-169">The default folder is Inbox.</span></span> <span data-ttu-id="bf431-170">フォルダーに再帰的な性質がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf431-170">Note that folders aren’t recursive in nature.</span></span> <span data-ttu-id="bf431-171">たとえば、サブフォルダーから電子メールは取得されません。</span><span class="sxs-lookup"><span data-stu-id="bf431-171">For example, email from subfolders aren’t retreived.</span></span> |
    | <span data-ttu-id="bf431-172">**を開始します。**</span><span class="sxs-lookup"><span data-stu-id="bf431-172">**Start from**</span></span> | <span data-ttu-id="bf431-173">Office 365 からメールを受信した方法を入力します。</span><span class="sxs-lookup"><span data-stu-id="bf431-173">Enter how email is received from Office 365.</span></span> <span data-ttu-id="bf431-174">この値は、Office 365 Outlook で電子メールの receivedTimeStamp を示します。</span><span class="sxs-lookup"><span data-stu-id="bf431-174">This value indicates receivedTimeStamp of an email in Office 365 Outlook.</span></span> <span data-ttu-id="bf431-175">入力された値が受信したよりも最近使用した電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="bf431-175">Email more recent than the entered values are received.</span></span>  |
    | <span data-ttu-id="bf431-176">**未読の電子メールを送信**</span><span class="sxs-lookup"><span data-stu-id="bf431-176">**Unread mails only**</span></span> | <span data-ttu-id="bf431-177">未読の電子メールのみを読み取るこれを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf431-177">Check this to read only unread email.</span></span> <span data-ttu-id="bf431-178">すべての電子メールを読み取るチェックを行わないようにします。</span><span class="sxs-lookup"><span data-stu-id="bf431-178">Keep it unchecked to read all email.</span></span> |
    | <span data-ttu-id="bf431-179">**後のアクション**</span><span class="sxs-lookup"><span data-stu-id="bf431-179">**Post Action**</span></span> | <span data-ttu-id="bf431-180">電子メールを読み取った後に実行される post アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf431-180">Select a post action to be performed after an email is read.</span></span> <span data-ttu-id="bf431-181">**None** 、既定値は、BizTalk でメールを受信した後は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="bf431-181">**None** is the default, and does nothing after email is received by BizTalk.</span></span> <span data-ttu-id="bf431-182">**既読としてマーク**BizTalk で、電子メールを受信した後に、メールボックスの電子メールが既読としてマークされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bf431-182">**Mark as read** implies, that after an email is received by BizTalk, the email in your mailbox is marked as read.</span></span> <span data-ttu-id="bf431-183">**削除**BizTalk で、電子メールを受信した後、メールボックスの電子メールが削除されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bf431-183">**Delete** implies, that after an email is received by BizTalk, the email in your mailbox is deleted.</span></span> <span data-ttu-id="bf431-184">後の操作は、ベスト エフォートで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf431-184">Post actions are performed on a best-effort basis.</span></span>|

    <span data-ttu-id="bf431-185">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bf431-185">When finished, your properties look similar to the following:</span></span>

    ![エンドポイントのプロパティ](../core/media/office365-mail-receive-properties.png)

7. <span data-ttu-id="bf431-187">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bf431-187">Select **Ok** to save your changes.</span></span>

### <a name="test-your-receive-settings"></a><span data-ttu-id="bf431-188">テストの設定を受け取る</span><span class="sxs-lookup"><span data-stu-id="bf431-188">Test your receive settings</span></span>

<span data-ttu-id="bf431-189">単純な File 送信ポートを使用するから Office 365 の Outlook 電子メール メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="bf431-189">You can use a simple File send port to receive messages from your Office 365 Outlook Email.</span></span>

1. <span data-ttu-id="bf431-190">ファイル アダプターを使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf431-190">Create a send port using the File adapter.</span></span> <span data-ttu-id="bf431-191">送信ポートのプロパティ内で、設定、**先フォルダー**に**c:\\Temp\\アウト\\**、設定と**ファイル名**に **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="bf431-191">Within your send port properties, set the **Destination folder** to **C:\\Temp\\Out\\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="bf431-192">ファイルの送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。</span><span class="sxs-lookup"><span data-stu-id="bf431-192">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="bf431-193">開始、Office 365 Outlook の電子メールは受信場所および File 送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="bf431-193">Start the Office 365 Outlook Email receive location and the File send port.</span></span>
4. <span data-ttu-id="bf431-194">保存先フォルダー (c:\temp\out) にメッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="bf431-194">Look for messages in the destination folder (c:\temp\out).</span></span>

### <a name="promoted-properties-from-receive-pipeline"></a><span data-ttu-id="bf431-195">受信パイプラインから昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="bf431-195">Promoted Properties from receive pipeline</span></span>

<span data-ttu-id="bf431-196">既定では、受信パイプラインから、次のプロパティが昇格されます。</span><span class="sxs-lookup"><span data-stu-id="bf431-196">The following properties from the Receive Pipeline are promoted by default:</span></span>

|<span data-ttu-id="bf431-197">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="bf431-197">Property Name</span></span>| <span data-ttu-id="bf431-198">昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="bf431-198">Promoted Property</span></span>|
|---|---|
| <span data-ttu-id="bf431-199">**重要度**</span><span class="sxs-lookup"><span data-stu-id="bf431-199">**Importance**</span></span> | <span data-ttu-id="bf431-200">OfficeMail.ReceivedMailImportance</span><span class="sxs-lookup"><span data-stu-id="bf431-200">OfficeMail.ReceivedMailImportance</span></span> |
| <span data-ttu-id="bf431-201">**[Subject]**</span><span class="sxs-lookup"><span data-stu-id="bf431-201">**Subject**</span></span> | <span data-ttu-id="bf431-202">OfficeMail.ReceivedMailSubject</span><span class="sxs-lookup"><span data-stu-id="bf431-202">OfficeMail.ReceivedMailSubject</span></span> |
| <span data-ttu-id="bf431-203">**依頼**</span><span class="sxs-lookup"><span data-stu-id="bf431-203">**SenderName**</span></span> | <span data-ttu-id="bf431-204">OfficeMail.SenderName</span><span class="sxs-lookup"><span data-stu-id="bf431-204">OfficeMail.SenderName</span></span> |
| <span data-ttu-id="bf431-205">**SenderAddress**</span><span class="sxs-lookup"><span data-stu-id="bf431-205">**SenderAddress**</span></span> | <span data-ttu-id="bf431-206">OfficeMail.SenderAddress</span><span class="sxs-lookup"><span data-stu-id="bf431-206">OfficeMail.SenderAddress</span></span> |
| <span data-ttu-id="bf431-207">**添付ファイル付き**</span><span class="sxs-lookup"><span data-stu-id="bf431-207">**HasAttachments**</span></span>| <span data-ttu-id="bf431-208">OfficeMail.HasAttachments</span><span class="sxs-lookup"><span data-stu-id="bf431-208">OfficeMail.HasAttachments</span></span> |

> [!NOTE]
> <span data-ttu-id="bf431-209">電子メールの本文の内容のみ、メッセージに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bf431-209">Only the body content of the Email is passed through to the message.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf431-210">次の手順</span><span class="sxs-lookup"><span data-stu-id="bf431-210">Next steps</span></span>
<span data-ttu-id="bf431-211">すべてを参照してください、 [Office 365 アダプター](office365-adapters.md)、インストールまたは[機能パック 3](https://aka.ms/bts2016fp3)します。</span><span class="sxs-lookup"><span data-stu-id="bf431-211">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>