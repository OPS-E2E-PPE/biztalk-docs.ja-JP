---
title: EDI パーティに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86475960-cdb2-4b39-817a-b5d834f498a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7305d28b9162ab1d88be8dde9e79437d5d1e85b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330337"
---
# <a name="known-issues-with-edi-parties"></a><span data-ttu-id="d1340-102">EDI パーティに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="d1340-102">Known Issues with EDI Parties</span></span>
<span data-ttu-id="d1340-103">このセクションには、EDI パーティと、パートナー アグリーメント マネージャに関する既知の問題を説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1340-103">This section contains topics that describe known issues with EDI parties and the Partner Agreement Manager.</span></span>  
  
## <a name="a-cache-refresh-period-delays-availability-of-a-changed-party-property"></a><span data-ttu-id="d1340-104">変更されたパーティ プロパティのキャッシュの更新期間の遅延可用性</span><span class="sxs-lookup"><span data-stu-id="d1340-104">A Cache Refresh Period Delays Availability of a Changed Party Property</span></span>  
 <span data-ttu-id="d1340-105">パーティまたは PAM でグローバル プロパティを変更すると、プロパティにキャッシュが 15 分ごとに更新した後、BizTalk Runtime または BizTalk サービスの再起動後に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d1340-105">If you change a party or global property in PAM, the properties will be available to the BizTalk Runtime after the cache refreshes every fifteen minutes or after a restart of the BizTalk Service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1340-106">参照</span><span class="sxs-lookup"><span data-stu-id="d1340-106">See Also</span></span>  
 <span data-ttu-id="d1340-107">[EDI 受信確認の構成](../core/configuring-edi-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="d1340-107">[Configuring EDI Acknowledgments](../core/configuring-edi-acknowledgments.md) </span></span>  
 <span data-ttu-id="d1340-108">[EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="d1340-108">[The Role of Agreements in EDI Processing](../core/the-role-of-agreements-in-edi-processing.md) </span></span>  
 <span data-ttu-id="d1340-109">[EDI のプロパティを構成します。](../core/configuring-edi-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d1340-109">[Configuring EDI Properties](../core/configuring-edi-properties.md) </span></span>  
 [<span data-ttu-id="d1340-110">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="d1340-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)