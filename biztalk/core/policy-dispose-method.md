---
title: Policy.Dispose メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: ba4713616edf55c149a215a6f7842cd5d0353dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263634"
---
# <a name="policydispose-method"></a><span data-ttu-id="c255b-102">Policy.Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="c255b-102">Policy.Dispose Method</span></span>
<span data-ttu-id="c255b-103">**Policy.Dispose**メソッドによって使用されているリソースを解放する、**ポリシー**クラス、さらにを返します、**ポリシー**キャッシュするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c255b-103">The **Policy.Dispose** method releases resources used by the **Policy** class, and also returns the **Policy** object to the cache.</span></span> <span data-ttu-id="c255b-104">同じポリシーが再度呼び出される場合、キャッシュされた**ポリシー**オブジェクトを使用すると、新しいを作成するために必要な時間を節約**ポリシー**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c255b-104">When the same policy is invoked again, the cached **Policy** object is used, which saves the time needed for creating a new **Policy** object.</span></span>  
  
 <span data-ttu-id="c255b-105">明示的に呼び出さない場合、 **Policy.Dispose**メソッド、ポリシーは返されませんをキャッシュに、.NET ランタイムがガベージ コレクション プロセス中に、オブジェクトが解放されるまでです。</span><span class="sxs-lookup"><span data-stu-id="c255b-105">If you do not explicitly call the **Policy.Dispose** method, then the policy is not returned to the cache until the .NET runtime frees up the object during the garbage collection process.</span></span> <span data-ttu-id="c255b-106">そのため、呼び出す必要は**Policy.Dispose**使用が終了したら、**ポリシー**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c255b-106">Therefore, you should call **Policy.Dispose** when you are finished with the **Policy** object.</span></span>  
  
 <span data-ttu-id="c255b-107">使用するサンプル コード、 **Policy.Dispose**メソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c255b-107">The sample code for using the **Policy.Dispose** method is as follows:</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```