---
title: "FRR NAK ハンドラー サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a3881b8bcf4b62af7653ef6214b4fccdf8402d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-nak-handler-sample"></a>FRR NAK ハンドラーのサンプル
FRR NAK ハンドラーのサンプルでは、迅速な応答を FIN 対応調整 (FRR) が関連付けられたメッセージを処理するカスタム ハンドラーを作成する方法を示します。 このカスタム ハンドラーを SWIFT 正常から取得されなかったメッセージ A4SWIFT を示す MTS21_FIN_ACKNAK 負の値確認のメッセージで FRR が関連付けられたメッセージを処理します。 カスタム ハンドラーは、2 部構成のメッセージでは、メッセージを作成、メッセージにエラー オブジェクトを追加し、発生するメッセージ修復オーケストレーションがメッセージを取得するプロパティを昇格させます。 その結果、修理会社は、メッセージを修正し、SWIFT Alliance アクセス (SAA) に再送信できます。  
  
 **サンプル コンポーネント**  
  
 FRR NAK ハンドラー サンプルには、次のコンポーネントが含まれます。  
  
-   **RepairSWIFTRejectedMessage.odx です。** このオーケストレーションは、SWIFT が正常に受信できません、修理会社が修正し、メッセージを再送信できるように、メッセージ修復オーケストレーションにルーティングするメッセージを処理するカスタム ハンドラーです。  
  
-   **RepairSWIFTRejectedMessage.btproj です。** このプロジェクトには、ビルドおよび配置するには、RepairSWIFTRejectedMessage.odx と、プロジェクトに必要な参照が含まれています。  
  
-   **RepairSWIFTRejectedMessage.sln です。** このソリューションには、RepairSWIFTRejectedMessage.btproj プロジェクトが含まれています。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [FRR NAK ハンドラーのサンプルを実装します。](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
-   [FRR NAK ハンドラーのサンプルのしくみ](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
