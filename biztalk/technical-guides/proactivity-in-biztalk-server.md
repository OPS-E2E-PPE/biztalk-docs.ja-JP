---
title: BizTalk Server で proactivity |Microsoft ドキュメント
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
ms.openlocfilehash: 4508507c0cf84141bc63df7a53eeab7c38c9f390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302106"
---
# <a name="proactivity-in-biztalk-server"></a><span data-ttu-id="10d29-102">BizTalk Server のプロアクティブ性</span><span class="sxs-lookup"><span data-stu-id="10d29-102">Proactivity in BizTalk Server</span></span>
<span data-ttu-id="10d29-103">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="10d29-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="10d29-104">**BizTalk Server のプロアクティブ性**</span><span class="sxs-lookup"><span data-stu-id="10d29-104">**Proactivity in BizTalk Server**</span></span>  
  
 <span data-ttu-id="10d29-105">**ライター:** Tord いただきありがとうございます Nordahl (ブーベ AS)</span><span class="sxs-lookup"><span data-stu-id="10d29-105">**Writer:** Tord Glad Nordahl (Bouvet AS)</span></span>  
  
 <span data-ttu-id="10d29-106">**技術レビューアー:** Sandro 現在 (Devscope)、Steef-jan Wiggers (Motion10)、Erik Thue (ブーベ AS)、Alexander Thue (ブーベ AS)、Saravana Kumar (BizTalk360)、Mandi Ohlinger (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="10d29-106">**Technical Reviewers:** Sandro Pereira (Devscope), Steef-Jan Wiggers (Motion10), Erik Thue (Bouvet AS), Alexander Thue (Bouvet AS), Saravana Kumar  (BizTalk360), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="10d29-107">**公開:** 2013 年 7 月</span><span class="sxs-lookup"><span data-stu-id="10d29-107">**Published:** July 2013</span></span>  
  
 <span data-ttu-id="10d29-108">**適用対象:** BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="10d29-108">**Applies To:** BizTalk Server</span></span>  
  
 <span data-ttu-id="10d29-109">**概要:** ホワイト ペーパーが BizTalk Server 2004 から BizTalk Server 2013 環境まで適用されます。</span><span class="sxs-lookup"><span data-stu-id="10d29-109">**Summary:** The white paper applies from BizTalk Server 2004 to BizTalk Server 2013 environments.</span></span>  <span data-ttu-id="10d29-110">目標は、および解決するには、プロアクティブなまたは発生する前に、潜在的な問題を回避する方法のいくつかの洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="10d29-110">The goal is to provide some insight of how to be proactive and resolve, or avoid, potential problems before they occur.</span></span> <span data-ttu-id="10d29-111">BizTalk ユーザーは、設計者、開発者、管理者などのすべての種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="10d29-111">It applies to all types of BizTalk users, including architects, developers, and administrators.</span></span> <span data-ttu-id="10d29-112">環境内説明されているすべてのシナリオが発生し、このホワイト ペーパーに記載いないいくつかのシナリオが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="10d29-112">Not all scenarios described may occur in your environment and some scenarios not mentioned in this white paper can occur.</span></span>  
  
 <span data-ttu-id="10d29-113">BizTalk Server の重要度と性質のための設定とベスト プラクティスによって異なる場合が環境です。ネットワーク設定、アーキテクチャの設計、バージョン、メッセージ フロー、およびリソースも含まれます。</span><span class="sxs-lookup"><span data-stu-id="10d29-113">Due to the nature and importance of BizTalk Server, settings and best practices can vary by environment; including network settings, architecture design, versions, message flow, and resources.</span></span> <span data-ttu-id="10d29-114">このホワイト ペーパーでは、共通のセットアップについて説明し、値のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10d29-114">This white paper discussed the common setup and recommended values.</span></span>  
  
 <span data-ttu-id="10d29-115">ダウンロード ドキュメントを参照してください、 [Proactivity in BizTalk Server](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx) Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="10d29-115">To review the document, please download the [Proactivity in BizTalk Server](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx) Word document.</span></span>