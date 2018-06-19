---
title: EDI パーティに関する既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: fddda6dd62e8e3bd2d38574343b7fcb0e0d76f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261786"
---
# <a name="known-issues-with-edi-parties"></a><span data-ttu-id="fdd1f-102">EDI パーティに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="fdd1f-102">Known Issues with EDI Parties</span></span>
<span data-ttu-id="fdd1f-103">このセクションには、EDI パーティと、パートナー アグリーメント マネージャに関する既知の問題を説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fdd1f-103">This section contains topics that describe known issues with EDI parties and the Partner Agreement Manager.</span></span>  
  
## <a name="a-cache-refresh-period-delays-availability-of-a-changed-party-property"></a><span data-ttu-id="fdd1f-104">キャッシュ更新間隔による変更後のパーティ プロパティの使用可能時期の遅延</span><span class="sxs-lookup"><span data-stu-id="fdd1f-104">A Cache Refresh Period Delays Availability of a Changed Party Property</span></span>  
 <span data-ttu-id="fdd1f-105">PAM でパーティまたはグローバル プロパティを変更すると、15 分ごとのキャッシュ更新または BizTalk サービスの再起動の後に、BizTalk Runtime でそのプロパティが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fdd1f-105">If you change a party or global property in PAM, the properties will be available to the BizTalk Runtime after the cache refreshes every fifteen minutes or after a restart of the BizTalk Service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd1f-106">参照</span><span class="sxs-lookup"><span data-stu-id="fdd1f-106">See Also</span></span>  
 <span data-ttu-id="fdd1f-107">[EDI 受信確認を構成します。](../core/configuring-edi-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="fdd1f-107">[Configuring EDI Acknowledgments](../core/configuring-edi-acknowledgments.md) </span></span>  
 <span data-ttu-id="fdd1f-108">[EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="fdd1f-108">[The Role of Agreements in EDI Processing](../core/the-role-of-agreements-in-edi-processing.md) </span></span>  
 <span data-ttu-id="fdd1f-109">[EDI のプロパティを構成します。](../core/configuring-edi-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fdd1f-109">[Configuring EDI Properties](../core/configuring-edi-properties.md) </span></span>  
 [<span data-ttu-id="fdd1f-110">グローバルまたはフォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="fdd1f-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)