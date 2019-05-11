---
title: PrivateResponder サンプル |Microsoft Docs
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
ms.openlocfilehash: a02d4b2d902f2dad24a20c150e474e671f582a66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282520"
---
# <a name="privateresponder-sample"></a>PrivateResponder サンプル
PrivateResponder.odx サンプルには、Microsoft® によってインストールされる応答側プライベート プロセスのコードが含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。 この汎用プライベート プロセスは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信します。  
  
 既定で、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってサンプルでは、 \<*ドライブ*>: \Program Files\\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\PrivateResponder します。  
  
## <a name="sample-contents"></a>サンプルの内容  
 応答側プライベート プロセスは、応答側の内部ビジネス プロセスです。 このプライベート プロセスにより、応答側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。 応答側プライベート プロセスは、パブリック プロセスと通信してメッセージに応答します。  
  
 応答側プライベート プロセスは実装ごとに固有です。 PrivateResponder.odx サンプルは用途に合わせてカスタマイズできます。 ただし、応答側パブリック プロセスの機能に支障をきたさないように注意する必要があります。  
  
 詳細については、メッセージ フローの説明を含む、次を参照してください。[応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)