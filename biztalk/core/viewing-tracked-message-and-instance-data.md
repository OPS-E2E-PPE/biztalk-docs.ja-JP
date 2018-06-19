---
title: 追跡メッセージおよびインスタンス データの表示 |Microsoft ドキュメント
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
ms.openlocfilehash: 592fa5c85913a69f4536055cdd790d638b15bc32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288218"
---
# <a name="viewing-tracked-message-and-instance-data"></a><span data-ttu-id="557bb-102">追跡メッセージおよびインスタンス データの表示</span><span class="sxs-lookup"><span data-stu-id="557bb-102">Viewing Tracked Message and Instance Data</span></span>
<span data-ttu-id="557bb-103">履歴データおよび追跡データは、BizTalk Server アプリケーションのトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="557bb-103">You can use historical and tracked data to help troubleshoot your BizTalk Server applications.</span></span> <span data-ttu-id="557bb-104">たとえば、システム管理者は履歴データおよび追跡データを次の目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="557bb-104">For example, system administrators can use historical and tracked data to:</span></span>  
  
-   <span data-ttu-id="557bb-105">メッセージ フローのさまざまなステージで、追跡したメッセージ イベント、メッセージ プロパティ、およびメッセージ本文を参照する。</span><span class="sxs-lookup"><span data-stu-id="557bb-105">View tracked message events, message properties, and message bodies at various stages in a message’s flow.</span></span> <span data-ttu-id="557bb-106">このデータは、トラブルシューティングまたは監査のために使用できます。</span><span class="sxs-lookup"><span data-stu-id="557bb-106">This data can be used for troubleshooting or auditing purposes.</span></span>  
  
-   <span data-ttu-id="557bb-107">特定のオーケストレーション インスタンスの実行を再生する。</span><span class="sxs-lookup"><span data-stu-id="557bb-107">Replay the execution of a specific orchestration instance.</span></span>  
  
-   <span data-ttu-id="557bb-108">イベントを発生させたルールを追跡して、後でイベントのシーケンスを再構築する。</span><span class="sxs-lookup"><span data-stu-id="557bb-108">Track rule firing events to reconstruct the sequence of events at a later point in time.</span></span>  
  
-   <span data-ttu-id="557bb-109">メッセージ スキーマやメッセージ プロパティと値の組み合わせなどの条件を指定してメッセージのクエリを実行する。</span><span class="sxs-lookup"><span data-stu-id="557bb-109">Query for messages by specifying criteria such as message schema and message property/value pairs.</span></span> <span data-ttu-id="557bb-110">このようにメッセージを特定することで、ユーザーは、メッセージがメッセージ フローのどの時点まで処理されたのかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="557bb-110">Having thus located the message, users can determine the point in the message flow to which the message has progressed.</span></span> <span data-ttu-id="557bb-111">また、詳しい知識のあるユーザーは、メッセージに対して独自の SQL Server クエリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="557bb-111">Advanced users can also create custom SQL Server queries for messages.</span></span>  
  
-   <span data-ttu-id="557bb-112">アーカイブ済みデータベースに格納されているアーカイブ済みデータを検索する。</span><span class="sxs-lookup"><span data-stu-id="557bb-112">Search for archived data in an archived database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="557bb-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="557bb-113">In This Section</span></span>  
  
-   [<span data-ttu-id="557bb-114">チェックリスト: メッセージとインスタンス データの追跡</span><span class="sxs-lookup"><span data-stu-id="557bb-114">Checklist: Message and Instance Data Tracking</span></span>](../core/checklist-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="557bb-115">メッセージとインスタンス データの追跡のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="557bb-115">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="557bb-116">メッセージとインスタンス データ追跡のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="557bb-116">Security Considerations for Message and Instance Data Tracking</span></span>](../core/security-considerations-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="557bb-117">追跡データについて</span><span class="sxs-lookup"><span data-stu-id="557bb-117">Understanding Tracked Data</span></span>](../core/understanding-tracked-data.md)  
  
-   [<span data-ttu-id="557bb-118">履歴および追跡データを表示します。</span><span class="sxs-lookup"><span data-stu-id="557bb-118">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)  
  
-   [<span data-ttu-id="557bb-119">ライブまたはアーカイブ済みのデータ ソースを選択する方法</span><span class="sxs-lookup"><span data-stu-id="557bb-119">How to Select a Live or Archived Data Source</span></span>](../core/how-to-select-a-live-or-archived-data-source.md)  
  
-   [<span data-ttu-id="557bb-120">追跡 QueryTimeout 値を変更する方法</span><span class="sxs-lookup"><span data-stu-id="557bb-120">How to Change the Tracking QueryTimeout Value</span></span>](../core/how-to-change-the-tracking-querytimeout-value.md)  
  
-   [<span data-ttu-id="557bb-121">追跡クエリを保存する方法</span><span class="sxs-lookup"><span data-stu-id="557bb-121">How to Save a Tracking Query</span></span>](../core/how-to-save-a-tracking-query.md)  
  
-   [<span data-ttu-id="557bb-122">保存されている追跡クエリを開く方法</span><span class="sxs-lookup"><span data-stu-id="557bb-122">How to Open a Saved Tracking Query</span></span>](../core/how-to-open-a-saved-tracking-query.md)  
  
-   [<span data-ttu-id="557bb-123">メッセージ フローの表示</span><span class="sxs-lookup"><span data-stu-id="557bb-123">Viewing Message Flow</span></span>](../core/viewing-message-flow.md)  
  
-   [<span data-ttu-id="557bb-124">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="557bb-124">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)  
  
-   [<span data-ttu-id="557bb-125">結果リストの使用</span><span class="sxs-lookup"><span data-stu-id="557bb-125">Working with the Results List</span></span>](../core/working-with-the-results-list.md)