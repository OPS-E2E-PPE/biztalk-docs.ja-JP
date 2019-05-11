---
title: サンプル BTARN ビジネス ポリシー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf5431fdf5bf03fd17634266528201891e2a7d30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282040"
---
# <a name="sample-btarn-business-policy"></a><span data-ttu-id="b2b2b-102">サンプル BTARN ビジネス ポリシー</span><span class="sxs-lookup"><span data-stu-id="b2b2b-102">Sample BTARN Business Policy</span></span>
<span data-ttu-id="b2b2b-103">このサンプルは、Microsoft® に関連付けられている XML コード[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ビジネス ルール ポリシー。</span><span class="sxs-lookup"><span data-stu-id="b2b2b-103">This sample is the XML code associated with a Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] business-rules policy.</span></span>  
  
 <span data-ttu-id="b2b2b-104">サンプル ファイル samplebtarnpolicy.xml は、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\PIPAutomation\3A4 します。</span><span class="sxs-lookup"><span data-stu-id="b2b2b-104">The sample file is samplebtarnpolicy.xml in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b2b2b-105">使用例</span><span class="sxs-lookup"><span data-stu-id="b2b2b-105">Demonstrates</span></span>  
 <span data-ttu-id="b2b2b-106">このコードは、次の規則にビジネス ルール ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="b2b2b-106">This code shows a business-rule policy with the following rule:</span></span>  
  
 <span data-ttu-id="b2b2b-107">場合 (AccountNumber、着信 3A4 発注書メッセージ =「111111111」) および (注文の MonetaryAmount < 500) 応答メッセージを自動的に送信</span><span class="sxs-lookup"><span data-stu-id="b2b2b-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b2b-108">参照</span><span class="sxs-lookup"><span data-stu-id="b2b2b-108">See Also</span></span>  
 [<span data-ttu-id="b2b2b-109">ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="b2b2b-109">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)