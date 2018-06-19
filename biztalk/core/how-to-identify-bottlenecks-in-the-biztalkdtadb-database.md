---
title: BizTalkDTADb データベースのボトルネックを特定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4499bc3-d50b-4b97-b19c-93c7bcc40483
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c7463a0288733936189d3cbbb69b59b3b202419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253762"
---
# <a name="how-to-identify-bottlenecks-in-the-biztalkdtadb-database"></a><span data-ttu-id="e169f-102">BizTalkDTADb データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="e169f-102">How to Identify Bottlenecks in the BizTalkDTADb Database</span></span>
<span data-ttu-id="e169f-103">BizTalkDTADb データベースのボトルネックを特定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e169f-103">To identify bottlenecks in the BizTalkDTADb database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="e169f-104">SQL エージェント サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e169f-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2.  <span data-ttu-id="e169f-105">Archive/Purge ジョブが実行され、正常に完了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e169f-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3.  <span data-ttu-id="e169f-106">DTADb アーカイブとデータベース サイズの増加に対応できるだけの十分な空きディスク領域があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e169f-106">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>