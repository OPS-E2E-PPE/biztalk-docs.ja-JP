---
title: '手順 1: 0c2 要求の送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05aa5200bd1df6207a962849cd776a03fe71805
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966136"
---
# <a name="step-1-submitting-a-0c2-request"></a>手順 1: a 0 C の送信要求します。
ここでは、0C2 - Asynchronous Test Request の PIP (Partner Interface Process) を使用して、要求を作成および送信します。 この PIP を使用することにより、非同期通信チャネルが 2 つの異なる組織間で正常に動作するようになります。 この PIP は、3A4 - Request Purchase Order PIP などの他の非同期ダブル アクション PIP と同様のパターンに従います。  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a>0C2 - Asynchronous Test Request を送信するには  
  
1.  Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。  
  
2.  **Submit Message**  ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**です。|  
    |**パートナー組織**|型**CONTOSO**です。|  
    |**[Pip Code]**|型**0c2**です。|  
    |**[Pip Version]**|型**R01.02**です。|  
    |**Pip インスタンス ID**|型**0C2_Test**です。 **重要:** するように注意してください、 **PIP**重複したメッセージ ID のエラーを避けるために送信するメッセージごとに一意です。 後で 0C2_Test を実行する場合は、このフィールドを変更する必要があります。|  
    |**メッセージのカテゴリ**|型**アクション**です。|  
  
3.  ある 0C2_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances フォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールドです。  
  
    > [!NOTE]
    >  Submit Message フォームの Service Content フィールドに既存のテキストを削除するには、テキスト、プレス アンド ホールドの先頭にカーソルを置き、 **shift キーを押し**と**Ctrl**ボタン、をクリックして**終了**、クリックして**削除**です。  
  
4.  をクリックして**送信**C 2 を要求を Contoso のコンピューターに送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したかどうか確認するには  
  
-   **メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。 次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。 カテゴリ -99 のメッセージは、エラーを表します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピュータで通信が成功したかどうか確認するには  
  
1.  **[スタート]** ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]** の順にポイントし、 **[SQL Server Management Studio]** をクリックします。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。  
  
    > [!NOTE]
    >  SQL Server エージェントが開始されていない場合を右クリックし、をクリックして**開始**です。  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  \<テーブル\>テキスト ダイアログ ボックスで、 **BTARNDATA**  をクリックし、一覧から**OK**です。  
  
5.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  **クエリ** メニューのをクリックして**Execute** SQL ステートメントを実行します。  
  
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
 [手順 2: 送信 a 0 C 4 クエリします。](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)