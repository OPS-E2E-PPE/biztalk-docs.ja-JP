---
title: "開始側プライベート プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- erros
- LOBs
- messages, message flow
- private processes, initiator
- private processes, message flow
- private processes, errors
ms.assetid: 8444a5c8-445a-4bbd-a793-a16816fcb397
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569d176a15ba5236d5f44d87406d9bbc0a19fca9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="initiator-private-process"></a>開始側プライベート プロセス
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]開始側プライベート プロセス (PrivateInitiator.odx) を使用して、開始側コンピュータの service content を処理します。 これには、次の内容が含まれます。  
  
-   元のメッセージの Service Content の作成、および取引先宛てのメッセージのパブリック プロセスへのルーティング  
  
-   リターン シグナル メッセージの処理、および基幹業務 (LOB) アプリケーションへのルーティング  
  
-   場合は、ダブル アクション PIP、戻り値の応答メッセージを処理し、LOB アプリケーションにルーティングします。  
  
 プライベート プロセスでは、メタデータの設定、および添付ファイルの追加も行います。 プライベート プロセスは、パブリック プロセスに送信メッセージをルーティングします。これによって、RNIF (RosettaNet Implementation Framework) ヘッダーが追加され、メッセージを送信する準備が整います。 プライベート プロセスは、LOB アプリケーション宛ての着信メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにルーティングします。  
  
 このプライベート プロセスは、3A2 および 3A4 の PIP (Partner Interface Process) を使用する購入クエリ/発注プロセスを自動化します。 他のすべての PIP メッセージも処理します。 プライベート プロセスは、個々のビジネス プロセスに合わせてカスタマイズできます。  
  
## <a name="message-flow"></a>メッセージ フロー  
 開始側プライベート プロセスを経由するメッセージ フローは次のとおりです。  
  
1.  開始側プライベート プロセスが、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesFromLOB テーブルから元のメッセージを受信します。 バックエンド LOB アプリケーションは、メッセージをこのテーブルにルーティングします。  
  
2.  プライベート プロセスが元のメッセージの Service Content を準備し、パブリック プロセスに送信します。  
  
3.  開始側プライベート プロセスが待機状態になり、リターン シグナルの受信待ちをします。  
  
4.  パブリック プロセスからリターン シグナルを受信すると、プライベート プロセスがシグナル メッセージを作成し、LOB アプリケーション宛てのシグナルを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルに送信します。  
  
5.  プライベート プロセスがシグナル メッセージを MessagesToLOB テーブルに保存したことを LOB アプリケーションに通知します。  
  
6.  RNIF バージョンが 1.1 の場合、プライベート プロセスは受信確認のシグナル メッセージを待ちます。 シグナルを受信すると、シグナル メッセージを作成し、LOB アプリケーション宛てのシグナルを MessagesToLOB テーブルに送信します。  
  
7.  元のメッセージがシングル アクション メッセージの場合、プライベート プロセスはシグナル メッセージを LOB アプリケーションに返すと完了します。 元のメッセージがダブル アクション メッセージの場合、プライベート プロセスは応答メッセージを受信待ちします。  
  
8.  プライベート プロセスはパブリック プロセスから応答メッセージを受信すると、LOB アプリケーションの形式で応答メッセージを作成します。 これには、LOB メッセージ テンプレートの取得、XML サービス コンテンツのシリアル化、および LOB メッセージへの XML メッセージ部の読み込みが含まれます。  
  
9. プライベート プロセスが [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにメッセージをルーティングします。  
  
10. 応答メッセージに添付ファイルがある場合、プライベート プロセスは AttachmentHelper ツールを呼び出して添付ファイルを処理します。  
  
11. プライベート プロセスが応答メッセージを MessagesToLOB テーブルに保存したことを LOB アプリケーションに通知し、終了します。  
  
## <a name="handling-of-incorrect-messages"></a>誤ったメッセージの処理  
 開始側プライベート プロセスが LOB アプリケーションから誤ったメッセージを受信した場合は、LOB に例外メッセージを送り返します。 ただし、プライベート プロセスは、誤ったメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理コンソールに渡しません。 したがって、誤ったメッセージを BizTalk 管理コンソールで表示することはできません。 例外メッセージを使用して、どれが誤ったメッセージなのかを判断してから、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA データベースの MessagesFromLOB テーブルで該当するメッセージを確認する必要があります。 ただし、このメッセージは、プライベート プロセスが使用したメッセージと異なっている可能性があります。これは、保存されているプロセスとメッセージ処理に使用されたアダプターが、メッセージを編集するためです。 この編集によって、ルート要素と名前空間がメッセージに追加されます。 保存されているプロセスとアダプターは、複数のレコードを返す場合があります。  
  
## <a name="see-also"></a>参照  
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateInitiator サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)