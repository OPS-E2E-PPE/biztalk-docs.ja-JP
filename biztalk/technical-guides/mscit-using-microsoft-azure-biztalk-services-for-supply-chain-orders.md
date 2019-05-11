---
title: MSCIT:サプライ チェーン発注の Microsoft Azure BizTalk Services を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22091261-cd17-45b2-8746-dc174b52dcff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 256c486b24736c46da9542508fe672076d1bd969
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320706"
---
# <a name="mscit-using-microsoft-azure-biztalk-services-for-supply-chain-orders"></a><span data-ttu-id="f7483-102">MSCIT:サプライ チェーン発注用 Microsoft Azure BizTalk Services を使用</span><span class="sxs-lookup"><span data-stu-id="f7483-102">MSCIT: Using Microsoft Azure BizTalk Services for Supply Chain Orders</span></span>
<span data-ttu-id="f7483-103">**Microsoft のデバイスとスタジオ:サプライ チェーン発注用 Microsoft Azure BizTalk Services を使用**</span><span class="sxs-lookup"><span data-stu-id="f7483-103">**Microsoft Devices & Studios: Using Microsoft Azure BizTalk Services for Supply Chain Orders**</span></span>  
  
 <span data-ttu-id="f7483-104">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="f7483-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="f7483-105">**ライター:** Anil Kongari (マイクロソフト)、Dipti Sharma (マイクロソフト)、Mandi Ohlinger (マイクロソフト)</span><span class="sxs-lookup"><span data-stu-id="f7483-105">**Writer:** Anil Kongari (Microsoft), Dipti Sharma (Microsoft), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="f7483-106">**技術校閲者:** Anil Kongari (マイクロソフト)、Hariharan Sundaram (マイクロソフト)、Dipti Sharma (マイクロソフト)、Heena Parmar (マイクロソフト)</span><span class="sxs-lookup"><span data-stu-id="f7483-106">**Technical Reviewers:** Anil Kongari (Microsoft), Hariharan Sundaram (Microsoft), Dipti Sharma (Microsoft), Heena Parmar (Microsoft)</span></span>  
  
 <span data-ttu-id="f7483-107">**公開日。** 2013 年 10 月</span><span class="sxs-lookup"><span data-stu-id="f7483-107">**Published:** October 2013</span></span>  
  
 <span data-ttu-id="f7483-108">**適用対象します。** Microsoft Azure BizTalk Services (MABS) および BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7483-108">**Applies To:** Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013</span></span>  
  
 <span data-ttu-id="f7483-109">**概要:** 製造、サプライ チェーン、および情報サービス (MSCIS) グループは、microsoft Global Supply Chain Management グループです。</span><span class="sxs-lookup"><span data-stu-id="f7483-109">**Summary:** The Manufacturing, Supply Chain, and Information Services (MSCIS) group is a Global Supply Chain Management group at Microsoft.</span></span> <span data-ttu-id="f7483-110">毎年、マイクロソフトは、新製品を起動します。</span><span class="sxs-lookup"><span data-stu-id="f7483-110">Every year, Microsoft launches new products.</span></span> <span data-ttu-id="f7483-111">MSCIS はこれらの新しい製品を市場に持参します。</span><span class="sxs-lookup"><span data-stu-id="f7483-111">MSCIS is responsible for bringing these new products to market.</span></span> <span data-ttu-id="f7483-112">これらの製品をサポートするためには、新しいパートナーが含む業者、製造元、ディストリビューター、小売業者、サービス センター、通信事業者、サプライ チェーンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f7483-112">To support these products, new partners are added to the Supply Chain, including Supplier, Manufacturer, Distributor, Retailer, Service Center, Carrier, and so on.</span></span>  
  
 <span data-ttu-id="f7483-113">パートナーのトランザクションの数は毎年増加します。</span><span class="sxs-lookup"><span data-stu-id="f7483-113">The number of partner transactions increases yearly.</span></span> <span data-ttu-id="f7483-114">高負荷時に、スループットに関連する問題があります。</span><span class="sxs-lookup"><span data-stu-id="f7483-114">During high load, there are issues related to throughput.</span></span> <span data-ttu-id="f7483-115">指定のチェーン BizTalk ハブより多くのトランザクション (量の増加) を処理するときに、エンド システムまたはパートナーのシステム続けることができます。</span><span class="sxs-lookup"><span data-stu-id="f7483-115">While the Supply Chain BizTalk hub processes more transactions (increased volume), the end system or partner system is not able to keep up.</span></span>  
  
 <span data-ttu-id="f7483-116">現在の課題は、ピーク セールスの企業間取引 (B2B) のシステムを準備します。</span><span class="sxs-lookup"><span data-stu-id="f7483-116">The current challenge is to prepare the business-to-business (B2B) systems for peak sales.</span></span> <span data-ttu-id="f7483-117">Technology Adoption Program (TAP) のパーツとして MSCIS は、Microsoft Azure BizTalk Services (MABS) を使用してサービス (PaaS) として、プラットフォームを検討します。</span><span class="sxs-lookup"><span data-stu-id="f7483-117">As part of Technology Adoption Program (TAP), MSCIS is exploring Platform as a Service (PaaS) using Microsoft Azure BizTalk Services (MABS).</span></span> <span data-ttu-id="f7483-118">MABS では、スケール状況を解決する主な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7483-118">MABS provides key capabilities that can solve the scale situation.</span></span> <span data-ttu-id="f7483-119">MSCIS、概念実証 (POC) に関する Microsoft Azure BizTalk Services (MABS) および BizTalk Server 2013 を使用するハイブリッド ソリューションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f7483-119">MSCIS created a Proof of Concept (POC) involving a hybrid solution that uses Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span> <span data-ttu-id="f7483-120">エンド ツー エンド、通常の売上をピーク セールスにスケールし、スケールする機能を含むから完璧な実行を提供することが要件です。</span><span class="sxs-lookup"><span data-stu-id="f7483-120">The requirement is to provide flawless execution from end-to-end, including the ability to scale up for peak sales and scale down for normal sales.</span></span>  
  
 <span data-ttu-id="f7483-121">このホワイト ペーパーでは、Microsoft Azure BizTalk Services (MABS) および BizTalk Server 2013 を使用してテスト ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7483-121">This white paper discusses the solutions tested using Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span>  
  
 <span data-ttu-id="f7483-122">ドキュメントを確認するには、ダウンロード、[チェーン注文の入力の Microsoft Azure BizTalk Services を使用して](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx)Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="f7483-122">To review the document, please download the [Using Microsoft Azure BizTalk Services for Supply Chain Orders](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx) Word document.</span></span>