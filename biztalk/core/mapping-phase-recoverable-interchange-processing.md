---
title: "マッピング フェーズ (回復可能なインターチェンジ処理) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 544d85c7-bc47-46c1-8990-82b48a8f2f23
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b3e45cf337702457dc8e5986db54df6bea5e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mapping-phase-recoverable-interchange-processing"></a>マッピング フェーズ (回復可能なインターチェンジ処理)
既定では、インターチェンジのメッセージが受信ポートのマッピング フェーズで失敗すると、インターチェンジ全体が中断されます。 この動作を変更するにはという名前のプロパティを追加することによって**BTS です。SuspendMessageOnMapFailure**をメッセージ コンテキストとするコンテキスト プロパティの値を設定して`True`パイプライン コンポーネントからです。 このプロパティを `True` に設定すると、エンド ポイント マネージャーはマッピングの間に失敗したメッセージを保留キューに格納し、インターチェンジの残りのメッセージの処理を続けます。  
  
 次のコードの値の設定、 **SuspendMessageOnFailure**プロパティを True にします。  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```