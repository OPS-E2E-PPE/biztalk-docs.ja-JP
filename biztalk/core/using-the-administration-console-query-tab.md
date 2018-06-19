---
title: 管理コンソールの [クエリ] タブを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Query tab
- Query tab [Administration Console]
ms.assetid: 7655f0b6-9217-46c4-88e0-ca2e661ce7a6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b95a4213f4ef449aa78441a7caabc1e7f6f074
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975834"
---
# <a name="using-the-administration-console-query-tab"></a><span data-ttu-id="c9939-102">管理コンソールの [クエリ] タブの使用</span><span class="sxs-lookup"><span data-stu-id="c9939-102">Using the Administration Console Query Tab</span></span>
<span data-ttu-id="c9939-103">BizTalk Server 管理コンソールの [グループ ハブ] ページの [クエリ] タブを使用すると、実行中または中断された特定のサービス インスタンス、メッセージ、またはサブスクリプションを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c9939-103">You can use the Query tab on the Group Hub page in the BizTalk Server Administration Console to search for and locate specific running and suspended service instances, messages, or subscriptions.</span></span> <span data-ttu-id="c9939-104">管理コンソールを使用して実行したクエリでは、メッセージ ボックス データベースに格納されているアクティブな項目が検索されます。</span><span class="sxs-lookup"><span data-stu-id="c9939-104">Queries performed using the Administration Console locate live items, which are stored in the MessageBox database.</span></span> <span data-ttu-id="c9939-105">新しいクエリを実行するたびに、[新しいクエリ] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9939-105">A new query tab appears each time you run a new query.</span></span>  
  
 <span data-ttu-id="c9939-106">追跡またはアーカイブされたメッセージやサービス インスタンスを検索するには、メッセージ イベントとサービス インスタンスの追跡を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9939-106">To locate tracked or archived messages or service instances, you use message event and service instance tracking.</span></span> <span data-ttu-id="c9939-107">詳細については、次を参照してください。[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9939-107">For more information, see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9939-108">サービス インスタンスに対してクエリを実行するときに返される結果セットでの値が表示**\<名は使用できません\>** の**ServiceName**サービスのフィールドインスタンスの場合は、対応する送信ポート、受信場所、またはオーケストレーションが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c9939-108">When you execute a query for service instances, the result set that is returned will display a value of **\<Name is not available\>** for the **ServiceName** field of a service instance if the corresponding send port, receive location, or orchestration has been deleted.</span></span>  <span data-ttu-id="c9939-109">**ServiceName** BizTalk 管理データベースに送信ポートのフレンドリ名を検索することによって、サービス インスタンスのフィールドが設定されると、受信場所、またはオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="c9939-109">The **ServiceName** field of a service instance is populated by a lookup into the BizTalk management database for the friendly name of the send port, receive location, or orchestration.</span></span>  <span data-ttu-id="c9939-110">場合、送信ポート、受信場所、またはオーケストレーションを削除し、フレンドリ名の参照が失敗したと**\<名は使用できません\>** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9939-110">If the send port, receive location, or orchestration is deleted then the lookup for the friendly name fails and **\<Name is not available\>** is displayed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9939-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9939-111">In This Section</span></span>  
  
-   [<span data-ttu-id="c9939-112">保存済みのクエリを開く方法</span><span class="sxs-lookup"><span data-stu-id="c9939-112">How to Open a Saved Query</span></span>](../core/how-to-open-a-saved-query.md)  
  
-   [<span data-ttu-id="c9939-113">すべてのサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-113">How to Search for All Service Instances</span></span>](../core/how-to-search-for-all-service-instances.md)  
  
-   [<span data-ttu-id="c9939-114">実行中のサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-114">How to Search for Running Service Instances</span></span>](../core/how-to-search-for-running-service-instances.md)  
  
-   [<span data-ttu-id="c9939-115">中断されたサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-115">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)  
  
-   [<span data-ttu-id="c9939-116">メッセージを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-116">How to Search for Messages</span></span>](../core/how-to-search-for-messages.md)  
  
-   [<span data-ttu-id="c9939-117">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-117">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)  
  
-   [<span data-ttu-id="c9939-118">クエリを保存する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-118">How to Save a Query</span></span>](../core/how-to-save-a-query.md)  
  
-   [<span data-ttu-id="c9939-119">追跡メッセージ イベントを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-119">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="c9939-120">追跡サービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="c9939-120">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)