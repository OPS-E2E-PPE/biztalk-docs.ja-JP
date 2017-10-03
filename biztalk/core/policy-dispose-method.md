---
title: "Policy.Dispose メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db37c6b9-acf0-42ee-9356-4d1567934862
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba4713616edf55c149a215a6f7842cd5d0353dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="policydispose-method"></a>Policy.Dispose メソッド
**Policy.Dispose**メソッドによって使用されているリソースを解放する、**ポリシー**クラス、さらにを返します、**ポリシー**キャッシュするオブジェクト。 同じポリシーが再度呼び出される場合、キャッシュされた**ポリシー**オブジェクトを使用すると、新しいを作成するために必要な時間を節約**ポリシー**オブジェクト。  
  
 明示的に呼び出さない場合、 **Policy.Dispose**メソッド、ポリシーは返されませんをキャッシュに、.NET ランタイムがガベージ コレクション プロセス中に、オブジェクトが解放されるまでです。 そのため、呼び出す必要は**Policy.Dispose**使用が終了したら、**ポリシー**オブジェクト。  
  
 使用するサンプル コード、 **Policy.Dispose**メソッドを次に示します。  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```