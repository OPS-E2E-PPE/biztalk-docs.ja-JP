---
title: Fabrikam サンプルを Price and Availability 要求を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ace1e92767b5eee040cd3c0e11cd747846f5ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284672"
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a>Fabrikam サンプルを使用して Price and Availability Request の作成
この手順では、LOBWebApplication ツールを使用して 3 a 2 Price and Availability 要求を作成します。  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a>3 a 2 Price and Availability 要求を Contoso に送信するには  
  
1.  Internet Explorer で、移動 http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx します。  
  
2.  **LOBWebApplication**ページで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホーム組織**|型**FABRIKAM**します。|  
    |**取引先組織**|型**CONTOSO**します。|  
    |**[PIP Code]**|型**3 a 2**します。|  
    |**[PIP Version]**|型**r02.00.00a など**します。|  
    |**メッセージのカテゴリ**|型**アクション**します。|  
  
3.  メモ帳または別のテキスト エディターを使用してを開く、 **3A2_Request.xml**ファイルは C:\Program files \microsoft biztalk\<バージョン\>RosettaNet\SDK\LOBApplication\SampleInstancesfolder のアクセラレータテキストを貼り付けるし、コピー、 **Service Content**フィールドで、LOBWebApplication ツール。  
  
4.  クリックして**送信**を Contoso 3 a 2 要求を送信します。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで通信が成功したことを確認するには  
  
1.  **メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。  
  
    > [!NOTE]
    >  Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。 Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。 カテゴリ-99 のメッセージでは、エラーを示します。 使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。  
  
2.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
3.  サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに「 **localhost**を選択します**Windows 認証** をクリックし、 **Connect**.  
  
4.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
5.  **\<テーブル\>テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧から。  
  
6.  **SQL**ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  クリックして**Execute** SQL ステートメントを実行します。  
  
8.  結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。 応答の検証を servicecontent フィールドを使用することもできます。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Contoso のコンピューターの通信が成功したことを確認するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2.  サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに「 **localhost**を選択します**Windows 認証** をクリックし、 **Connect**.  
  
3.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4.  **\<テーブル\>テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧から。  
  
5.  **SQL**ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  クリックして**Execute** SQL ステートメントを実行します。  
  
7.  結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。  
  
    > [!NOTE]
    >  最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。 受信確認のメッセージを表すカテゴリ 25 のメッセージを受信する必要があります。  
  
8.  **SQL**ウィンドウで、次の SQL ステートメントを入力します。  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. クリックして**Execute** SQL ステートメントを実行します。  
  
10. 結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。  
  
    > [!NOTE]
    >  Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。 Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。  
  
## <a name="see-also"></a>参照  
 [プライベート プロセス チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)