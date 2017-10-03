---
title: "PrivateInitiator サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d33b164033cdd3b966ed1f0e77dd551cd56076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="privateinitiator-sample"></a>PrivateInitiator サンプル
PrivateInitiator.odx サンプルには、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] によってインストールされる開始側プライベート プロセスのコードが含まれます。 これは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信する、汎用のプライベート プロセスです。  
  
 既定では、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムのインストールのサンプルを\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for rosettanet \sdk\PrivateInitiator です。  
  
## <a name="sample-contents"></a>サンプルの内容  
 開始側プライベート プロセスは、開始側の内部ビジネス プロセスです。 このプライベート プロセスにより、開始側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。 開始側プライベート プロセスは、パブリック プロセスと通信してメッセージを開始します。  
  
 開始側プライベート プロセスは実装ごとに固有です。 PrivateInitiator.odx サンプルは用途に合わせてカスタマイズできます。 ただし、開始側パブリック プロセスの機能に支障をきたさないように注意する必要があります。  
  
 詳細については、メッセージ フローの説明を参照してください。[開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)