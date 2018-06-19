---
title: PrivateResponder サンプル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3de3428aa9971ba62b682494cd94c6bb74bcab53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206946"
---
# <a name="privateresponder-sample"></a>PrivateResponder サンプル
PrivateResponder.odx サンプルには、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] によってインストールされる応答側プライベート プロセスのコードが含まれます。 この汎用プライベート プロセスは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信します。  
  
 既定では、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムのインストールのサンプルを\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for rosettanet \sdk\PrivateResponder です。  
  
## <a name="sample-contents"></a>サンプルの内容  
 応答側プライベート プロセスは、応答側の内部ビジネス プロセスです。 このプライベート プロセスにより、応答側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。 応答側プライベート プロセスは、パブリック プロセスと通信してメッセージに応答します。  
  
 応答側プライベート プロセスは実装ごとに固有です。 PrivateResponder.odx サンプルは用途に合わせてカスタマイズできます。 ただし、応答側パブリック プロセスの機能に支障をきたさないように注意する必要があります。  
  
 詳細については、メッセージ フローの説明を参照してください。[応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)