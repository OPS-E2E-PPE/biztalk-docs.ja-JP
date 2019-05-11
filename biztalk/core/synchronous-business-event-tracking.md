---
title: 同期ビジネス イベントの追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 302c7918-bc62-46f1-a949-fbf94a7073e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a97cfac1eb2b4fa13e0f3d94867d2a4993c6ba5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321827"
---
# <a name="synchronous-business-event-tracking"></a><span data-ttu-id="fc9b4-102">同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="fc9b4-102">Synchronous Business Event Tracking</span></span>
<span data-ttu-id="fc9b4-103">BAM にイベント データを送信する最も簡単な方法は、DirectEventStream クラスのインスタンスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="fc9b4-103">The simplest way to send event data to BAM is to use an instance of the class DirectEventStream.</span></span> <span data-ttu-id="fc9b4-104">このクラスでは、アプリケーションの現在のトランザクション (存在する場合) のコンテキストで、BAM プライマリ インポート データベースにイベント データを直接保存します。</span><span class="sxs-lookup"><span data-stu-id="fc9b4-104">This class saves the event data directly into the BAM Primary Import Database in the context of the current transaction of the application (if present).</span></span>  
  
 <span data-ttu-id="fc9b4-105">この操作中にエラーが発生した場合、メソッドを呼び出すと、呼び出し元のアプリケーションに例外がスローされて戻されます。</span><span class="sxs-lookup"><span data-stu-id="fc9b4-105">If any error happens during this operation, the method call will throw an exception back in the calling application.</span></span> <span data-ttu-id="fc9b4-106">たとえば、UpdateActivity に渡された項目の名前が BAM アクティビティ定義と一致しない場合、または BAM 定義をまだ展開していなかった場合に、この現象が発生します。</span><span class="sxs-lookup"><span data-stu-id="fc9b4-106">This will happen for example if the name of an item passed in UpdateActivity mismatches the BAM Activity Definition, or you did not deploy the BAM Definition yet.</span></span> <span data-ttu-id="fc9b4-107">これにより、呼び出し元のアプリケーションでは BAM データを保存するときに、すべてのエラーをキャッチして、回復できます。その結果、この BAM データを後から容易に管理できます。</span><span class="sxs-lookup"><span data-stu-id="fc9b4-107">This allows the calling application to catch and recover from any errors when saving the BAM data, which results in much easier management later.</span></span>  
  
 <span data-ttu-id="fc9b4-108">呼び出し元のアプリケーションは、BAM がすべてのストアド プロシージャやトリガーを実行するまで待機する必要があるため、データを同期的に保存することはパフォーマンスに影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc9b4-108">Saving the data synchronously might have a performance impact, because the calling application has to wait until BAM executes all stored procedures and triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc9b4-109">参照</span><span class="sxs-lookup"><span data-stu-id="fc9b4-109">See Also</span></span>  
 [<span data-ttu-id="fc9b4-110">非同期ビジネス イベントの追跡</span><span class="sxs-lookup"><span data-stu-id="fc9b4-110">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)