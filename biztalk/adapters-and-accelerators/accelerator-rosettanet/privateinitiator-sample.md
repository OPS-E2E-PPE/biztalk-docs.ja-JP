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
ms.openlocfilehash: 853b77e24359d6a833d526fc07166384ea946887
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="privateinitiator-sample"></a>PrivateInitiator サンプル
PrivateInitiator.odx サンプルがインストールされている開始側プライベート プロセスのコードが含まれています[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server です。 これは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信する、汎用のプライベート プロセスです。  
  
 既定では、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムのインストールのサンプルを\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>\Sdk\privateinitiator のアクセラレータです。  
  
## <a name="sample-contents"></a>サンプルの内容  
 開始側プライベート プロセスは、開始側の内部ビジネス プロセスです。 このプライベート プロセスにより、開始側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。 開始側プライベート プロセスは、パブリック プロセスと通信してメッセージを開始します。  
  
 開始側プライベート プロセスは実装ごとに固有です。 PrivateInitiator.odx サンプルは用途に合わせてカスタマイズできます。 ただし、開始側パブリック プロセスの機能に支障をきたさないように注意する必要があります。  
  
 詳細については、メッセージ フローの説明を参照してください。[開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)