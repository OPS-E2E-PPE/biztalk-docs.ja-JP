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
ms.sourcegitcommit: 85e827c42f193e44ca8b5b8d78d6f8b8ac686f1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767028"
---
# <a name="mapping-phase-recoverable-interchange-processing"></a>マッピング フェーズ (回復可能なインターチェンジ処理)
既定では、インターチェンジ内のメッセージは、受信ポートのマッピング フェーズに失敗した場合、インターチェンジ全体が中断されます。 この動作を変更するにはという名前のプロパティを追加することで**BTS します。SuspendMessageOnMappingFailure**に、コンテキスト プロパティの値を設定して、メッセージ コンテキストに`True`パイプライン コンポーネントから。 このプロパティに設定しているときに`True`、エンド ポイント マネージャーは、保留キューにマッピング中に失敗し、インターチェンジの残りのメッセージの処理を続行するメッセージを配置します。  
  
 次のコードの値の設定、 **SuspendMessageOnMappingFailure**プロパティを True にします。  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```
