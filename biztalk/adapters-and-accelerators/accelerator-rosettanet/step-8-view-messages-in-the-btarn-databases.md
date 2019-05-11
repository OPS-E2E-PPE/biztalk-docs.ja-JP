---
title: 手順 8:BTARN データベース内のメッセージの表示 |Microsoft Docs
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
ms.openlocfilehash: 94f9b676c2f8ea8c212a4ded6f50ee9037cad6ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280546"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a>手順 8:BTARN データベース内のメッセージの表示
この手順で、Microsoft® に格納されている基幹業務 (LOB) メッセージを表示する SQL クエリ アナライザーを使用する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ループバック シナリオが正しく動作していることを確認するデータベース。  
  
 LOB アプリケーション後ユーティリティが LOB メッセージを生成しに送信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、(ホーム) のイニシエーターおよびレスポンダー (パートナー) に対して次のイベントが発生します。  
  
 開始側ワークフロー  
  
- SubmitRNIF の MessagesFromLOB テーブルに LOB メッセージの送信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。  
  
- SQL アダプターでは、受信場所がメッセージを取得し、メッセージ ボックス データベースに配信します。 SQL アダプターは、時間の実行中に 1 つのメッセージを取得、`GetMessagesFromLOB`ストアド プロシージャ。  
  
- プライベート開始側はメッセージ ボックス データベースからメッセージを取得し、昇格させた追加のコンテキスト プロパティをメッセージ ボックス データベースにもう一度削除します。  
  
- パブリック開始側は、サブスクリプション フィルターに基づいて、メッセージ ボックス データベースからメッセージを取得します。  
  
- HTTP では、サブスクリプションに基づいて、RNIFSend パイプラインでポートによって取得、メッセージを送信します。 MessageStorageOut テーブルにメッセージを保存、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]非否認のアーカイブ データベースを RNIFSend.aspx ページにメッセージを送信するとします。  
  
- RNIFSend.aspx ページは、メッセージ (パートナー組織の URL) の最終的な送信先を含むクエリ文字列変数で MIME でエンコードされたメッセージを受信します。  
  
  応答側ワークフロー  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MIME でデコードされたラッパーを除去する RNIFReceive.aspx ページに RNIF メッセージを送信します。 同期または非同期のどちらかとして識別されるメッセージを転送し、同期または非同期のいずれかの受信場所 (RNIF_Sync_Receive または RNIF_Async_Receive)。  
  
- HTTP の否認不可用 MessageStorageIn テーブル内の場所の最初の保存、メッセージのワイヤ形式を受信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]アーカイブ データベース。 HTTP 受信場所をデコードし、(RNIF 2.0) の復号化、その署名を検証、XML メッセージの部分を逆アセンブル、承認、シグネチャに基づいており、昇格された正しいプロパティを付けて MessageBox データベースにドロップします  
  
- パブリック応答側は、ベースのサブスクリプションでは、メッセージ部分を取得、それを検証してから、正しい RNIF 規格に基づいてメッセージを処理します。 Service content 部では、正しいコンテキスト プロパティをメッセージ ボックス データベースにメッセージを削除します。  
  
- SQL 送信ポートは、サブスクリプション フィルターに基づいてメッセージ。 MessagesToLOB テーブルにメッセージを保存し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。  
  
> [!NOTE]
>  応答側では、パブリック応答側は受信確認または例外シグナルを発信側に生成する責任を負います。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MessagesFromLOB テーブルには、シグナル メッセージは保存されません。 これは、LOB アプリケーションがシグナル メッセージを生成しないためです。 プライベート応答側アクションのメッセージが今後と[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]MessagesToLOB テーブルに保存します。  
> 
> [!NOTE]
>  ダブル アクション Pip の応答側に LOB が応答メッセージを生成する責任を負います。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 開始側プロセスと同じプロセスを経由する MessagesFromLOB テーブルにドロップします。 ここで、開始側パブリック開始側プロセスでは、戻る応答メッセージの受信確認または例外シグナルのために送信します。  
  
### <a name="to-view-messages-in-the-btarn-databases"></a>BTARN データベース内のメッセージを表示するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server\<バージョン\>**、順にクリックします**SQL ServerManagement Studio**します。  
  
2. [サーバー] ダイアログ ボックスへの接続、クリックして**Connect**します。  
  
   > [!NOTE]
   >  オブジェクト エクスプ ローラー ウィンドウで、SQL Server エージェントが開始されていることを確認します。 ない場合を右クリックして**SQL Server エージェント**、 をクリック**開始**します。  
  
3. Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4. 空のクエリ ウィンドウで、次のように入力します。  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. Microsoft SQL Server Management Studio で次のようにクリックします。 **Execute**します。  
  
   MessagesFromLOB テーブル内のアクション メッセージは表示され (時刻は、システム構成によって異なる場合があります)、数分後にもう一度クエリを実行する場合は、MessageCategory 値を持つ MessagesToLOB テーブルで生成された 2 つのメッセージが表示されます。AsyncAckSignal (25) および AsyncAction (10)。  
  
## <a name="see-also"></a>参照  
 [Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)   
 [ループバックのチュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
