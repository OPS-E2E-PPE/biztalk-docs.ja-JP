---
title: 応答側プライベート プロセス |Microsoft Docs
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
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 045559ad13492055e0e63a0cb19c4e7e780d5252
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989619"
---
# <a name="responder-private-process"></a>応答側プライベート プロセス
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]の service content を応答側コンピューターの処理に応答側プライベート プロセス (PrivateResponder.odx) を使用します。 これには、次の内容が含まれます。  
  
- 基幹業務 (LOB) アプリケーションへの着信メッセージのルーティング  
  
- 応答メッセージの Service Content の作成、および応答側コンピューター宛てのメッセージのパブリック プロセスへのルーティング  
  
  プライベート プロセスにより、メタデータの設定と、応答メッセージへの添付ファイルの追加も行われます。 プライベート プロセスでは、応答側パブリック プロセスに送信メッセージをルーティングします。これによって、RNIF (RosettaNet Implementation Framework) ヘッダーが追加され、メッセージを送信する準備が整います。 プライベート プロセスは、LOB アプリケーション宛ての着信メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにルーティングします。  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、個々のビジネス プロセスに合わせてカスタマイズ可能な応答側プライベート プロセスのサンプルが 2 つ含まれています。 1 つ目のサンプルは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によってインストールされた応答側プライベート プロセスのコードを含む PrivateResponder プロセスのサンプルです。 詳細については、[PrivateResponder サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)を参照してください。  
  
  2 つ目のサンプルは、3A2 および 3A4 の PIP (Partner Interface Process) を使用する発注照会/発注プロセスを自動化する PIP3A4PrivateResponder プライベート プロセスのサンプルです。 他のすべての PIP メッセージも処理します。 詳細については、[3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)を参照してください。  
  
## <a name="message-flow"></a>メッセージ フロー  
 応答側プライベート プロセスを経由するメッセージ フローは次のとおりです。  
  
1. 応答側プライベート プロセスは、開始側コンピューターから発信された元の着信メッセージを応答側パブリック プロセスから受信します。  
  
2. プライベート プロセスは、LOB アプリケーション メッセージを作成します。 これには、LOB メッセージ テンプレートの取得、XML サービス コンテンツのシリアル化、および LOB メッセージへの XML メッセージ部の読み込みが含まれます。  
  
3. プライベート プロセスは、バックエンド LOB アプリケーション宛てのメッセージを、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesFromLOB テーブルにルーティングします。  
  
4. 元のメッセージに添付ファイルがある場合、プライベート プロセスは AttachmentHelper コンポーネントを呼び出して添付ファイルを処理します。  
  
5. プライベート プロセスは、応答メッセージを MessagesToLOB テーブルに保存したことを LOB アプリケーションに通知します。  
  
6. シングル アクション メッセージの場合、プライベート プロセスは完了します。  
  
7. ダブル アクション メッセージの場合、プライベート プロセスは LOB アプリケーションからの応答をリッスンします。  
  
8. プライベート プロセスは LOB アプリケーションからの応答を受信すると、応答メッセージを作成してパブリック プロセスに送信します。  
  
9. プライベート プロセスは、パブリック プロセスからのシグナルを待ちます。 シグナルを受信すると、プライベート プロセスは LOB シグナル メッセージを作成して LOB アプリケーションに送信します。 RNIF のバージョンが 1.1 の場合、プライベート プロセスは 2 番目の受信確認シグナルの受信をリッスンし、それを受信すると、LOB シグナル メッセージを作成して LOB アプリケーションに送信します。 プライベート プロセスは、各シグナル メッセージを送信した後に LOB アプリケーションに通知します。  
  
10. プライベート プロセスは、開始側から発信されたエラー通知 (NoF) メッセージをパブリック プロセスから受信すると、"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Exception" メッセージを作成して LOB アプリケーションに送信します。  
  
## <a name="see-also"></a>参照  
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)   
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateResponder サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)