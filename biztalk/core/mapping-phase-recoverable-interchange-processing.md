---
title: マッピング フェーズ (回復可能なインターチェンジ処理) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544d85c7-bc47-46c1-8990-82b48a8f2f23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f7b00bb5bd1490b5a3249ed2b37fb1335e266b
ms.sourcegitcommit: 68239c81fb12b84a479bf6a4ed8c5b25b249f5ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58852367"
---
# <a name="mapping-phase-recoverable-interchange-processing"></a>マッピング フェーズ (回復可能なインターチェンジ処理)
既定では、インターチェンジのメッセージが受信ポートのマッピング フェーズで失敗すると、インターチェンジ全体が中断されます。 この動作を変更するにはという名前のプロパティを追加することで**BTS します。SuspendMessageOnMappingFailure**に、コンテキスト プロパティの値を設定して、メッセージ コンテキストに`True`パイプライン コンポーネントから。 このプロパティを `True` に設定すると、エンド ポイント マネージャーはマッピングの間に失敗したメッセージを保留キューに格納し、インターチェンジの残りのメッセージの処理を続けます。  
  
 次のコードの値の設定、 **SuspendMessageOnMappingFailure**プロパティを True にします。  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```
