---
title: FRR NAK ハンドラー サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35574f47af789054bd8192da93ce5cffa1b3984b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996937"
---
# <a name="frr-nak-handler-sample"></a>FRR NAK ハンドラー サンプル
FRR NAK ハンドラー サンプルでは、迅速な応答を FIN 応答の調整 (FRR) が関連付けられたメッセージを処理するカスタム ハンドラーを作成する方法を示します。 このカスタム ハンドラーでは、する SWIFT 正常から受信しなかったメッセージ A4SWIFT を示す MTS21_FIN_ACKNAK 負では受信確認のメッセージの FRR が関連付けられたメッセージが処理されます。 カスタム ハンドラーは、エラー オブジェクトを 2 つの部分のメッセージがメッセージになります、メッセージに追加し、メッセージ修復オーケストレーションが、メッセージを取得するプロパティを昇格させます。 その結果、修理会社は、メッセージを修正し、SWIFT Alliance アクセス (SAA) を再送信できます。  
  
 **サンプル コンポーネント**  
  
 FRR NAK ハンドラー サンプルには、次のコンポーネントが含まれます。  
  
- **RepairSWIFTRejectedMessage.odx します。** このオーケストレーションは、SWIFT 正常に受信できなかった、修理会社が修正し、メッセージの再送信できるようにメッセージ修復オーケストレーションにルーティングするメッセージを処理するカスタム ハンドラーです。  
  
- **RepairSWIFTRejectedMessage.btproj します。** このプロジェクトには、構築およびデプロイするには、RepairSWIFTRejectedMessage.odx と、プロジェクトに必要な参照が含まれています。  
  
- **RepairSWIFTRejectedMessage.sln します。** このソリューションには、RepairSWIFTRejectedMessage.btproj プロジェクトが含まれています。  
  
  このセクションには、次のトピックが含まれています。  
  
- [FRR NAK ハンドラー サンプルの実装](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
- [FRR NAK ハンドラー サンプルのしくみ](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
