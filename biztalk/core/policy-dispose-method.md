---
title: Policy.Dispose メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db37c6b9-acf0-42ee-9356-4d1567934862
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eba833edcedd814fffd823bfe01729b77f0f033
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394960"
---
# <a name="policydispose-method"></a>Policy.Dispose メソッド
**Policy.Dispose**メソッドで使用されるリソースを解放、**ポリシー**クラス、およびも返します、**ポリシー**キャッシュするオブジェクト。 同じポリシーが再度呼び出されるとき、キャッシュされた**ポリシー**オブジェクトを使用すると、新しいを作成するために必要な時間を節約**ポリシー**オブジェクト。  
  
 明示的に呼び出さない場合、 **Policy.Dispose**メソッド、ポリシーは返されませんをキャッシュに、ガベージ コレクション プロセス中に、.NET ランタイムがオブジェクトを解放するまでです。 そのため、呼び出す必要がある**Policy.Dispose**使用が終了したら、**ポリシー**オブジェクト。  
  
 使用するためのサンプル コード、 **Policy.Dispose**メソッドを次に示します。  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```