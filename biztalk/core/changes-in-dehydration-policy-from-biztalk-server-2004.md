---
title: "BizTalk Server 2004 からの退避ポリシーの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c760bffe-5f64-4eb2-bc23-89d7c9310f39
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 167c53d953369d7b35138995b4f38ad8994c18cb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a><span data-ttu-id="3bed9-102">BizTalk Server 2004 からの退避ポリシーの変更点</span><span class="sxs-lookup"><span data-stu-id="3bed9-102">Changes in Dehydration Policy from BizTalk Server 2004</span></span>
<span data-ttu-id="3bed9-103">BizTalk Server の退避ポリシーが変更された[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="3bed9-103">BizTalk Server dehydration policy has changed from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to BizTalk Server.</span></span> <span data-ttu-id="3bed9-104">違いの説明は、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]で退避を判断するブール値を次で BizTalk Server をまとめると[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)](true = 退避)</span><span class="sxs-lookup"><span data-stu-id="3bed9-104">The explanation for the difference between [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] and BizTalk Server can be summarized by the following Boolean that determines dehydration in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = dehydrate)</span></span>  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 <span data-ttu-id="3bed9-105">BizTalk Server の退避ポリシーは、このマイナーの方法で変更されました。</span><span class="sxs-lookup"><span data-stu-id="3bed9-105">Dehydration policy for BizTalk Server has changed in this minor way.</span></span> <span data-ttu-id="3bed9-106">BizTalk Server、常に退避受信/遅延/待ち受けで 2 よりも長く待機している場合 ***MaxThreshold**です。</span><span class="sxs-lookup"><span data-stu-id="3bed9-106">BizTalk Server always dehydrates at a receive/delay/listen if there is a wait longer than 2***MaxThreshold**.</span></span>