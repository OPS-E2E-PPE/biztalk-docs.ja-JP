---
title: 応答側パブリック プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a98cfde175b9377be11bf4b18570eb93bd16437
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282430"
---
# <a name="responder-public-process"></a>応答側パブリック プロセス
この応答側のパブリック プロセスは、開始側から RNIF (RosettaNet Implementation Framework) メッセージを受信し、必要に応じて応答します。  
  
## <a name="message-flow-in-the-responder-public-process"></a>応答側パブリック プロセスにおけるメッセージ フロー  
 応答側パブリック プロセスにおけるメッセージ フローは次のとおりです。  
  
1. 応答側パブリック プロセスが応答側メッセージ ボックス データベースから RNIF メッセージを受信します。  
  
2. パブリック プロセスが Service Content およびヘッダーをアクション メッセージから抽出してプライベート プロセスに送信します。  
  
   > [!NOTE]
   >  応答側パブリック プロセスが着信メッセージに対して標準検証 (適用できる場合は、検証アダプターに含まれる追加の検証) を実行します。 検証が正常に終了すると、パブリック プロセスはアプリケーション アダプターを開始して個々の実装に基づいて通知を実行します。 応答側パブリック プロセスはメッセージ ボックス データベースにメッセージを保存し、`BeginNotify` クラスの `ApplicationAdapter` メソッドを使用して、メッセージ ボックスにメッセージを保存したことを応答側プライベート プロセスに通知します。 検証アダプターとアプリケーション アダプターの詳細については、次を参照してください。 [ValidationAdapter &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)と[ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)します。  
  
3. 非同期のシングル アクションの場合、パブリック プロセスは Service Content のメッセージ部を Preamble、Service Header、および Delivery Header (RNIF 2.01 の場合のみ) でラップして、RNIF シグナル メッセージ (受信確認) を作成します。 パブリック プロセスは、パーティ間の取引先アグリーメントに保存されている情報 (プロセス構成設定、送信元と送信先パーティの構成情報、および PIP (Partner Interface Process) 変数) を使用して、Preamble、Service Header、および Delivery Header を作成します。 その後、開始側にシグナル メッセージを送信します。  
  
   > [!NOTE]
   >  シングル アクション メッセージの場合、メッセージ フローは完了します。  
  
4. パブリック プロセスは、待機状態 (応答側プライベート プロセスのアクションを待っている状態) になります。  
  
5. 待機状態 (応答側プライベート プロセスのアクションを待っている状態) は、次のアクションによって終了します。  
  
   1. 応答側プライベート プロセスが元のダブル アクション メッセージに応答して、Service Content メッセージおよびヘッダーを返した場合。  
  
       パブリック プロセスがプライベート プロセスから応答サービス コンテンツを受信する場合、パブリック プロセスは Service Content を含む RNIF メッセージを作成します。 パブリック プロセスは、送信元と送信先のパーティに関する構成情報を含むヘッダー、およびパーティ間のアグリーメントに保存されている PIP 変数で Service Content のメッセージ部をラップして、メッセージを作成します。  
  
       パブリック プロセスが Action/Signal Role リンク ポートを使用して、開始側に RNIF メッセージを送信します。  
  
       マイクロソフトに通知を受信するパブリック プロセス場合[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]メッセージ正常に送信して、パブリック プロセスとその状態、プライベート プロセスに返信し終了します。  
  
       パブリック プロセスは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージを正常に送信したことを知らせる通知を受信すると、待機状態 (開始側のアクションを待っている状態) になります。 この待機状態は、開始側が応答側のアクションを待つ場合の待機状態に似ています。  
  
   2. パブリック プロセスが、開始側からエラー通知メッセージ (NoF) を受信した場合。  
  
   > [!NOTE]
   >  応答側プライベート プロセスが、着信メッセージを正常に処理した後に応答側パブリック プロセスに通知します。 応答側パブリック プロセスが `EndNotify` クラスの `ApplicationAdapter` メソッドからこの通知を受信した場合のみ、応答側パブリック プロセスが正常に完了したことになります。  
  
6. 応答側パブリック プロセスは、待機状態 (応答側パブリック プロセスが送信した応答メッセージに対する開始側からのシグナルの受信を待っている状態) になります。  
  
## <a name="see-also"></a>参照  
 [パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [開始側パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)   
 [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)   
 [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)