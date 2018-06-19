---
title: 'MSIT: 現実の世界移行ストーリー Gentran 5.1 から BizTalk 2010 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31326e2f-fb86-4b2c-88cd-b9406695038b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b742777c5e547078c2fa3fbf1a8d5bd8c466924
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22298914"
---
# <a name="msit-real-world-migration-story-from-gentran-51-to-biztalk-2010"></a><span data-ttu-id="6f106-102">MSIT: 現実の世界移行ストーリー Gentran 5.1 から BizTalk 2010</span><span class="sxs-lookup"><span data-stu-id="6f106-102">MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010</span></span>
<span data-ttu-id="6f106-103">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="6f106-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="6f106-104">**MSIT: Gentran 5.1 から BizTalk 2010 への実際の移行事例**</span><span class="sxs-lookup"><span data-stu-id="6f106-104">**MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010**</span></span>  
  
 <span data-ttu-id="6f106-105">**作成者:** Amit Kumar Dua、Microsoft &#124; Banupriya Thirumaran、Microsoft</span><span class="sxs-lookup"><span data-stu-id="6f106-105">**Author:** Amit Kumar Dua, Microsoft  &#124;  Banupriya Thirumaran, Microsoft</span></span>  
  
 <span data-ttu-id="6f106-106">**校閲者:** Mandi Ohlinger、Microsoft &#124; Nitin Mehrotra、Microsoft</span><span class="sxs-lookup"><span data-stu-id="6f106-106">**Reviewed By:** Mandi Ohlinger, Microsoft  &#124;  Nitin Mehrotra, Microsoft</span></span>  
  
 <span data-ttu-id="6f106-107">**寄稿者:** Nikhil Tayal、Microsoft &#124; Anil チャンドラ Lingam、Microsoft</span><span class="sxs-lookup"><span data-stu-id="6f106-107">**Contributors:** Nikhil Tayal, Microsoft  &#124;  Anil Chandra Lingam, Microsoft</span></span>  
  
 <span data-ttu-id="6f106-108">**公開:** 2014 年 10 月</span><span class="sxs-lookup"><span data-stu-id="6f106-108">**Published:** October 2014</span></span>  
  
 <span data-ttu-id="6f106-109">**適用対象:** BizTalk Server 2010、Gentran サーバー</span><span class="sxs-lookup"><span data-stu-id="6f106-109">**Applies To:** BizTalk Server 2010, Gentran Server</span></span>  
  
 <span data-ttu-id="6f106-110">**概要:** Microsoft IT (MSIT) 統合プラットフォームは、BizTalk Server と Gentran を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f106-110">**Summary:** The Microsoft IT (MSIT) integration platform uses BizTalk Server and Gentran.</span></span> <span data-ttu-id="6f106-111">最近まで、Microsoft IT Gentran フット プリントの適切な支持されていました。</span><span class="sxs-lookup"><span data-stu-id="6f106-111">Until recently, Microsoft IT had a good presence of Gentran footprints.</span></span> <span data-ttu-id="6f106-112">クラウド コンピューティングと AS2 と EDI 機能をサポートする BizTalk Server、Microsoft BizTalk Server 2010 と Gentran を置換する機会が存在します。</span><span class="sxs-lookup"><span data-stu-id="6f106-112">With BizTalk Server supporting cloud computing and AS2/EDI capabilities, there is an opportunity to replace Gentran with Microsoft BizTalk Server 2010.</span></span>  <span data-ttu-id="6f106-113">Windows Server 2003 および SQL server 2005; Gentran をサポートしています拡張のサポートがすぐに終了することであります。</span><span class="sxs-lookup"><span data-stu-id="6f106-113">Gentran supports Windows Server 2003 and SQL server 2005; which are in extended support that is soon ending.</span></span> <span data-ttu-id="6f106-114">Windows Server 2008/2012 および 2014/SQL Server 2008 を含む、新しいプラットフォームをサポートするために Gentran のロードマップではありません。</span><span class="sxs-lookup"><span data-stu-id="6f106-114">There is no roadmap for Gentran to support newer platforms, including Windows Server 2008/2012 and SQL Server 2008/2014.</span></span>  
  
 <span data-ttu-id="6f106-115">MSIT は、これをする機会として表示。</span><span class="sxs-lookup"><span data-stu-id="6f106-115">MSIT viewed this as an opportunity to:</span></span>  
  
-   <span data-ttu-id="6f106-116">新しいテクノロジ プラットフォームへの取得します。</span><span class="sxs-lookup"><span data-stu-id="6f106-116">Get to the newer technology platforms</span></span>  
  
-   <span data-ttu-id="6f106-117">サポートの制約を削除します。</span><span class="sxs-lookup"><span data-stu-id="6f106-117">Remove the supportability constraints</span></span>  
  
-   <span data-ttu-id="6f106-118">統合プラットフォームの全体的なアーキテクチャを簡素化します。</span><span class="sxs-lookup"><span data-stu-id="6f106-118">Simplify the overall architecture of the integration platform</span></span>  
  
-   <span data-ttu-id="6f106-119">コスト効果の高い、堅牢な統合プラットフォームを行う</span><span class="sxs-lookup"><span data-stu-id="6f106-119">Make the integration platform more cost effective and robust</span></span>  
  
 <span data-ttu-id="6f106-120">BizTalk Server 2010 は、実証済みの統合プラットフォームはの多数の機能と機能、および新しいプラットフォーム テクノロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6f106-120">BizTalk Server 2010 is a proven integration platform, has numerous capabilities and features, and supports the new platform technologies.</span></span>  
  
 <span data-ttu-id="6f106-121">このホワイト ペーパーでは、戦略と Gentran 5.1 から BizTalk Server に移行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f106-121">This white paper discusses the strategy and steps taken to migrate from Gentran 5.1 to BizTalk Server.</span></span>  
  
 <span data-ttu-id="6f106-122">ダウンロード ドキュメントを参照してください、 [MSIT: Gentran 5.1 から BizTalk 2010 に実際の世界移行状況](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx)Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="6f106-122">To review the document, please download the [MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word document.</span></span>