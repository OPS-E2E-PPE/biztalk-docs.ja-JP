---
title: 手順 4:3A4 要求の送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6589a46665edf6e446483b673fd4228dd471bbd3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280923"
---
# <a name="step-4-submitting-a-3a4-request"></a>手順 4:3A4 要求の送信
この手順では、準備し、3a4-request Purchase Order を要求をプロセス PIP (Partner Interface) を使用して、要求を送信します。 この PIP は、業者に注文要求を送信する購入者組織を使用できます。 一般に、3A4 - 製品の可用性を 3 a 2 - Request Price and Availability PIP を使用してクエリを実行した後の要求の発注書を要求します。 3A4 PIP は、受信確認を送信する非同期の PIP です。  
  
 ![&#60;変更なし&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a>3A4 の発注書の要求を送信するには  
  
1.  Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。  
  
2.  **Submit Message**ページで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**ホーム組織**|型**FABRIKAM**します。|  
    |**取引先組織**|型**Contoso**します。|  
    |**[Pip Code]**|型**3A4**します。|  
    |**[Pip Version]**|型**V02.02.00**します。|  
    |**Pip インスタンス ID**|型**3A4_Test**します。 **重要:** 重複するメッセージ ID のエラーを回避する必要があること確認する、 **Pip インスタンス ID**は送信した各メッセージに一意です。 今後 3a4_test を実行する場合はこのフィールドを変更する必要があります。|  
    |**メッセージのカテゴリ**|型**アクション**します。|  
  
3.  メモ帳または別のテキスト エディターを使用してある 3A4_Request.xml ファイルを開き、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances のフォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールド。  
  
4.  クリックして**送信**3A4 要求を Contoso のコンピューターを送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したことを確認するには  
  
-   **メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。 Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。 カテゴリ-99 のメッセージでは、エラーを示します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピューターの通信が成功したことを確認するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。  
  
3.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4.  \<テーブル\>テキスト] ダイアログ ボックス、[ **BTARNDATA**一覧から。  
  
5.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  クリックして**Execute** SQL ステートメントを実行します。  
  
7.  結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。  
  
    > [!NOTE]
    >  最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。 Acknowledegment メッセージを表すカテゴリ 25 のメッセージを受信する必要があります。  
  
8.  SQL ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. クリックして**Execute** SQL ステートメントを実行します。  
  
10. クエリ ウィンドウ内で、**結果**ウィンドウで、1 つの送信メッセージを表示することを確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。  
  
## <a name="see-also"></a>参照  
 [ダブル アクション チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)