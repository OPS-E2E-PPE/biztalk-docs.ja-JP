---
title: "MSCIT: サプライ チェーン発注の Microsoft Azure BizTalk サービスを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22091261-cd17-45b2-8746-dc174b52dcff
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a1609be7326db4988d31d51597cde3fd280227
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mscit-using-microsoft-azure-biztalk-services-for-supply-chain-orders"></a><span data-ttu-id="6a145-102">サプライ チェーン発注の Microsoft Azure BizTalk サービスを使用して MSCIT:</span><span class="sxs-lookup"><span data-stu-id="6a145-102">MSCIT: Using Microsoft Azure BizTalk Services for Supply Chain Orders</span></span>
<span data-ttu-id="6a145-103">**Microsoft デバイス & スタジオ: サプライ チェーン発注の Microsoft Azure BizTalk サービスを使用します。**</span><span class="sxs-lookup"><span data-stu-id="6a145-103">**Microsoft Devices & Studios: Using Microsoft Azure BizTalk Services for Supply Chain Orders**</span></span>  
  
 <span data-ttu-id="6a145-104">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="6a145-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="6a145-105">**ライター:** Anil Kongari (Microsoft) Dipti Sharma (Microsoft) Mandi Ohlinger (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="6a145-105">**Writer:** Anil Kongari (Microsoft), Dipti Sharma (Microsoft), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="6a145-106">**技術レビューアー:** Anil Kongari (Microsoft)、Hariharan Sundaram (Microsoft)、Dipti Sharma (Microsoft)、Heena Parmar (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="6a145-106">**Technical Reviewers:** Anil Kongari (Microsoft), Hariharan Sundaram (Microsoft), Dipti Sharma (Microsoft), Heena Parmar (Microsoft)</span></span>  
  
 <span data-ttu-id="6a145-107">**公開:** 2013 年 10 月</span><span class="sxs-lookup"><span data-stu-id="6a145-107">**Published:** October 2013</span></span>  
  
 <span data-ttu-id="6a145-108">**適用対象:** Microsoft Azure BizTalk サービス (MABS) と BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a145-108">**Applies To:** Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013</span></span>  
  
 <span data-ttu-id="6a145-109">**概要:**製造、サプライ チェーンおよび情報サービス (MSCIS) グループは、Microsoft のグローバル サプライ チェーン マネジメント グループ。</span><span class="sxs-lookup"><span data-stu-id="6a145-109">**Summary:** The Manufacturing, Supply Chain, and Information Services (MSCIS) group is a Global Supply Chain Management group at Microsoft.</span></span> <span data-ttu-id="6a145-110">毎年、Microsoft では、新しい製品を起動します。</span><span class="sxs-lookup"><span data-stu-id="6a145-110">Every year, Microsoft launches new products.</span></span> <span data-ttu-id="6a145-111">MSCIS はこれらの新しい製品を市場に持参します。</span><span class="sxs-lookup"><span data-stu-id="6a145-111">MSCIS is responsible for bringing these new products to market.</span></span> <span data-ttu-id="6a145-112">これらの製品をサポートするために、新しいパートナーは、サプライ チェーン供給業者、製造元、ディストリビューター、小売業者、Service Center、通信事業者、およびなどを含むに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6a145-112">To support these products, new partners are added to the Supply Chain, including Supplier, Manufacturer, Distributor, Retailer, Service Center, Carrier, and so on.</span></span>  
  
 <span data-ttu-id="6a145-113">パートナーのトランザクションの数は毎年増加します。</span><span class="sxs-lookup"><span data-stu-id="6a145-113">The number of partner transactions increases yearly.</span></span> <span data-ttu-id="6a145-114">高の読み込み中、スループットに関連する問題があります。</span><span class="sxs-lookup"><span data-stu-id="6a145-114">During high load, there are issues related to throughput.</span></span> <span data-ttu-id="6a145-115">指定のチェーン BizTalk ハブより多くのトランザクション (増加したボリューム) を処理するときに、エンド システムまたはパートナーのシステム継続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6a145-115">While the Supply Chain BizTalk hub processes more transactions (increased volume), the end system or partner system is not able to keep up.</span></span>  
  
 <span data-ttu-id="6a145-116">現在の課題は、ピーク時の売上の企業間取引 (B2B) システムを準備するのにです。</span><span class="sxs-lookup"><span data-stu-id="6a145-116">The current challenge is to prepare the business-to-business (B2B) systems for peak sales.</span></span> <span data-ttu-id="6a145-117">一部として Technology Adoption Program (TAP) の MSCIS は探索、プラットフォームとして Microsoft Azure BizTalk サービス (MABS) を使用してサービス (PaaS)。</span><span class="sxs-lookup"><span data-stu-id="6a145-117">As part of Technology Adoption Program (TAP), MSCIS is exploring Platform as a Service (PaaS) using Microsoft Azure BizTalk Services (MABS).</span></span> <span data-ttu-id="6a145-118">MABS では、スケールの状況を解決できる主要な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a145-118">MABS provides key capabilities that can solve the scale situation.</span></span> <span data-ttu-id="6a145-119">MSCIS 実証の概念 (POC) 関連する Microsoft Azure BizTalk サービス (MABS) および BizTalk Server 2013 を使用するハイブリッド ソリューションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6a145-119">MSCIS created a Proof of Concept (POC) involving a hybrid solution that uses Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span> <span data-ttu-id="6a145-120">要件では、エンド ツー エンドを含むにスケール アップ ピーク sales とスケール ダウンの通常の販売から完璧な実行を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a145-120">The requirement is to provide flawless execution from end-to-end, including the ability to scale up for peak sales and scale down for normal sales.</span></span>  
  
 <span data-ttu-id="6a145-121">このホワイト ペーパーでは、Microsoft Azure BizTalk サービス (MABS) と BizTalk Server 2013 を使用してテスト ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a145-121">This white paper discusses the solutions tested using Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span>  
  
 <span data-ttu-id="6a145-122">ダウンロード ドキュメントを参照してください、[チェーン発注の指定の Microsoft Azure BizTalk サービスを使用して](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx)Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="6a145-122">To review the document, please download the [Using Microsoft Azure BizTalk Services for Supply Chain Orders](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx) Word document.</span></span>