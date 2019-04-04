---
title: メッセージの応答側 BTARN でのフロー |Microsoft Docs
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
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629e53f7126c15f84640c8862644beb78e2a5cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980707"
---
# <a name="message-flow-in-the-responder-btarn"></a>応答側 BTARN でのメッセージ フロー
応答側コンピューターのメッセージ フローは、開始側コンピューターからインターネット経由でメッセージを受信することから始まります。 これには、RNIF (RosettaNet Implementation Framework) 準拠のメッセージをバックエンド アプリケーション専用形式のメッセージに変換し、基幹業務 (LOB) アプリケーションにメッセージをルーティングする処理が含まれます。  
  
 PIP (Partner Interface Process) がシングル アクションの場合の応答は、受信確認のシグナル メッセージのみです。 PIP がダブル アクションの場合、応答側は応答メッセージを処理して送信した後、その応答の受信確認を受信します。  
  
 PIP が非同期の場合、インターネットを経由する各メッセージは、個別の HTTP 接続で転送されます。 PIP が同期の場合、各メッセージはプロセスが完了するまで HTTP アダプターが保持する接続と同じ接続で転送されます。 ダブル アクション同期シナリオでは、応答側コンピューターは開始側コンピューターに対して、最初の要求メッセージに応える受信確認を送信しません。 応答メッセージが受信確認となります。  
  
## <a name="btarn-components-on-the-responder-computer"></a>応答側コンピューター上の BTARN コンポーネント  
 メッセージが Microsoft を流れるよう[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]応答側コンピューターは、次のコンポーネントによってメッセージが処理されます。  
  
- RNIFReceive.aspx ページ  
  
- HTTP アダプター  
  
- 受信パイプライン。  
  
- 応答側パブリック プロセス  
  
- 応答側プライベート プロセス  
  
- SQL アダプター  
  
- [送信パイプライン]  
  
  これらのコンポーネントとメッセージの処理方法の詳細については、[BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)を参照してください。  
  
## <a name="message-flow-on-the-responder-computer"></a>応答側コンピューターでのメッセージ フロー  
 応答側 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] コンピュータでの受信メッセージのフローは次のとおりです。  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1. RNIFReceive aspx ページが開始側から着信メッセージを受信します。  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージを HTTP アダプタに送信し、HTTP アダプタがそれを受信パイプラインに送信します。  
  
3. 受信パイプラインがメッセージのデコード、逆アセンブル、およびパーティの解決を実行し、バックエンドの基幹業務 (LOB) アプリケーションの専用形式に変換します。  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が MessageBox データベースにメッセージをルーティングします。  
  
5. パブリック プロセスが、メッセージの RNIF ヘッダーを処理します。  
  
6. プライベート プロセスでメッセージの Service Content を処理します。 プライベート プロセスでは受信確認を生成します。この受信確認は、インターネット上でパブリック プロセス、MessageBox データベース、送信パイプライン、HTTP アダプターを経由して開始側に返されます。  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が MessageBox データベースにメッセージをルーティングします。  
  
8. 送信パイプラインがメッセージを編成し、メッセージに署名して、暗号化とエンコードを行います。  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が SQL アダプタにメッセージをルーティングします。  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] を経由してバックエンドの基幹業務 (LOB) アプリケーションにメッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [イニシエーター BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)