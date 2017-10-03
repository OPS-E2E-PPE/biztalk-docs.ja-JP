---
title: "MSCIT: BizTalk Server 2013 R2 の仮想化されたハブに BizTalk Server 2009 のハブからサプライ チェーンの移行 |Microsoft ドキュメント"
ms.custom: 
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7366ffc2-d1f6-44df-b1f8-f07b99cf5d11
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a3cc49424ead924bdb98dd196f7792806d2702f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mscit-supply-chain-migration-from-biztalk-server-2009-hub-to-biztalk-server-2013-r2-virtualized-hub"></a><span data-ttu-id="a2ca8-102">BizTalk Server 2013 R2 の仮想化されたハブに BizTalk Server 2009 のハブから MSCIT: サプライ チェーンの移行</span><span class="sxs-lookup"><span data-stu-id="a2ca8-102">MSCIT: Supply Chain migration from BizTalk Server 2009 hub to BizTalk Server 2013 R2 virtualized hub</span></span>
<span data-ttu-id="a2ca8-103">アプリケーションの移行は、BizTalk Server 2010 から BizTalk Server 2013 R2。</span><span class="sxs-lookup"><span data-stu-id="a2ca8-103">Application migration from BizTalk Server 2010 to BizTalk Server 2013 R2.</span></span>  
  
 <span data-ttu-id="a2ca8-104">**作成者**: Arvind Chaudhary、Microsoft & #124 です。Piyush は、Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2ca8-104">**Author**: Arvind Chaudhary, Microsoft &#124; Piyush Prasad, Microsoft</span></span>  
  
 <span data-ttu-id="a2ca8-105">**パブリッシュされた**: 2015 年 9 月</span><span class="sxs-lookup"><span data-stu-id="a2ca8-105">**Published**: September 2015</span></span>  
  
 <span data-ttu-id="a2ca8-106">**適用されます**: BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="a2ca8-106">**Applies to**: BizTalk Server 2013 R2</span></span>  
  
 <span data-ttu-id="a2ca8-107">**概要**: 理由と、アプリケーションを BizTalk Server 2009 および 2010 から BizTalk Server 2013 R2 に移行する Microsoft IT によって取得される移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ca8-107">**Summary**:  Describes the reasons and the  migration process taken by Microsoft IT to migrate applications from BizTalk Server 2009 and 2010 to BizTalk Server 2013 R2.</span></span> <span data-ttu-id="a2ca8-108">MSIT で、メッセージ ストリームを識別、Visual Studio の BizTalk プロジェクトを変換、取引パートナー管理のパーティとアグリーメント、移動、および、アプリケーションのバインドを更新します。</span><span class="sxs-lookup"><span data-stu-id="a2ca8-108">MSIT identified message streams, converted the BizTalk projects in Visual Studio, moved trading partner management parties and agreements, and updated the application bindings.</span></span>  
  
 <span data-ttu-id="a2ca8-109">MSIT が直面する課題とためのベスト プラクティスについて参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2ca8-109">You can also read about the challenges MSIT faced and the best practices used.</span></span>  
  
 <span data-ttu-id="a2ca8-110">ダウンロード、 [MSIT 移行ストーリーは、BizTalk Server 2013 R2 を BizTalk Server 2009/2010 から](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx)ホワイト ペーパー。</span><span class="sxs-lookup"><span data-stu-id="a2ca8-110">Download the [MSIT Migration story from BizTalk Server 2009/2010 to BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx) whitepaper.</span></span>