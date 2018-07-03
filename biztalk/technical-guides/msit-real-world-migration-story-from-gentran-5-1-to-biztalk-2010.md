---
title: 'MSIT: 現実の世界移行ストーリー Gentran 5.1 から BizTalk 2010 |Microsoft Docs'
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
ms.openlocfilehash: f91fbf6a76f993a75a213f2e062a6a70c0f35623
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008243"
---
# <a name="msit-real-world-migration-story-from-gentran-51-to-biztalk-2010"></a><span data-ttu-id="8ce7d-102">BizTalk 2010 へ Gentran 5.1 から MSIT: 実際の移行プロセス</span><span class="sxs-lookup"><span data-stu-id="8ce7d-102">MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010</span></span>
<span data-ttu-id="8ce7d-103">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="8ce7d-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="8ce7d-104">**MSIT: Gentran 5.1 から BizTalk 2010 への実際の移行事例**</span><span class="sxs-lookup"><span data-stu-id="8ce7d-104">**MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010**</span></span>  
  
 <span data-ttu-id="8ce7d-105">**作成者:** Amit Kumar Dua, Microsoft &#124; Banupriya Thirumaran, Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ce7d-105">**Author:** Amit Kumar Dua, Microsoft  &#124;  Banupriya Thirumaran, Microsoft</span></span>  
  
 <span data-ttu-id="8ce7d-106">**校閲者:** Mandi Ohlinger、Microsoft &#124; Nitin Mehrotra, Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ce7d-106">**Reviewed By:** Mandi Ohlinger, Microsoft  &#124;  Nitin Mehrotra, Microsoft</span></span>  
  
 <span data-ttu-id="8ce7d-107">**寄稿者:** Nikhil Tayal, Microsoft &#124; Anil チャンドラ Lingam, Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ce7d-107">**Contributors:** Nikhil Tayal, Microsoft  &#124;  Anil Chandra Lingam, Microsoft</span></span>  
  
 <span data-ttu-id="8ce7d-108">**公開日:** 2014 年 10 月</span><span class="sxs-lookup"><span data-stu-id="8ce7d-108">**Published:** October 2014</span></span>  
  
 <span data-ttu-id="8ce7d-109">**適用対象:** BizTalk Server 2010、Gentran サーバー</span><span class="sxs-lookup"><span data-stu-id="8ce7d-109">**Applies To:** BizTalk Server 2010, Gentran Server</span></span>  
  
 <span data-ttu-id="8ce7d-110">**概要:** Microsoft IT (MSIT) の統合プラットフォームは、BizTalk Server と Gentran を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-110">**Summary:** The Microsoft IT (MSIT) integration platform uses BizTalk Server and Gentran.</span></span> <span data-ttu-id="8ce7d-111">最近まで、Microsoft IT は Gentran フット プリントの適切なプレゼンスがありました。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-111">Until recently, Microsoft IT had a good presence of Gentran footprints.</span></span> <span data-ttu-id="8ce7d-112">クラウド コンピューティングおよび AS2 または EDI 機能をサポートしている BizTalk Server では、営業案件に Gentran を Microsoft BizTalk Server 2010 に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-112">With BizTalk Server supporting cloud computing and AS2/EDI capabilities, there is an opportunity to replace Gentran with Microsoft BizTalk Server 2010.</span></span>  <span data-ttu-id="8ce7d-113">Windows Server 2003 および SQL server 2005; Gentran をサポートしています延長サポートが間もなく終了することであります。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-113">Gentran supports Windows Server 2003 and SQL server 2005; which are in extended support that is soon ending.</span></span> <span data-ttu-id="8ce7d-114">Windows Server 2008/2012、2014/SQL Server 2008 などの新しいプラットフォームをサポートする Gentran のためのロードマップではありません。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-114">There is no roadmap for Gentran to support newer platforms, including Windows Server 2008/2012 and SQL Server 2008/2014.</span></span>  
  
 <span data-ttu-id="8ce7d-115">MSIT は、これをする機会と見なします。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-115">MSIT viewed this as an opportunity to:</span></span>  
  
- <span data-ttu-id="8ce7d-116">新しいテクノロジ プラットフォームに取得します。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-116">Get to the newer technology platforms</span></span>  
  
- <span data-ttu-id="8ce7d-117">サポート性制約を削除します。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-117">Remove the supportability constraints</span></span>  
  
- <span data-ttu-id="8ce7d-118">統合プラットフォームの全体的なアーキテクチャを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-118">Simplify the overall architecture of the integration platform</span></span>  
  
- <span data-ttu-id="8ce7d-119">コスト効率の高い、堅牢な統合プラットフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-119">Make the integration platform more cost effective and robust</span></span>  
  
  <span data-ttu-id="8ce7d-120">BizTalk Server 2010 は、実績のある統合プラットフォームですには、多数の機能と機能、および新しいプラットフォーム テクノロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-120">BizTalk Server 2010 is a proven integration platform, has numerous capabilities and features, and supports the new platform technologies.</span></span>  
  
  <span data-ttu-id="8ce7d-121">このホワイト ペーパーでは、戦略と Gentran 5.1 から BizTalk Server に移行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-121">This white paper discusses the strategy and steps taken to migrate from Gentran 5.1 to BizTalk Server.</span></span>  
  
  <span data-ttu-id="8ce7d-122">ドキュメントを確認するには、ダウンロード、 [MSIT: Gentran 5.1 から BizTalk 2010 に実際の世界の移行状況](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx)Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="8ce7d-122">To review the document, please download the [MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word document.</span></span>