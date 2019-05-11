---
title: 手順 2:クエリの送信、0 C 4 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5ea963049d8d7a53c0098c1a53ae54784e0653
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281292"
---
# <a name="step-2-submitting-a-0c4-query"></a>手順 2:4 のクエリの送信
この手順では、準備し、0 c 4 - 0c4-synchronous Test Query の PIP Partner Interface Process () を使用して、要求を送信します。 RosettaNet では、2 つの異なる組織間で同期通信チャネルが正常かどうかを確認するには、この PIP を定義します。 この PIP は同期通信パターンでは、ため[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信確認を送信しません。 この PIP は Technical Product Information PIP 2a9 と - などの他の同期のダブル アクション Pip と同様のパターンに従います。  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a>0 C 4 - 0c4-synchronous Test Query を送信するには  
  
1.  Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。  
  
2.  **Submit Message**ページで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**します。|  
    |**取引先組織**|型**CONTOSO**します。|  
    |**[Pip Code]**|型**0 C 4**します。|  
    |**[Pip Version]**|型**R01.02**します。|  
    |**Pip インスタンス ID**|型**0C4_Test**します。 **重要:** 重複するメッセージ ID のエラーを回避する必要があること確認する、 **PIP**は送信した各メッセージに一意です。 場合は、0 C 4 は、後でテストを実行すると、このフィールドを変更する必要があります。|  
    |**メッセージのカテゴリ**|型**アクション**します。|  
  
3.  内の 0C4_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk 2009 Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーでは、コピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールド。  
  
4.  クリックして**送信**C 4 が Contoso のコンピューターにクエリを送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したことを確認するには  
  
-   **メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要があります。 カテゴリ-99 のメッセージでは、エラーを示します。 イベント ビューアーを使用すると、実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピューターの通信が成功したことを確認するには  
  
1.  **[スタート]** ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]** の順にポイントし、 **[SQL Server Management Studio]** をクリックします。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。  
  
    > [!NOTE]
    >  SQL Server エージェントが開始されていない場合を右クリックし、順にクリックします**開始**します。  
  
3.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4.  \<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧から。  
  
5.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  クリックして**Execute** SQL ステートメントを実行します。  
  
7.  結果ウィンドウで、クエリ ウィンドウで 1 つの受信メッセージが表示されることを確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターの送信元の要求を表すカテゴリ 10 のメッセージが表示されます。  
  
8.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. クリックして**Execute** SQL ステートメントを実行します。  
  
10. 結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。  
  
    > [!NOTE]
    >  PIP に Contoso の応答を表すカテゴリ 50 のメッセージを表示する必要があります 0c4 クエリの送信を Fabrikam。 ダブル アクション同期シナリオでは、応答側コンピューターは、最初のクエリ メッセージに対する応答の開始側コンピューターに、受信確認を送信しません。 応答メッセージが受信確認となります。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:3 a 2 要求を送信します。](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)