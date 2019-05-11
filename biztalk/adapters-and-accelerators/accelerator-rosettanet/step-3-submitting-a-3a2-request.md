---
title: 手順 3:3 a 2 要求の送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4feb98c9258c870fc43eb9cf5b9583e932933092
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281044"
---
# <a name="step-3-submitting-a-3a2-request"></a>手順 3:3 a 2 要求を送信します。
この手順では、準備し、3 a 2 - Request Price and Availability をプロセス PIP (Partner Interface) を使用して、要求を送信します。 この PIP により、購入者の組織が、特定の製品価格と使用可能なユニットの数などに関する情報を取得します。 購入者には、業者から製品を購入するかどうかを決定するビジネス ルールに基づいてその情報を処理し、できます。  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a>3 a 2 - Request Price and Availability を送信するには  
  
1.  Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。  
  
2.  **Submit Message**ページで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**します。|  
    |**取引先組織**|型**Contoso**します。|  
    |**[Pip Code]**|型**3 a 2**します。 **重要:** 重複するメッセージ ID のエラーを回避する必要があること確認する、 **Pip**は送信した各メッセージに一意です。 今後 3 a 2 テストを実行する場合は、このフィールドを変更する必要があります。|  
    |**[Pip Version]**|型**r02.00.00a など**します。|  
    |**Pip インスタンス ID**|型**3A2_Test**します。|  
    |**メッセージのカテゴリ**|型**アクション**します。|  
  
3.  メモ帳または別のテキスト エディターを使用して、内の 3A2_Request.xml ファイルを開き、 *\<ドライブ\>*: \プログラムの files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーに、コピーして貼り付け、内容、 **Service Content**フィールドにLOBWebApplication します。  
  
4.  クリックして**送信**Contoso のコンピューターに 3 a 2 要求を送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したことを確認するには  
  
-   **メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。 Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。 カテゴリ-99 のメッセージでは、エラーを示します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピューターの通信が成功したことを確認するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。  
  
3.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4.  \<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧から。  
  
5.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  クリックして**Execute** SQL ステートメントを実行します。  
  
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
 [手順 4:3A4 要求の送信](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)