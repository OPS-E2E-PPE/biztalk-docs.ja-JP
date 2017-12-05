---
title: "変換して、ディスクのフォルダー、キュー、または FTP フォルダーにメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcbc9d42fbed5dfd73aee910ba2e1a40da595658
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a><span data-ttu-id="8e388-102">変換して、ディスクのフォルダー、キュー、または FTP フォルダーへのメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="8e388-102">Transforming and Routing a Message to Disk Folder, Queue, or FTP Folder</span></span>
<span data-ttu-id="8e388-103">このユース ケースでは、ESB は、行程 Web サービスを通じて送信された、または、ランプでメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="8e388-103">In this use case, the ESB transforms a message submitted through the Itinerary Web service or any on-ramp.</span></span> <span data-ttu-id="8e388-104">ファイルの種類の動的解決の参照、FTP、またはキューの場所は、マップの名前 (変換) と、メッセージのターゲット エンドポイントを図 1 に示すように決定します。</span><span class="sxs-lookup"><span data-stu-id="8e388-104">A dynamic resolution lookup of type FILE, FTP, or queue location determines the map name (for transformation) and the target endpoint for the message, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="8e388-105">![ディスク フォルダーの変換](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3 TransformingDiskFolder")</span><span class="sxs-lookup"><span data-stu-id="8e388-105">![Transforming Disk Folder](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span></span>  
  
 <span data-ttu-id="8e388-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="8e388-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="8e388-107">**変換して、ディスクのフォルダーへのメッセージのルーティング**</span><span class="sxs-lookup"><span data-stu-id="8e388-107">**Transforming and routing a message to a disk folder**</span></span>  
  
 <span data-ttu-id="8e388-108">含まれる動的な解決サンプル[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="8e388-108">The Dynamic Resolution sample included with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="8e388-109">コンポーネントを使用して動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し、解決するにはおよびオーケストレーションを使用しなくてもメッセージ レベルでは、BizTalk Server マップを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e388-109">It shows how to use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="8e388-110">また、一方向と双方向の両方のメッセージング パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="8e388-110">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="8e388-111">このユース ケースの拡張機能は、単純なルーティング ソリューション ファイル、FTP、または変換の追加のステップがない場合、キューの場所に、受信メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8e388-111">An extension of this use case is a simple routing solution that routes an incoming message to a file, FTP, or queue location without the additional step of transformation.</span></span>  
  
 <span data-ttu-id="8e388-112">詳細については、次を参照してください。[をインストールすると、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="8e388-112">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>