---
title: BizTalk Server で proactivity |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b924ddae-0e7f-4058-b308-7ea9537fb45f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d232d7dec46c4de7ebb523bfaa7543db258009d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65252944"
---
# <a name="proactivity-in-biztalk-server"></a><span data-ttu-id="acc73-102">BizTalk Server のプロアクティブ性</span><span class="sxs-lookup"><span data-stu-id="acc73-102">Proactivity in BizTalk Server</span></span>
<span data-ttu-id="acc73-103">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="acc73-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="acc73-104">**BizTalk Server のプロアクティブ性**</span><span class="sxs-lookup"><span data-stu-id="acc73-104">**Proactivity in BizTalk Server**</span></span>  
  
 <span data-ttu-id="acc73-105">**ライター:** Tord よかった Nordahl (ブーベ AS)</span><span class="sxs-lookup"><span data-stu-id="acc73-105">**Writer:** Tord Glad Nordahl (Bouvet AS)</span></span>  
  
 <span data-ttu-id="acc73-106">**技術校閲者:** Sandro Pereira (Devscope)、Steef-jan Wiggers (Motion10) Erik Thue (ブーベとして)、Alexander Thue (ブーベとして)、Saravana Kumar (BizTalk360) Mandi Ohlinger (マイクロソフト)</span><span class="sxs-lookup"><span data-stu-id="acc73-106">**Technical Reviewers:** Sandro Pereira (Devscope), Steef-Jan Wiggers (Motion10), Erik Thue (Bouvet AS), Alexander Thue (Bouvet AS), Saravana Kumar  (BizTalk360), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="acc73-107">**公開日。** 2013 年 7 月</span><span class="sxs-lookup"><span data-stu-id="acc73-107">**Published:** July 2013</span></span>  
  
 <span data-ttu-id="acc73-108">**適用対象します。** BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="acc73-108">**Applies To:** BizTalk Server</span></span>  
  
 <span data-ttu-id="acc73-109">**概要:** ホワイト ペーパーは、BizTalk Server 2004 から BizTalk Server 2013 の環境まで適用されます。</span><span class="sxs-lookup"><span data-stu-id="acc73-109">**Summary:** The white paper applies from BizTalk Server 2004 to BizTalk Server 2013 environments.</span></span>  <span data-ttu-id="acc73-110">目標は、積極的にして解決するには、または発生する前に、潜在的な問題を回避する方法のいくつかの洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="acc73-110">The goal is to provide some insight of how to be proactive and resolve, or avoid, potential problems before they occur.</span></span> <span data-ttu-id="acc73-111">BizTalk ユーザーは、アーキテクト、開発者、管理者などのすべての種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="acc73-111">It applies to all types of BizTalk users, including architects, developers, and administrators.</span></span> <span data-ttu-id="acc73-112">環境内で説明されているすべてのシナリオが発生して、このホワイト ペーパーに記載されていない一部のシナリオが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="acc73-112">Not all scenarios described may occur in your environment and some scenarios not mentioned in this white paper can occur.</span></span>  
  
 <span data-ttu-id="acc73-113">性質と BizTalk Server の重要性のため設定およびベスト プラクティスが環境によって異なることができます。ネットワーク設定、アーキテクチャの設計、バージョン、メッセージ フロー、およびリソースを含むです。</span><span class="sxs-lookup"><span data-stu-id="acc73-113">Due to the nature and importance of BizTalk Server, settings and best practices can vary by environment; including network settings, architecture design, versions, message flow, and resources.</span></span> <span data-ttu-id="acc73-114">このホワイト ペーパーでは、一般的なセットアップについて説明し、値をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="acc73-114">This white paper discussed the common setup and recommended values.</span></span>  
  
 <span data-ttu-id="acc73-115">ドキュメントを確認するには、ダウンロード、 [BizTalk Server のプロアクティブ性](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx)Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="acc73-115">To review the document, please download the [Proactivity in BizTalk Server](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx) Word document.</span></span>