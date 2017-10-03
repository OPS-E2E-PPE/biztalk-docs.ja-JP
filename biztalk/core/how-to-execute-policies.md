---
title: "ポリシーを実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0aa834150f0d5c84ebb4c757769a2be38f3942
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-execute-policies"></a>ポリシーを実行する方法
次のサンプル コードを使用してプログラムからポリシーを実行するルール エンジンを起動する方法を示しています、**ポリシー**クラス内で、 **Microsoft.RuleEngine**アセンブリ。  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a>Policy クラスの重要なメソッド  
 Policy クラスの重要なメソッドとその説明を次に示します。  
  
|Policy クラスのメソッド|Description|  
|--------------------------------|-----------------|  
|Execute|指定された短期間のファクトをルール エンジンの作業メモリに追加し、一致 - 競合解決 - アクションのアルゴリズムを使用してポリシーを実行します。 一致-競合解決-アクションのアルゴリズムの詳細については、次を参照してください。[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)です。|  
|Dispose|ポリシーを実行するためにルール エンジンで使用されているリソースを解放します。|  
|Clear|ポリシーを実行するために作成されたルール エンジン インスタンスの作業メモリと議題をクリアまたはリセットします。|  
  
## <a name="see-also"></a>参照  
 [Policy.Dispose メソッド](../core/policy-dispose-method.md)