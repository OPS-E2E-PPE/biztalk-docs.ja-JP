---
title: 管理コンソールの [クエリ] タブを使用して |Microsoft Docs
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
ms.openlocfilehash: cc28e2b9c07cc456c64c7956ab9cda2e898ba942
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321246"
---
# <a name="using-the-administration-console-query-tab"></a><span data-ttu-id="797f8-102">管理コンソールの [クエリ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="797f8-102">Using the Administration Console Query Tab</span></span>
<span data-ttu-id="797f8-103">特定の実行、中断されたサービス インスタンス、メッセージ、またはサブスクリプションを検索して、BizTalk Server 管理コンソールの [グループ ハブ] ページで、[クエリ] タブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="797f8-103">You can use the Query tab on the Group Hub page in the BizTalk Server Administration Console to search for and locate specific running and suspended service instances, messages, or subscriptions.</span></span> <span data-ttu-id="797f8-104">管理コンソールを使用して実行されるクエリは、メッセージ ボックス データベースに格納されているアクティブな項目を見つけます。</span><span class="sxs-lookup"><span data-stu-id="797f8-104">Queries performed using the Administration Console locate live items, which are stored in the MessageBox database.</span></span> <span data-ttu-id="797f8-105">新しいクエリ タブでは、新しいクエリを実行するたびに表示されます。</span><span class="sxs-lookup"><span data-stu-id="797f8-105">A new query tab appears each time you run a new query.</span></span>  
  
 <span data-ttu-id="797f8-106">追跡またはアーカイブされたメッセージやサービス インスタンスを検索するには、メッセージ イベントおよびサービス インスタンスの追跡を使用します。</span><span class="sxs-lookup"><span data-stu-id="797f8-106">To locate tracked or archived messages or service instances, you use message event and service instance tracking.</span></span> <span data-ttu-id="797f8-107">詳細については、次を参照してください。[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="797f8-107">For more information, see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="797f8-108">サービス インスタンスのクエリを実行するときに、返される結果セットの値が表示**\<名は使用できません\>** の**ServiceName**サービスのフィールドインスタンスの場合は、対応する送信ポート、受信場所、またはオーケストレーションが削除されました。</span><span class="sxs-lookup"><span data-stu-id="797f8-108">When you execute a query for service instances, the result set that is returned will display a value of **\<Name is not available\>** for the **ServiceName** field of a service instance if the corresponding send port, receive location, or orchestration has been deleted.</span></span>  <span data-ttu-id="797f8-109">**ServiceName**送信ポートのフレンドリ名の BizTalk 管理データベースにサービス インスタンスのフィールドが、参照によって設定されると、受信場所、またはオーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="797f8-109">The **ServiceName** field of a service instance is populated by a lookup into the BizTalk management database for the friendly name of the send port, receive location, or orchestration.</span></span>  <span data-ttu-id="797f8-110">場合、送信ポート、受信場所、またはオーケストレーションを削除し、フレンドリ名の参照が失敗したと**\<名は使用できません\>** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="797f8-110">If the send port, receive location, or orchestration is deleted then the lookup for the friendly name fails and **\<Name is not available\>** is displayed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="797f8-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="797f8-111">In This Section</span></span>  
  
-   [<span data-ttu-id="797f8-112">保存されたクエリを開く方法</span><span class="sxs-lookup"><span data-stu-id="797f8-112">How to Open a Saved Query</span></span>](../core/how-to-open-a-saved-query.md)  
  
-   [<span data-ttu-id="797f8-113">すべてのサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-113">How to Search for All Service Instances</span></span>](../core/how-to-search-for-all-service-instances.md)  
  
-   [<span data-ttu-id="797f8-114">実行中のサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-114">How to Search for Running Service Instances</span></span>](../core/how-to-search-for-running-service-instances.md)  
  
-   [<span data-ttu-id="797f8-115">中断されたサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-115">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)  
  
-   [<span data-ttu-id="797f8-116">メッセージを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-116">How to Search for Messages</span></span>](../core/how-to-search-for-messages.md)  
  
-   [<span data-ttu-id="797f8-117">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-117">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)  
  
-   [<span data-ttu-id="797f8-118">クエリを保存する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-118">How to Save a Query</span></span>](../core/how-to-save-a-query.md)  
  
-   [<span data-ttu-id="797f8-119">追跡メッセージ イベントを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-119">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="797f8-120">追跡サービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="797f8-120">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)