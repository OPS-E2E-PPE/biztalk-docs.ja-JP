---
title: 変換して、ディスク フォルダー、キュー、または FTP フォルダーへのメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfed87c48e0e8dfc845163325319f77de1bc2dff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399636"
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a><span data-ttu-id="ee033-102">変換して、ディスク フォルダー、キュー、または FTP フォルダーへのメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="ee033-102">Transforming and Routing a Message to Disk Folder, Queue, or FTP Folder</span></span>
<span data-ttu-id="ee033-103">このユース ケースでは、ESB は、旅行プランの Web サービスを通じて送信された、または、ランプでメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="ee033-103">In this use case, the ESB transforms a message submitted through the Itinerary Web service or any on-ramp.</span></span> <span data-ttu-id="ee033-104">ファイルの種類の動的解決のルックアップ、FTP、またはキューの場所は、(変換) のマップの名前と、メッセージの対象のエンドポイントを図 1 に示すように決定します。</span><span class="sxs-lookup"><span data-stu-id="ee033-104">A dynamic resolution lookup of type FILE, FTP, or queue location determines the map name (for transformation) and the target endpoint for the message, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="ee033-105">![ディスクのフォルダーの変換](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3 TransformingDiskFolder")</span><span class="sxs-lookup"><span data-stu-id="ee033-105">![Transforming Disk Folder](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span></span>  
  
 <span data-ttu-id="ee033-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="ee033-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="ee033-107">**変換して、ディスク フォルダーへのメッセージのルーティング**</span><span class="sxs-lookup"><span data-stu-id="ee033-107">**Transforming and routing a message to a disk folder**</span></span>  
  
 <span data-ttu-id="ee033-108">動的解決サンプルに含まれている[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="ee033-108">The Dynamic Resolution sample included with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="ee033-109">コンポーネントを使用して動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し解決およびオーケストレーションを使用しなくても、メッセージング レベルで maps に BizTalk Server を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee033-109">It shows how to use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="ee033-110">一方向と双方向の両方のメッセージング パターンも示します。</span><span class="sxs-lookup"><span data-stu-id="ee033-110">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="ee033-111">このユース ケースの拡張機能は、ファイル、FTP、または変換の追加の手順を使用せず、キューの場所に、受信メッセージをルーティングする単純なルーティング ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ee033-111">An extension of this use case is a simple routing solution that routes an incoming message to a file, FTP, or queue location without the additional step of transformation.</span></span>  
  
 <span data-ttu-id="ee033-112">詳細については、次を参照してください。[をインストールすると、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee033-112">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>