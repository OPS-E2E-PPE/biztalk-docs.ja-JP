---
title: オーケストレーションでビジネス ルールの呼び出し |Microsoft Docs
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
ms.openlocfilehash: 691fa4bf5e9633e32cfb5583ab8a181f0f69633a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380984"
---
# <a name="invoking-business-rules-in-orchestrations"></a><span data-ttu-id="256f5-102">オーケストレーションでビジネス ルールの呼び出し</span><span class="sxs-lookup"><span data-stu-id="256f5-102">Invoking Business Rules in Orchestrations</span></span>
<span data-ttu-id="256f5-103">呼び出すことができますを使用してオーケストレーションからポリシー (またはルール セット)、**ルールの呼び出し**図形。</span><span class="sxs-lookup"><span data-stu-id="256f5-103">You can invoke a policy (or rule set) from an orchestration by using the **Call Rules** shape.</span></span> <span data-ttu-id="256f5-104">ポリシーは、ポリシー内のルールに機能します。 ルール エンジンを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="256f5-104">The policy invokes the rule engine, which operates on the rules in the policy.</span></span>  
  
 <span data-ttu-id="256f5-105">ルールの呼び出しを使用するだけでなく、ルール エンジンを式からプログラムで呼び出すことがコード、例についてで、**式**または**メッセージの割り当て**図形。</span><span class="sxs-lookup"><span data-stu-id="256f5-105">In addition to using Call Rules, the rules engine can be programmatically called from expression code, for example, in an **Expression** or **Message Assignment** shape.</span></span> <span data-ttu-id="256f5-106">ポリシーをプログラムで実行する方法の詳細については、次を参照してください。[ポリシーの実行方法](../core/how-to-execute-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="256f5-106">For information about programmatically executing policies, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  
  
 <span data-ttu-id="256f5-107">このセクションでは、構成情報およびを呼び出すし、BizTalk オーケストレーションからのビジネス ポリシーの実行に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="256f5-107">This section describes configuration information and the procedures required to call and execute a business policy from a BizTalk orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="256f5-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="256f5-108">In This Section</span></span>  
  
-   [<span data-ttu-id="256f5-109">構成情報</span><span class="sxs-lookup"><span data-stu-id="256f5-109">Configuration Information</span></span>](../core/configuration-information.md)  
  
-   [<span data-ttu-id="256f5-110">ルールの呼び出し図形を使用する方法</span><span class="sxs-lookup"><span data-stu-id="256f5-110">How to Use the Call Rules Shape</span></span>](../core/how-to-use-the-call-rules-shape.md)