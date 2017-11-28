---
title: "オーケストレーションでルールをビジネスを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- atomic transactions, business rules
- Call Rules shape [Orchestration Designer], business rules
- business rules, orchestrations
- orchestrations, business rules
ms.assetid: d20473c2-267f-4a44-93c3-df6ef655020c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346582f90cada01b2350fae227885a9e9cd71712
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-business-rules-in-orchestrations"></a><span data-ttu-id="53f4e-102">オーケストレーションでビジネス ルールを使用する方法 [BTS05]</span><span class="sxs-lookup"><span data-stu-id="53f4e-102">How to Use Business Rules in Orchestrations</span></span>
<span data-ttu-id="53f4e-103">ビジネス ルール ポリシーのインスタンスを作成し、オーケストレーションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="53f4e-103">You can create an instance of a Business Rules policy and execute it in your orchestration.</span></span> <span data-ttu-id="53f4e-104">これを行うには、アトミック トランザクション スコープ内部にルールの呼び出し図形を追加し、追加した図形にポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="53f4e-104">To do this, add a Call Rules shape inside an atomic transaction scope, and configure a policy on it.</span></span>  
  
## <a name="examples-of-using-business-rules"></a><span data-ttu-id="53f4e-105">ビジネス ルールの使用例</span><span class="sxs-lookup"><span data-stu-id="53f4e-105">Examples of Using Business Rules</span></span>  
  
-   [<span data-ttu-id="53f4e-106">Business Rules こんにちは World1 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="53f4e-106">Business Rules Hello World1 (BizTalk Server Sample)</span></span>](../core/business-rules-hello-world1-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="53f4e-107">Business Rules こんにちは World2 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="53f4e-107">Business Rules Hello World2 (BizTalk Server Sample)</span></span>](../core/business-rules-hello-world2-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="53f4e-108">ローン処理を使用してビジネス ルール (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="53f4e-108">Loans Processing Using Business Rules (BizTalk Server Sample)</span></span>](../core/loans-processing-using-business-rules-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="53f4e-109">Medical Claims 処理およびテストのポリシー (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="53f4e-109">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>](../core/medical-claims-processing-and-testing-policies-biztalk-server-sample.md)  
  
-   <span data-ttu-id="53f4e-110">サンプルをダウンロードする SDK「ポリシーの連鎖」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="53f4e-110">Download the SDK sample "Policy Chaining" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f4e-111">参照</span><span class="sxs-lookup"><span data-stu-id="53f4e-111">See Also</span></span>  
 [<span data-ttu-id="53f4e-112">作成して、ビジネス ルールの使用</span><span class="sxs-lookup"><span data-stu-id="53f4e-112">Creating and Using Business Rules</span></span>](../core/creating-and-using-business-rules.md)