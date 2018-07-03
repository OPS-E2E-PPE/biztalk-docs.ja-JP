---
title: PrivateInitiator サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ab84d145939191a8bdbca9afb44d04fdf24b3e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011283"
---
# <a name="privateinitiator-sample"></a>PrivateInitiator サンプル
PrivateInitiator.odx サンプルには、Microsoft® BizTalk Server によってインストールされる開始側プライベート プロセスのコードが含まれています。 これは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信する、汎用のプライベート プロセスです。  
  
 既定で、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってサンプルでは、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>のアクセラレータRosettaNet\SDK\PrivateInitiator します。  
  
## <a name="sample-contents"></a>サンプルの内容  
 開始側プライベート プロセスは、開始側の内部ビジネス プロセスです。 このプライベート プロセスにより、開始側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。 開始側プライベート プロセスは、パブリック プロセスと通信してメッセージを開始します。  
  
 開始側プライベート プロセスは実装ごとに固有です。 PrivateInitiator.odx サンプルは用途に合わせてカスタマイズできます。 ただし、開始側パブリック プロセスの機能に支障をきたさないように注意する必要があります。  
  
 詳細については、メッセージ フローの説明を含む、次を参照してください。[開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)