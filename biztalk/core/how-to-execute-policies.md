---
title: ポリシーを実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eaf60193a3435808c0901ca1c441527a67884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337817"
---
# <a name="how-to-execute-policies"></a>ポリシーを実行する方法
次のサンプル コードを使用してポリシーをプログラムで実行するルール エンジンを呼び出す方法を示しています、**ポリシー**クラス、 **Microsoft.RuleEngine**アセンブリ。  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a>ポリシー クラスの重要なメソッド  
 Policy クラスとその説明の重要なメソッドを次に示します。  
  
|ポリシー クラスのメソッド|説明|  
|--------------------------------|-----------------|  
|Execute|指定した短期間のファクトをルール エンジンの作業メモリに追加し、一致-競合解決-アクションのアルゴリズムを使用してポリシーを実行します。 一致-競合解決-アクションのアルゴリズムの詳細については、次を参照してください。[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)します。|  
|Dispose|ポリシーを実行するため、ルール エンジンによって使用されるリソースを解放します。|  
|Clear|クリアまたは作業メモリと、ポリシーの実行用に作成されたルール エンジン インスタンスの議題をリセットします。|  
  
## <a name="see-also"></a>参照  
 [Policy.Dispose メソッド](../core/policy-dispose-method.md)