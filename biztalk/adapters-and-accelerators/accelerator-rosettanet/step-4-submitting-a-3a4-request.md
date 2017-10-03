---
title: "手順 4: 3A4 要求の送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2436d33033163b32c4ead0fdab807b7db0b0158f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-submitting-a-3a4-request"></a>手順 4: 3A4 要求の送信
ここでは、3A4 - Request Purchase Order の PIP (Partner Interface Process) を使用して、要求を作成および送信します。 この PIP を使用することにより、購入者組織が発注を業者に送信できるようになります。 通常は、3A2 - Request Price and Availability PIP を使用して注文可能な製品を照会してから、3A4 - Request Purchase Order を要求します。 3A4 PIP は、受信確認を送信する非同期の PIP です。  
  
 ![(& m); 60変更なし &#62;。] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a>3A4 - Request Purchase Order を送信するには  
  
1.  Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。  
  
2.  **Submit Message**  ページで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**ホーム組織**|型**FABRIKAM**です。|  
    |**パートナー組織**|型**Contoso**です。|  
    |**[Pip Code]**|型**3A4**です。|  
    |**[Pip Version]**|型**V02.02.00**です。|  
    |**Pip インスタンス ID**|型**3A4_Test**です。 **重要:**重複したメッセージ ID のエラーを避けるためには、する必要があることを確認、 **Pip インスタンス ID**を送信するメッセージごとに一意です。 後で 3A4_Test を実行する場合は、このフィールドを変更する必要があります。|  
    |**メッセージのカテゴリ**|型**アクション**です。|  
  
3.  ある 3A4_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 \<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances フォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールドです。  
  
4.  をクリックして**送信**を Contoso のコンピューター 3A4 要求を送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したかどうか確認するには  
  
-   **メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。 次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。 カテゴリ -99 のメッセージは、エラーを表します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピュータで通信が成功したかどうか確認するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  \<テーブル > のテキスト ダイアログ ボックスで、 **BTARNDATA**一覧からです。  
  
5.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  をクリックして**Execute** SQL ステートメントを実行します。  
  
7.  [クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。 受信 acknowledegment メッセージを表すカテゴリ 25 のメッセージを表示する必要があります。  
  
8.  SQL ウィンドウに、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. をクリックして**Execute** SQL ステートメントを実行します。  
  
10. クエリ ウィンドウ内で、**結果** ウィンドウで、1 つの送信メッセージが表示されることを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。  
  
## <a name="see-also"></a>参照  
 [ダブル アクション チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md)   
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)