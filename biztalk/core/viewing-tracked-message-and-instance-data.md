---
title: 追跡メッセージおよびインスタンス データの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, HAT
- HAT, about HAT
ms.assetid: e3cc7bef-90c7-4375-9f6c-7df00391132e
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18e08e4f7aa98941dcd859557661d2e5883c76ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253586"
---
# <a name="viewing-tracked-message-and-instance-data"></a><span data-ttu-id="84e05-102">追跡メッセージを表示し、インスタンス データ</span><span class="sxs-lookup"><span data-stu-id="84e05-102">Viewing Tracked Message and Instance Data</span></span>
<span data-ttu-id="84e05-103">履歴および追跡データを使用して、BizTalk Server アプリケーションのトラブルシューティングに役立つことができます。</span><span class="sxs-lookup"><span data-stu-id="84e05-103">You can use historical and tracked data to help troubleshoot your BizTalk Server applications.</span></span> <span data-ttu-id="84e05-104">たとえば、システム管理者は、履歴および追跡データを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84e05-104">For example, system administrators can use historical and tracked data to:</span></span>  
  
-   <span data-ttu-id="84e05-105">メッセージのフローのさまざまな段階では、追跡メッセージ イベント、メッセージ プロパティ、およびメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="84e05-105">View tracked message events, message properties, and message bodies at various stages in a message’s flow.</span></span> <span data-ttu-id="84e05-106">このデータは、トラブルシューティングまたは監査のために使用できます。</span><span class="sxs-lookup"><span data-stu-id="84e05-106">This data can be used for troubleshooting or auditing purposes.</span></span>  
  
-   <span data-ttu-id="84e05-107">特定のオーケストレーション インスタンスの実行を再生します。</span><span class="sxs-lookup"><span data-stu-id="84e05-107">Replay the execution of a specific orchestration instance.</span></span>  
  
-   <span data-ttu-id="84e05-108">時間で、後でイベントのシーケンスを再構築にイベントを発生させたルールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="84e05-108">Track rule firing events to reconstruct the sequence of events at a later point in time.</span></span>  
  
-   <span data-ttu-id="84e05-109">メッセージ スキーマやメッセージ プロパティと値のペアなどの条件を指定してメッセージを照会します。</span><span class="sxs-lookup"><span data-stu-id="84e05-109">Query for messages by specifying criteria such as message schema and message property/value pairs.</span></span> <span data-ttu-id="84e05-110">メッセージ置いているため、ユーザーは、メッセージが進んだ先のメッセージ フロー内の位置を判断できます。</span><span class="sxs-lookup"><span data-stu-id="84e05-110">Having thus located the message, users can determine the point in the message flow to which the message has progressed.</span></span> <span data-ttu-id="84e05-111">高度なユーザーには、メッセージのカスタムの SQL Server クエリも作成できます。</span><span class="sxs-lookup"><span data-stu-id="84e05-111">Advanced users can also create custom SQL Server queries for messages.</span></span>  
  
-   <span data-ttu-id="84e05-112">アーカイブ済みのデータベースにアーカイブされたデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="84e05-112">Search for archived data in an archived database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84e05-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="84e05-113">In This Section</span></span>  
  
-   [<span data-ttu-id="84e05-114">チェックリスト:メッセージとインスタンス データ追跡</span><span class="sxs-lookup"><span data-stu-id="84e05-114">Checklist: Message and Instance Data Tracking</span></span>](../core/checklist-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="84e05-115">メッセージとインスタンス データ追跡のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="84e05-115">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="84e05-116">メッセージとインスタンス データの追跡のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="84e05-116">Security Considerations for Message and Instance Data Tracking</span></span>](../core/security-considerations-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="84e05-117">追跡データについて</span><span class="sxs-lookup"><span data-stu-id="84e05-117">Understanding Tracked Data</span></span>](../core/understanding-tracked-data.md)  
  
-   [<span data-ttu-id="84e05-118">履歴および追跡データの表示</span><span class="sxs-lookup"><span data-stu-id="84e05-118">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)  
  
-   [<span data-ttu-id="84e05-119">ライブまたはアーカイブ済みのデータ ソースを選択する方法</span><span class="sxs-lookup"><span data-stu-id="84e05-119">How to Select a Live or Archived Data Source</span></span>](../core/how-to-select-a-live-or-archived-data-source.md)  
  
-   [<span data-ttu-id="84e05-120">追跡 QueryTimeout 値を変更する方法</span><span class="sxs-lookup"><span data-stu-id="84e05-120">How to Change the Tracking QueryTimeout Value</span></span>](../core/how-to-change-the-tracking-querytimeout-value.md)  
  
-   [<span data-ttu-id="84e05-121">追跡クエリを保存する方法</span><span class="sxs-lookup"><span data-stu-id="84e05-121">How to Save a Tracking Query</span></span>](../core/how-to-save-a-tracking-query.md)  
  
-   [<span data-ttu-id="84e05-122">保存されている追跡クエリを開く方法</span><span class="sxs-lookup"><span data-stu-id="84e05-122">How to Open a Saved Tracking Query</span></span>](../core/how-to-open-a-saved-tracking-query.md)  
  
-   [<span data-ttu-id="84e05-123">メッセージ フローの表示</span><span class="sxs-lookup"><span data-stu-id="84e05-123">Viewing Message Flow</span></span>](../core/viewing-message-flow.md)  
  
-   [<span data-ttu-id="84e05-124">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="84e05-124">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)  
  
-   [<span data-ttu-id="84e05-125">結果一覧を使用した作業</span><span class="sxs-lookup"><span data-stu-id="84e05-125">Working with the Results List</span></span>](../core/working-with-the-results-list.md)