---
title: 開始側プライベート プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0bcf79ba696068e1dfa52b3d2d44542343060b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283474"
---
# <a name="initiator-private-process"></a>開始側プライベート プロセス
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]開始側プライベート プロセス (PrivateInitiator.odx) を使用して、開始側コンピュータでのサービス内容を処理します。 これには、次の内容が含まれます。  
  
- 元のメッセージの service content を作成して、取引先パートナーへのルートで、パブリック プロセスへのメッセージのルーティング  
  
- リターン シグナル メッセージを処理し、基幹業務 (LOB) アプリケーションへのルーティング  
  
- 場合はダブル アクション PIP、戻り値の応答メッセージを処理し、LOB アプリケーションへのルーティングします。  
  
  プライベート プロセスは、メタデータを設定し、すべての添付ファイルを追加します。 プライベート プロセスは、RosettaNet Implementation Framework (RNIF) ヘッダーを追加して、メッセージ転送の準備が整います、パブリック プロセスに送信メッセージをルーティングします。 プライベート プロセスは、LOB アプリケーション宛ての着信メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにルーティングします。  
  
  このプライベート プロセスは、3 a 2 および 3A4 の Partner Interface Process (Pip) を使用する購入クエリ/発注注文プロセスを自動化します。 他のすべての PIP メッセージも処理します。 特定のビジネス プロセスのプライベート プロセスをカスタマイズできます。  
  
## <a name="message-flow"></a>メッセージ フロー  
 開始側プライベート プロセスを経由するメッセージ フローは次のとおりです。  
  
1. 開始側プライベート プロセスが MessagesFromLOB テーブルから、元のメッセージを受信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。 バックエンドの LOB アプリケーションは、このテーブルにメッセージをルーティングします。  
  
2. プライベート プロセスでは、発信されたメッセージの service content を準備し、パブリック プロセスに送信します。  
  
3. 開始側プライベート プロセスは、リターン シグナルの待機、待機状態を入力します。  
  
4. パブリック プロセスからリターン シグナルを受信すると、プライベート プロセスがシグナル メッセージを作成し、シグナルを MessagesToLOB テーブルに送信します、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベースで、LOB アプリケーションへのルートでします。  
  
5. プライベート プロセスは、シグナル メッセージを MessagesToLOB テーブルに配置が LOB アプリケーションに通知を送信します。  
  
6. RNIF のバージョンが 1.1 の場合は、プライベート プロセスへの同意の確認のシグナル メッセージを待ちます。 シグナルを受信した場合、シグナル メッセージを作成し、シグナルを MessagesToLOB テーブルに LOB アプリケーションへのルートに送信します。  
  
7. 元のメッセージがシングル アクション メッセージの場合は、シグナル メッセージを LOB アプリケーションに戻った後、プライベート プロセスが完了しました。 元のメッセージがダブル アクション メッセージの場合は、プライベート プロセスは、応答メッセージをリッスンします。  
  
8. プライベート プロセスは、パブリック プロセスから応答メッセージを受信した場合は、LOB アプリケーションの形式で応答メッセージを構築します。 これには、LOB メッセージ テンプレートの取得、XML サービス コンテンツのシリアル化、および LOB メッセージへの XML メッセージ部の読み込みが含まれます。  
  
9. プライベート プロセスは、メッセージを MessagesToLOB テーブルにルーティング、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。  
  
10. 応答メッセージに添付ファイルがある場合は、プライベート プロセスは AttachmentHelper ツールで、添付ファイルを処理するを呼び出します。  
  
11. プライベート プロセスは、応答メッセージを MessagesToLOB テーブルに配置しが完了し、LOB アプリケーションに通知を送信します。  
  
## <a name="handling-of-incorrect-messages"></a>誤ったメッセージの処理  
 開始側プライベート プロセスは LOB アプリケーションから正しくないメッセージを受信、プライベート プロセスは、LOB に例外メッセージを送信します。 ただし、プライベート プロセスには、正しくないメッセージで通知されません、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理コンソール。 したがって、BizTalk 管理コンソールで、正しくないメッセージを表示することはできません。 正しくないメッセージが正しくなかったことを確認するメッセージへのアクセス、例外メッセージを使用しての MessagesFromLOB テーブルに正しくないメッセージにアクセスし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。 ただし、このメッセージができません消費されると、プライベート プロセス メッセージと同じ編集、保存されているプロセスとメッセージの処理に使用するアダプター。 メッセージにルート要素と名前空間を追加するとします。 保存されているプロセスとアダプターは、複数のレコードを返す可能性があります。  
  
## <a name="see-also"></a>参照  
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateInitiator サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)