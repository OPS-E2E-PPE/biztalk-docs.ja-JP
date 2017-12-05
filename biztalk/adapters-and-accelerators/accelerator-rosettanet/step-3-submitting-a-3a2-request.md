---
title: "手順 3: 3 a 2 要求の送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312e5980636d211f1e023331826e016eb141eb4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-submitting-a-3a2-request"></a>手順 3: 3 a 2 要求の送信
ここでは、3A2 - Request Price and Availability の PIP (Partner Interface Process) を使用して、要求の準備と送信を行います。 購入者組織はこの PIP を使用して、特定の製品について価格や入手可能な数などの情報を取得できます。 次に、購入者は、ビジネス ルールに基づいてその情報を処理し、業者から製品を購入するかどうかを決定します。  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a>3A2 - Request Price and Availability を送信するには  
  
1.  Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。  
  
2.  **Submit Message**  ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**です。|  
    |**パートナー組織**|型**Contoso**です。|  
    |**[Pip Code]**|型**3 a 2**です。 **重要:**重複したメッセージ ID のエラーを避けるためには、する必要があることを確認、 **Pip**を送信するメッセージごとに一意です。 後で 3A2_Test を実行する場合は、このフィールドを変更する必要があります。|  
    |**[Pip Version]**|型**r02.00.00a など**です。|  
    |**Pip インスタンス ID**|型**3A2_Test**です。|  
    |**メッセージのカテゴリ**|型**アクション**です。|  
  
3.  メモ帳または別のテキスト エディターを使用して、内の 3A2_Request.xml ファイルを開き、 *\<ドライブ\>*: \プログラムの \program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーをコピーして貼り付け、内容、 **Service Content**フィールドLOBWebApplication です。  
  
4.  をクリックして**送信**Contoso のコンピューターに 3 a 2 要求を送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したかどうか確認するには  
  
-   **メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。 次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。 カテゴリ -99 のメッセージは、エラーを表します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピュータで通信が成功したかどうか確認するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  \<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧からです。  
  
5.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  をクリックして**Execute** SQL ステートメントを実行します。  
  
7.  [クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。 次に受信しているのは、受信確認メッセージを表すカテゴリ 25 のメッセージです。  
  
8.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. をクリックして**Execute** SQL ステートメントを実行します。  
  
10. [クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。  
  
## <a name="see-also"></a>参照  
 [手順 4: 3A4 要求の送信](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)