---
title: オーケストレーションでビジネス ルールの呼び出し |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], business rules
- business rules, orchestrations
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
- orchestrations, business rules
ms.assetid: ac3a3277-e9ea-4f40-9326-c63076c6b90e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ecbb9738089dfa2d885f9aa45ac12e92ed27aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261826"
---
# <a name="invoking-business-rules-in-orchestrations"></a><span data-ttu-id="7f007-102">オーケストレーションでビジネス ルールの呼び出し</span><span class="sxs-lookup"><span data-stu-id="7f007-102">Invoking Business Rules in Orchestrations</span></span>
<span data-ttu-id="7f007-103">呼び出すことができます、ポリシー (ルール セット) を使用してオーケストレーションから、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="7f007-103">You can invoke a policy (or rule set) from an orchestration by using the **Call Rules** shape.</span></span> <span data-ttu-id="7f007-104">ポリシーは、そのポリシー内のルールに基づいて動作するルール エンジンを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7f007-104">The policy invokes the rule engine, which operates on the rules in the policy.</span></span>  
  
 <span data-ttu-id="7f007-105">ルールの呼び出しを使用して、だけでなく、ルール エンジンを式からプログラムによって呼び出すことがコード、例についてで、**式**または**メッセージの割り当て**図形です。</span><span class="sxs-lookup"><span data-stu-id="7f007-105">In addition to using Call Rules, the rules engine can be programmatically called from expression code, for example, in an **Expression** or **Message Assignment** shape.</span></span> <span data-ttu-id="7f007-106">ポリシーをプログラムで実行する方法の詳細については、次を参照してください。[ポリシーの実行方法](../core/how-to-execute-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f007-106">For information about programmatically executing policies, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  
  
 <span data-ttu-id="7f007-107">このセクションでは、ビジネス ポリシーを BizTalk オーケストレーションから呼び出して実行するために必要な構成と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f007-107">This section describes configuration information and the procedures required to call and execute a business policy from a BizTalk orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f007-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7f007-108">In This Section</span></span>  
  
-   [<span data-ttu-id="7f007-109">構成情報</span><span class="sxs-lookup"><span data-stu-id="7f007-109">Configuration Information</span></span>](../core/configuration-information.md)  
  
-   [<span data-ttu-id="7f007-110">ルールの呼び出し図形を使用する方法</span><span class="sxs-lookup"><span data-stu-id="7f007-110">How to Use the Call Rules Shape</span></span>](../core/how-to-use-the-call-rules-shape.md)