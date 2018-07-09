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
ms.openlocfilehash: daea28056180b436f226fa32b6179bfb1e091f7a
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946214"
---
# <a name="send-and-receive-email-with-office-365-outlook-email-adapter---biztalk-server"></a>Office 365 Outlook メールのアダプターの BizTalk Server で電子メールの送受信

Office 365 Outlook メール アダプターを使用すると、BizTalk からは、Office 365 Outlook メールからメールを送受信できます。

## <a name="send-mail-using-a-send-port"></a>送信ポートを使用してメールを送信します。

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。

    [送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。

2. 入力、**名前**します。 **トランスポート**、設定、**型**に**Office 365 Outlook メール**を選択し、**構成**します。

3. 選択**にサインインしています.**、し、Office 365 アカウントにサインインします。 アカウントは、電子メール アドレスに自動的に設定されます。

4. BizTalk Server の承認にアクセスする権限を許可します。

    ![Office 365 のメールのアクセス許可](../core/media/office365-mail-permissions.png)

5. Office 365 Outlook メール既定のプロパティを構成します。

    |プロパティ|目的|  
    |---|---|  
    | **変換先** | 区切られたメール アドレスを既定値を指定します ';'。(256 文字の最大)|
    | **Cc** | 区切られた、既定 CC メール アドレスを指定します ';'。(256 文字の最大)|
    | **[Subject]** | 既定メールの件名を説明します。 (256 文字の最大) |
    | **重要度** | 重要度の値を選択します。 ドロップダウン リストには、値が含まれています。**低**、**標準**と**高**で**標準**既定。 |

    完了したらのプロパティは、次のようになります。

    ![エンドポイントのプロパティ](../core/media/office365-mail-send-properties.png)

6. 選択**Ok**変更を保存します。

### <a name="important-details"></a>重要な詳細情報

1. 送信アダプターを使用してテキスト形式のメッセージのみ送信できます。
2. 昇格させたプロパティを使用して、既定のプロパティを更新も可能性があります。

|プロパティ|昇格させたプロパティ|
|---|---|
| **変換先** | OfficeMail.To |
| **Cc** | OfficeMail.CC |
| **[Subject]** | OfficeMail.Subject |
| **重要度** | OfficeMail.Importance |

### <a name="test-your-send-port"></a>送信ポートをテストします。

単純なを使用するファイルの受信ポートと場所、Office 365 Outlook メールにメッセージを送信します。

1. ファイル アダプターを使用して受信ポートを作成します。 内で、受信場所、設定、**受信フォルダー**に **C:\Temp\In\**、ファイル マスクを設定 **\*.xml**します。
2. 送信ポートのプロパティでは、Office 365 Outlook メール アダプターは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。
3. テキスト エディターに貼り付け、ファイルに保存します**Office365Mail.xml**します。 これは、サンプル メッセージです。

    ```xml
    <ns0:Root xmlns:ns0="http://BizTalk_Server_Project1.Schema1"> 
        <Record> 
            <Name>BizTalk User</Name> 
            <ID>001</ID> 
        </Record> 
    </ns0:Root> 
    ```

4. 開始ファイルは、場所と Office 365 Outlook メール アダプターの送信ポートを受信します。
5. コピー **Office365Mail.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。 送信ポートでは、XML ファイルを電子メールの本文として、Office 365 Outlook メールに送信されます。

## <a name="receive-email-using-a-receive-port"></a>受信ポートを使用して電子メールを受信します。

1. 右クリックし、BizTalk Server 管理コンソールで**受信ポート**を選択します**新規**、選択と**一方向受信ポート**します。

    [受信ポートを作成](../core/how-to-create-a-receive-port.md)いくつかのガイダンスを提供します。

2. 名前を入力し、選択**受信場所**します。

3. 選択**新規**、および**名前**受信場所。 **トランスポート**を選択します**Office 365 Outlook メール**から、**型**クリックしてドロップダウン リスト、**構成**します。

4. 選択 **[サインイン]**、し、Office 365 アカウントにサインインします。 アカウントは、電子メール アドレスに自動的に設定されます。

5. BizTalk Server の承認にアクセスする権限を許可します。

    ![Office 365 のメールのアクセス許可](../core/media/office365-mail-permissions.png)

6. 構成、**エンドポイント**プロパティ。

    |プロパティ|目的|  
    |---|---|  
    | **フォルダー** | 電子メールを取得するフォルダーを選択します。 既定のフォルダーでは、受信トレイです。 フォルダーに再帰的な性質がないことに注意してください。 たとえば、サブフォルダーから電子メールは取得されません。 |
    | **を開始します。** | Office 365 からメールを受信した方法を入力します。 この値は、Office 365 Outlook で電子メールの receivedTimeStamp を示します。 入力された値が受信したよりも最近使用した電子メール アドレス。  |
    | **未読の電子メールを送信** | 未読の電子メールのみを読み取るこれを確認します。 すべての電子メールを読み取るチェックを行わないようにします。 |
    | **後のアクション** | 電子メールを読み取った後に実行される post アクションを選択します。 **None** 、既定値は、BizTalk でメールを受信した後は何も行いません。 **既読としてマーク**BizTalk で、電子メールを受信した後に、メールボックスの電子メールが既読としてマークされていることを意味します。 **削除**BizTalk で、電子メールを受信した後、メールボックスの電子メールが削除されることを意味します。 後の操作は、ベスト エフォートで実行されます。|

    完了したらのプロパティは、次のようになります。

    ![エンドポイントのプロパティ](../core/media/office365-mail-receive-properties.png)

7. 選択**Ok**変更を保存します。

### <a name="test-your-receive-settings"></a>テストの設定を受け取る

単純な File 送信ポートを使用するから Office 365 の Outlook 電子メール メッセージを受信します。

1. ファイル アダプターを使用して送信ポートを作成します。 送信ポートのプロパティ内で次のように設定します、**先フォルダー**に **C:\Temp\Out\**、設定、および**ファイル名**に **%MessageID%.xml。**.
2. ファイルの送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == <Receive Port Name>`します。
3. 開始、Office 365 Outlook の電子メールは受信場所および File 送信ポートです。
4. 保存先フォルダー (c:\temp\out) にメッセージを探します。

### <a name="promoted-properties-from-receive-pipeline"></a>受信パイプラインから昇格させたプロパティ

既定では、受信パイプラインから、次のプロパティが昇格されます。

|プロパティ名| 昇格させたプロパティ|
|---|---|
| **重要度** | OfficeMail.ReceivedMailImportance |
| **[Subject]** | OfficeMail.ReceivedMailSubject |
| **依頼** | OfficeMail.SenderName |
| **SenderAddress** | OfficeMail.SenderAddress |
| **添付ファイル付き**| OfficeMail.HasAttachments |

> [!NOTE]
> 電子メールの本文の内容のみ、メッセージに渡されます。

## <a name="next-steps"></a>次のステップ
すべてを参照してください、 [Office 365 アダプター](office365-adapters.md)、インストールまたは[機能パック 3](https://aka.ms/bts2016fp3)します。