---
title: 手順 1:0c2 要求の送信 |Microsoft Docs
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
ms.openlocfilehash: 8bc9102198305d6f9ea92ca4d1462d1839c4f5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281421"
---
# <a name="step-1-submitting-a-0c2-request"></a>手順 1:要求の送信
この手順では、準備し、0 c 2 - 0c2-asynchronous Test Request の PIP Partner Interface Process () を使用して、要求を送信します。 この PIP により、非同期通信チャネルが 2 つの異なる組織間で正常に動作するようになります。 この PIP は Purchase Order PIP 3A4 - などの他の非同期のダブル アクション Pip と同様のパターンに従います。  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a>0 の C 2 - 0c2-asynchronous Test Request を送信するには  
  
1.  Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。  
  
2.  **Submit Message**ページで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**します。|  
    |**取引先組織**|型**CONTOSO**します。|  
    |**[Pip Code]**|型**0c2**します。|  
    |**[Pip Version]**|型**R01.02**します。|  
    |**Pip インスタンス ID**|型**0C2_Test**します。 **重要:** 必ず必要がありますが、 **PIP**は重複するメッセージ ID のエラーを回避するために送信する各メッセージに一意です。 0 の C 2 は、後でテストを実行する場合は、このフィールドを変更する必要があります。|  
    |**メッセージのカテゴリ**|型**アクション**します。|  
  
3.  内の 0C2_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances のフォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールド。  
  
    > [!NOTE]
    >  Submit Message フォームの Service Content フィールドで、既存のテキストを削除するには、テキスト、プレス アンド ホールドの先頭にカーソルを置き、 **Shift**と**Ctrl**ボタン、をクリックして**終了**、 をクリックし、**削除**します。  
  
4.  クリックして**送信**C 2 が Contoso のコンピューターに要求を送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したことを確認するには  
  
-   **メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。 Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。 カテゴリ-99 のメッセージでは、エラーを示します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピューターの通信が成功したことを確認するには  
  
1.  **[スタート]** ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]** の順にポイントし、 **[SQL Server Management Studio]** をクリックします。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。  
  
    > [!NOTE]
    >  SQL Server エージェントが開始されていない場合を右クリックし、順にクリックします**開始**します。  
  
3.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4.  \<テーブル\>テキスト ダイアログ ボックス、 **BTARNDATA**  をクリックし、一覧から**OK**。  
  
5.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  **クエリ** メニューのをクリックして**Execute** SQL ステートメントを実行します。  
  
7.  結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。  
  
    > [!NOTE]
    >  最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。 受信確認のメッセージを表すカテゴリ 25 のメッセージを受信する必要があります。  
  
8.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. クリックして**Execute** SQL ステートメントを実行します。  
  
10. 結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。  
  
## <a name="see-also"></a>参照  
 [手順 2:4 のクエリの送信](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)