---
title: '手順 8: BTARN データベース内のメッセージの表示 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 018bd2515dc2c363474c8058a861fd763cb73352
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855445"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a>手順 8: BTARN データベース内のメッセージの表示
ここでは、ループバック シナリオが正しく動作していることを確認するために、SQL クエリ アナライザーを使用して、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] データベースに格納されている基幹業務 (LOB) メッセージを表示します。  
  
 LOB アプリケーション ユーティリティが LOB メッセージを生成し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信した後、開始側 (ホーム) と応答側 (パートナー) で次のイベントが発生します。  
  
 開始側ワークフロー  
  
-   SubmitRNIF が、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA データベースの MessagesFromLOB テーブルに LOB メッセージを送信します。  
  
-   SQL アダプター受信場所がメッセージを取得し、MessageBox データベースに配信します。 SQL アダプターは `GetMessagesFromLOB` ストアド プロシージャを実行して、一度に 1 つのメッセージを取得します。  
  
-   プライベート開始側が MessageBox データベースからメッセージを取得し、追加で昇格されたコンテキスト プロパティを付けて MessageBox データベースに再度ドロップします。  
  
-   パブリック開始側がサブスクリプション フィルターに基づいて、MessageBox データベースからメッセージを取得します。  
  
-   HTTP 送信ポートがサブスクリプションに基づいて、RNIFSend パイプラインでメッセージを取得します。 HTTP 送信ポートは、否認不可用の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive データベースの MessageStorageOut テーブルにメッセージを格納した後、メッセージを RNIFSend.aspx ページに送信します。  
  
-   RNIFSend.aspx ページは、メッセージの最終送信先 (取引先組織の URL) を含むクエリ文字列変数付きの MIME でエンコードされたメッセージを受け取ります。  
  
 応答側ワークフロー  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が RNIF メッセージを RNIFReceive.aspx ページに送信します。RNIFReceive.aspx ページでは、MIME でデコードされたラッパーが削除されます。 メッセージは、同期メッセージまたは非同期メッセージのいずれかとして識別された後、同期または非同期の受信場所 (RNIF_Sync_Receive または RNIF_Async_Receive) に転送されます。  
  
-   まず、HTTP 受信場所が、ワイヤ形式のメッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive データベースの否認不可用 MessageStorageIn テーブルに格納します。 次に HTTP 受信場所は、デコードおよび暗号化の解除を実行して (RNIF 2.0 の場合)、その署名を検証します。次に XML メッセージ部を逆アセンブルし、署名に基づいて承認してから、昇格された正しいプロパティを付けて MessageBox データベースにドロップします。  
  
-   パブリック応答側が、サブスクリプションに基づいてメッセージ部を取得し、正しい RNIF 規格に基づいてメッセージを検証および処理します。 Service Content 部が、メッセージに正しいコンテキスト プロパティを付けて MessageBox データベースにドロップします。  
  
-   SQL 送信ポートがサブスクリプション フィルターに基づいてメッセージを取得します。 次に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA データベースの MessagesToLOB テーブルにメッセージを格納します。  
  
> [!NOTE]
>  応答側パブリック応答側は受信確認または例外シグナル、発信側に戻れるの生成を担当します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MessagesFromLOB テーブルには、シグナル メッセージは保存されません。 これは、LOB アプリケーションがシグナル メッセージを生成しないためです。 アクション メッセージはプライベート応答側を経由し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって MessagesToLOB テーブルに格納されます。  
  
> [!NOTE]
>  ダブル アクション Pip の応答側の LOB は応答メッセージを生成します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 開始側プロセスと同じプロセスを経由する MessagesFromLOB テーブルにドロップします。 この場合、開始側のパブリック開始側プロセスが、応答メッセージの受信確認または例外シグナルを送信します。  
  
### <a name="to-view-messages-in-the-btarn-databases"></a>BTARN データベース内のメッセージを表示するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server\<バージョン\>**、クリックして**SQL ServerManagement Studio**です。  
  
2.  [サーバー] ダイアログ ボックスへの接続でクリックして**接続**です。  
  
    > [!NOTE]
    >  オブジェクト エクスプローラー ペインで、SQL Server エージェントが開始されていることを確認します。 いない場合を右クリックし**SQL Server エージェント**、 をクリック**開始**です。  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  空のクエリ ウィンドウに以下を入力します。  
  
    ```  
    use BTARNArchive  
    SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
    SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
    use BTARNData  
    SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
    ```  
  
5.  Microsoft SQL Server Management Studio でクリックして**Execute**です。  
  
 MessagesFromLOB テーブル内のアクション メッセージが表示されます。数分後 (この時間はシステム構成によって異なります) にクエリを再度実行すると、MessageCategory 値が AsyncAckSignal (25) および AsyncAction (10) である 2 つのメッセージが MessagesToLOB テーブルに生成されて表示されます。  
  
## <a name="see-also"></a>参照  
 [ループバック](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)   
 [ループバックのチュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
