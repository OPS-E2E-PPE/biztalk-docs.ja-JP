---
title: "ネットワークのパフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6c3985a-48b3-489b-8fe3-3b7bfd0515f9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8225bd082140ac1347bc99a91ea209f9d79a8bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-network-performance"></a><span data-ttu-id="fa042-102">ネットワーク パフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="fa042-102">Optimizing Network Performance</span></span>
<span data-ttu-id="fa042-103">BizTalk Server コンピューターが SQL Server コンピューターとは別の場所、BizTalk Server 環境で BizTalk Server によって処理される各メッセージには、ネットワーク経由で通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="fa042-103">In a BizTalk Server environment where the BizTalk Server computer is separate from the SQL Server computer, each and every message processed by BizTalk Server requires communication over the network.</span></span> <span data-ttu-id="fa042-104">この通信には、BizTalk Server コンピューターと BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、BAM データベースおよびその他のデータベース間のかなりのトラフィックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa042-104">This communication includes considerable traffic between the BizTalk Server computer and the BizTalk MessageBox database, the BizTalk Management database, the BAM databases, and other databases.</span></span> <span data-ttu-id="fa042-105">高負荷のシナリオで、この通信は大量のネットワーク トラフィックにより、ネットワーク設定が最適化されていない、十分なネットワーク インターフェイス カードがインストールされている、または十分なネットワーク帯域幅が場合は特に、ボトルネックになることができます。使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa042-105">In high-load scenarios, this communication can result in considerable network traffic and can become a bottleneck, especially when network settings have not been optimized, not enough network interface cards are installed, or insufficient network bandwidth is available.</span></span>  
  
 <span data-ttu-id="fa042-106">このセクションでは、ネットワークのパフォーマンスを向上させるための一般的な推奨事項を説明し、ネットワーク上のボトルネックの発生を軽減するために、ネットワーク スタックを最適化するために変更できるいくつかのレジストリ エントリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa042-106">This section provides some general recommendations for improving network performance and describes several registry entries that can be modified to optimize the network stack to mitigate the occurrence of bottlenecks on the network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fa042-107">このセクションの推奨事項の一部には、Windows レジストリに対する変更が必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa042-107">Some of the recommendations in this section require modifications to the Windows registry.</span></span> <span data-ttu-id="fa042-108">レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa042-108">Incorrect use of Registry Editor may cause problems requiring you to reinstall your operating system.</span></span> <span data-ttu-id="fa042-109">レジストリ エディターは、ご自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="fa042-109">Use Registry Editor at your own risk.</span></span> <span data-ttu-id="fa042-110">バックアップ、復元、およびレジストリを変更する方法の詳細については、Microsoft サポート技術情報の記事を参照してください。 [256896、"Windows のレジストリ情報上級ユーザー向けに"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729)。</span><span class="sxs-lookup"><span data-stu-id="fa042-110">For more information about how to back up, restore, and modify the registry, see the Microsoft Knowledge Base article [256896, "Windows registry information for advanced users"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa042-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fa042-111">In This Section</span></span>  
  
-   [<span data-ttu-id="fa042-112">ネットワークのパフォーマンスを向上させるための一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="fa042-112">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [<span data-ttu-id="fa042-113">ネットワーク パフォーマンスを向上するように変更する設定</span><span class="sxs-lookup"><span data-stu-id="fa042-113">Settings that can be Modified to Improve Network Performance</span></span>](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a><span data-ttu-id="fa042-114">参照</span><span class="sxs-lookup"><span data-stu-id="fa042-114">See Also</span></span>  
 [<span data-ttu-id="fa042-115">パフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="fa042-115">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)