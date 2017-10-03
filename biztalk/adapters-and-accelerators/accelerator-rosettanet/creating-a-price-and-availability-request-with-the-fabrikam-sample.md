---
title: "Fabrikam サンプルを使用して Price and Availability 要求を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914988661789fdb7750e9c9b650f9887d888694b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a>Fabrikam サンプルを使用して Price and Availability Request の作成
ここでは、LOBWebApplication ツールを使用して、3A2 Price and Availability 要求を作成します。  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a>3A2 Price and Availability 要求を Contoso に送信するには  
  
1.  Internet Explorer で、移動 http://\<*fabrikam_computername*>/>/lobwebapplication/default.aspx です。  
  
2.  **LOBWebApplication**  ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**です。|  
    |**パートナー組織**|型**CONTOSO**です。|  
    |**[PIP Code]**|型**3 a 2**です。|  
    |**[PIP Version]**|型**r02.00.00a など**です。|  
    |**メッセージのカテゴリ**|型**アクション**です。|  
  
3.  メモ帳または別のテキスト エディターを使用してを開く、 **3A2_Request.xml**ファイルで、C:\Program files \microsoft BizTalk\<バージョン > Accelerator for RosettaNet\SDK\LOBApplication\SampleInstancesfolder およびコピーとテキストを貼り付けます、 **Service Content**フィールドで、LOBWebApplication ツールです。  
  
4.  をクリックして**送信**を Contoso 3 a 2 要求を送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したかどうか確認するには  
  
1.  **メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。 次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。 カテゴリ -99 のメッセージは、エラーを表します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。  
  
3.  サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに、入力**localhost**を選択**Windows 認証**、クリックして**接続**.  
  
4.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
5.  **\<テーブル > テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧からです。  
  
6.  **SQL**ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  をクリックして**Execute** SQL ステートメントを実行します。  
  
8.  [クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。 [ServiceContent] フィールドを使用して、応答を確認することもできます。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピュータで通信が成功したかどうか確認するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。  
  
2.  サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに、入力**localhost**を選択**Windows 認証**、クリックして**接続**.  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  **\<テーブル > テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧からです。  
  
5.  **SQL**ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  をクリックして**Execute** SQL ステートメントを実行します。  
  
7.  [クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。 次に受信しているのは、受信確認メッセージを表すカテゴリ 25 のメッセージです。  
  
8.  **SQL**ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. をクリックして**Execute** SQL ステートメントを実行します。  
  
10. [クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。  
  
## <a name="see-also"></a>参照  
 [プライベート プロセス チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)