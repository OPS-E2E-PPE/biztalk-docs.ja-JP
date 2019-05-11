---
title: MSCIT:BizTalk Server 2009 ハブから BizTalk Server 2013 R2 仮想化ハブへのチェーンの移行の指定 |Microsoft Docs
ms.custom: ''
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7366ffc2-d1f6-44df-b1f8-f07b99cf5d11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8973c25923ede8b1dbaa060843129f931d300c3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395815"
---
# <a name="mscit-supply-chain-migration-from-biztalk-server-2009-hub-to-biztalk-server-2013-r2-virtualized-hub"></a><span data-ttu-id="5038b-102">MSCIT:BizTalk Server 2009 ハブから BizTalk Server 2013 R2 仮想化ハブへのチェーンの移行を指定します。</span><span class="sxs-lookup"><span data-stu-id="5038b-102">MSCIT: Supply Chain migration from BizTalk Server 2009 hub to BizTalk Server 2013 R2 virtualized hub</span></span>
<span data-ttu-id="5038b-103">アプリケーションの移行は、BizTalk Server 2010 から BizTalk Server 2013 R2。</span><span class="sxs-lookup"><span data-stu-id="5038b-103">Application migration from BizTalk Server 2010 to BizTalk Server 2013 R2.</span></span>  
  
 <span data-ttu-id="5038b-104">**作成者**:Arvind Chaudhary, Microsoft &#124; Piyush、, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5038b-104">**Author**: Arvind Chaudhary, Microsoft &#124; Piyush Prasad, Microsoft</span></span>  
  
 <span data-ttu-id="5038b-105">**発行**:2015 年 9 月</span><span class="sxs-lookup"><span data-stu-id="5038b-105">**Published**: September 2015</span></span>  
  
 <span data-ttu-id="5038b-106">**適用対象**:BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="5038b-106">**Applies to**: BizTalk Server 2013 R2</span></span>  
  
 <span data-ttu-id="5038b-107">**概要**:上の理由から、アプリケーションを BizTalk Server 2009 および 2010 から BizTalk Server 2013 R2 に移行する Microsoft IT が行った移行プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5038b-107">**Summary**:  Describes the reasons and the  migration process taken by Microsoft IT to migrate applications from BizTalk Server 2009 and 2010 to BizTalk Server 2013 R2.</span></span> <span data-ttu-id="5038b-108">MSIT で、メッセージ ストリームを識別、Visual Studio で BizTalk プロジェクトを変換、取引先パートナー管理のパーティーと契約に移動、および、アプリケーションのバインドを更新します。</span><span class="sxs-lookup"><span data-stu-id="5038b-108">MSIT identified message streams, converted the BizTalk projects in Visual Studio, moved trading partner management parties and agreements, and updated the application bindings.</span></span>  
  
 <span data-ttu-id="5038b-109">MSIT 直面する課題および使用のベスト プラクティスについて読むこともできます。</span><span class="sxs-lookup"><span data-stu-id="5038b-109">You can also read about the challenges MSIT faced and the best practices used.</span></span>  
  
 <span data-ttu-id="5038b-110">ダウンロード、 [MSIT 移行ストーリーを BizTalk Server 2009/2010 から BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx)ホワイト ペーパー。</span><span class="sxs-lookup"><span data-stu-id="5038b-110">Download the [MSIT Migration story from BizTalk Server 2009/2010 to BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx) whitepaper.</span></span>