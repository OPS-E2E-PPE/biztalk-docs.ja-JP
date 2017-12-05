---
title: "手順 2: 0c4 を送信するクエリを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c621b6891b816f72603202bd6f2214882eb4b5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-submitting-a-0c4-query"></a>手順 2: 送信 a 0 C 4 クエリします。
ここでは、0C4 - Synchronous Test Query の PIP (Partner Interface Process) を使用して、要求を作成および送信します。 RosettaNet では、この PIP を定義することにより、2 つの異なる組織間で同期通信チャネルが正しく動作するようにしています。 この PIP は同期通信パターンを持っているため、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] は受信確認を送信しません。 この PIP は、2A9 - Query Technical Product Information PIP などの他の同期ダブル アクション PIP と同様のパターンに従います。  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a>0C4 - Synchronous Test Query を送信するには  
  
1.  Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。  
  
2.  **Submit Message**  ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**です。|  
    |**パートナー組織**|型**CONTOSO**です。|  
    |**[Pip Code]**|型**0 C 4**です。|  
    |**[Pip Version]**|型**R01.02**です。|  
    |**Pip インスタンス ID**|型**0C4_Test**です。 **重要:**重複したメッセージ ID のエラーを避けるためには、する必要があることを確認、 **PIP**を送信するメッセージごとに一意です。 後で 0C4 を実行する場合は、このフィールドを変更する必要があります。|  
    |**メッセージのカテゴリ**|型**アクション**です。|  
  
3.  内の 0C4_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk 2009 Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールドです。  
  
4.  をクリックして**送信**C 4 のクエリを Contoso のコンピューターに送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したかどうか確認するには  
  
-   **メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。  
  
    > [!NOTE]
    >  受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。 カテゴリ -99 のメッセージは、エラーを表します。 実際のエラー メッセージを特定するには、イベント ビューアーを使用します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピュータで通信が成功したかどうか確認するには  
  
1.  **[スタート]**ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]**の順にポイントし、 **[SQL Server Management Studio]**をクリックします。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。  
  
    > [!NOTE]
    >  SQL Server エージェントが開始されていない場合を右クリックし、をクリックして**開始**です。  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  \<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧からです。  
  
5.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  をクリックして**Execute** SQL ステートメントを実行します。  
  
7.  [クエリ] ウィンドウの結果ペインで、1 つの着信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージが表示されます。  
  
8.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. をクリックして**Execute** SQL ステートメントを実行します。  
  
10. [クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターが送信した PIP 0C4 クエリに対する Contoso の応答を表すカテゴリ 50 のメッセージが表示されます。 ダブル アクション同期シナリオでは、応答側コンピューターは開始側コンピューターに対して、最初のクエリ メッセージに応える受信確認を送信しません。 応答メッセージが受信確認となります。  
  
## <a name="see-also"></a>参照  
 [手順 3: 3 a 2 要求の送信](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)