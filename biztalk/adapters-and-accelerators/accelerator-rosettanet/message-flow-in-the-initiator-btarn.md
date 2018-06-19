---
title: メッセージの開始側 BTARN での流れ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85fed6404627fd8abfa9d50e7d56d98ff7306f09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210594"
---
# <a name="message-flow-in-the-initiator-btarn"></a>開始側 BTARN でのメッセージ フロー
開始側コンピューターが、バックエンドの基幹業務 (LOB) アプリケーションから専用形式のメッセージを受信すると、メッセージ フローが開始されます。 メッセージ フローには、受信したメッセージを RNIF (RosettaNet Implementation Framework) に準拠するメッセージに変換して、インターネット経由で応答側コンピューターに送信するタスクも含まれています。  
  
 PIP (Partner Interface Process) がシングル アクションの場合の応答は、受信確認のシグナル メッセージのみです。 シングル アクションのメッセージ フローの詳細については、後の「開始メッセージのフロー」を参照してください。 PIP がダブル アクションの場合、開始側はシングル アクションのメッセージ フローに加えて、応答メッセージを受信し、受信確認を返信します。  
  
 PIP が非同期の場合、インターネットを経由する各メッセージは、個別の HTTP 接続で転送されます。 PIP が同期の場合、各メッセージはプロセスが完了するまで HTTP アダプターが保持する接続と同じ接続で転送されます。 ダブル アクション同期シナリオでは、応答側コンピューターは開始側コンピューターに対して、最初の要求メッセージに応える受信確認を送信しません。 応答メッセージが受信確認となります。  
  
## <a name="btarn-components-on-the-initiator-computer"></a>開始側コンピューター上の BTARN コンポーネント  
 メッセージが開始側コンピュータの [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] を流れていく際は、次のコンポーネントがメッセージを処理します。  
  
-   SQL アダプター  
  
-   XML 受信パイプライン  
  
-   開始側プライベート プロセス  
  
-   開始側パブリック プロセス  
  
-   XML 送信パイプライン  
  
-   HTTP アダプター  
  
-   RNIFSend.aspx ページ  
  
 これらのコンポーネントとメッセージの処理方法の詳細については、次を参照してください。 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)です。  
  
## <a name="flow-of-an-initiated-message"></a>開始メッセージのフロー  
 以下の手順は、開始側の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] コンピュータから発信されたメッセージのメッセージ フローを示します。 このプロセスを次に示します。  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1.  基幹業務アプリケーションにメッセージを送信する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]です。  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースから SQL アダプタにメッセージを送信します。  
  
3.  XML 受信パイプラインは、メッセージの単純な XML 検証を行います。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] が MessageBox データベースにメッセージをルーティングします。  
  
5.  プライベート プロセスでメッセージの Service Content を処理します。  
  
6.  パブリック プロセスが、メッセージの RNIF ヘッダーを処理します。  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、再度 MessageBox データベースにメッセージをルーティングします。  
  
8.  送信パイプラインは、メッセージのアセンブリと署名/暗号化/エンコードを実行します。  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、HTTP アダプタにメッセージをルーティングします。  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は RNIFSend.aspx ページにメッセージをルーティングし、メッセージはここから送信先にインターネット経由で送信されます。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [応答側 BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md)   
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)