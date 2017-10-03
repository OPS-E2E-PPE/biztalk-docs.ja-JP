---
title: "サンプル BTARN ビジネス ポリシー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfe0bd746894106fc7ac9ebeaae600fe7344ba18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-btarn-business-policy"></a><span data-ttu-id="aee7b-102">サンプル BTARN ビジネス ポリシー</span><span class="sxs-lookup"><span data-stu-id="aee7b-102">Sample BTARN Business Policy</span></span>
<span data-ttu-id="aee7b-103">このサンプルは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ビジネス ルール ポリシーに関連する XML コードです。</span><span class="sxs-lookup"><span data-stu-id="aee7b-103">This sample is the XML code associated with a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] business-rules policy.</span></span>  
  
 <span data-ttu-id="aee7b-104">サンプル ファイル samplebtarnpolicy.xml は\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for rosettanet \sdk\pipautomation\3a4 にあります。</span><span class="sxs-lookup"><span data-stu-id="aee7b-104">The sample file is samplebtarnpolicy.xml in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="aee7b-105">使用例</span><span class="sxs-lookup"><span data-stu-id="aee7b-105">Demonstrates</span></span>  
 <span data-ttu-id="aee7b-106">このコードは、次のルールを含んでいるビジネス ルール ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="aee7b-106">This code shows a business-rule policy with the following rule:</span></span>  
  
 <span data-ttu-id="aee7b-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span><span class="sxs-lookup"><span data-stu-id="aee7b-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee7b-108">参照</span><span class="sxs-lookup"><span data-stu-id="aee7b-108">See Also</span></span>  
 [<span data-ttu-id="aee7b-109">ビジネス ルールを使用して、3A4 プライベート応答側オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="aee7b-109">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)