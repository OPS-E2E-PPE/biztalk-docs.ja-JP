---
title: "EDI および AS2 のパフォーマンスに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e034cf228ee92157c4b29c36660111bb1856c358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-and-as2-performance"></a><span data-ttu-id="1f19d-102">EDI および AS2 のパフォーマンスに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="1f19d-102">Known Issues with EDI and AS2 Performance</span></span>
<span data-ttu-id="1f19d-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI ソリューションおよび AS2 ソリューションのパフォーマンスに関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f19d-103">This topic describes known issues with the performance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a><span data-ttu-id="1f19d-104">EDI および AS2 状態レポートのパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1f19d-104">Performance Considerations for EDI and AS2 Status Reporting</span></span>  
 <span data-ttu-id="1f19d-105">EDI または AS2 状態レポートを有効にすると、状態レポートが実行される対象のメッセージの数によってはシステムのパフォーマンスに影響が及ぶ場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f19d-105">When you activate EDI or AS2 status reporting, the performance of your system may be affected by the number of messages that status reporting is performed for.</span></span> <span data-ttu-id="1f19d-106">EDI または AS2 の処理に "レポート用にトランザクション セット/ペイロードを格納する" プロパティを選択すると、状態レポートが実行される対象のメッセージのサイズによってはシステムのパフォーマンスに影響が及ぶことがあります。</span><span class="sxs-lookup"><span data-stu-id="1f19d-106">When you select the "Store transaction set/payload for reporting" property for either EDI or AS2 processing, the performance of your system may be affected by the size of the messages that status reporting is performed for.</span></span>  
  
 <span data-ttu-id="1f19d-107">EDI または AS2 状態レポート用に BAMPrimaryImport データベースで使用されるテーブルは、最適化されています。</span><span class="sxs-lookup"><span data-stu-id="1f19d-107">The tables used in the BAMPrimaryImport database for EDI or AS2 status reporting are optimized.</span></span> <span data-ttu-id="1f19d-108">さらに最適化を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1f19d-108">No further optimization is required.</span></span> <span data-ttu-id="1f19d-109">ただし、BAMPrimaryImport データベースに格納されているアクティビティ インスタンス データをアーカイブする時間枠を変更することで、BAM プライマリ インポート データベースのデータがアーカイブされる速度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="1f19d-109">You can, however, increase the rate at which data from the BAM primary import database is archived by changing the time window for archiving activity instance data in the BAMPrimaryImport database.</span></span> <span data-ttu-id="1f19d-110">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「プライマリ インポート データベースのデータのアーカイブ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f19d-110">For more information, see "Archiving Primary Import Database Data" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="1f19d-111">トランザクション セット/ペイロード データは、BizTalkDTADb データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1f19d-111">Transaction set/payload data is stored in the BizTalkDTADb database.</span></span> <span data-ttu-id="1f19d-112">このデータベースのパフォーマンスの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「DTA 追跡のパフォーマンス特性について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f19d-112">For more information about the performance of this database, see "Understanding DTA Tracking Performance Behavior" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="1f19d-113">システムのパフォーマンスは、システムの構成で有効に設定されている状態レポートのレベルによって影響を受けることもあります。</span><span class="sxs-lookup"><span data-stu-id="1f19d-113">Performance of your system may also be affected by the degree of status reporting enabled in the configuration of your system.</span></span> <span data-ttu-id="1f19d-114">特定の種類の状態レポートを無効にすることによってパフォーマンスを向上させることも可能です。</span><span class="sxs-lookup"><span data-stu-id="1f19d-114">You may be able to improve performance by disabling a specific type of status reporting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f19d-115">参照</span><span class="sxs-lookup"><span data-stu-id="1f19d-115">See Also</span></span>  
 [<span data-ttu-id="1f19d-116">EDI および AS2 ソリューションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1f19d-116">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)