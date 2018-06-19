---
title: イベント ソース ビューについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, Source Event view
- Source Event view [Tracking Profile Editor]
- message schemas, Tracking Profile Editor
- orchestrations, Tracking Profile Editor
- Tracking Profile Editor, message schemas
- Tracking Profile Editor, orchestrations
ms.assetid: 72e74780-8590-484b-899d-cdc3d2a908be
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2437d2effe2fa03078e7f92fdb06f378c9e7cac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289482"
---
# <a name="what-is-the-source-event-view"></a><span data-ttu-id="8e72f-103">イベント ソース ビューについて</span><span class="sxs-lookup"><span data-stu-id="8e72f-103">What Is the Source Event View?</span></span>
<span data-ttu-id="8e72f-104">追跡プロファイル エディター (TPE) では、イベント ソース ビューを使用して、アセンブリから選択したオーケストレーションやメッセージ スキーマを表示したり、アクティビティ定義にマップするコンテキスト プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e72f-104">The Event Source View is where the Tracking Profile Editor (TPE) presents the orchestrations or message schemas selected from the assemblies or the context properties which you map to the activity definition.</span></span>  
  
 <span data-ttu-id="8e72f-105">イベント ソース ビューはユーザー インターフェイスの右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-105">The Source Event View is presented in the right pane of user interface.</span></span> <span data-ttu-id="8e72f-106">ペインの表示内容は、選択したデータ ソースによって変わります。</span><span class="sxs-lookup"><span data-stu-id="8e72f-106">The contents of the pane vary based on the data source you selected.</span></span>  
  
## <a name="event-source-options"></a><span data-ttu-id="8e72f-107">イベント ソースのオプション</span><span class="sxs-lookup"><span data-stu-id="8e72f-107">Event source options</span></span>  
 <span data-ttu-id="8e72f-108">イベント ソースの 4 つのオプションがある: オーケストレーション スケジュール、メッセージング ペイロード、コンテキスト プロパティ、およびメッセージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8e72f-108">You have four options for event sources: orchestration schedules, messaging payloads, context properties, and messaging properties.</span></span>  
  
 <span data-ttu-id="8e72f-109">オーケストレーションとメッセージング ペイロードを使用するには、データ項目のマップ元になるアセンブリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e72f-109">Orchestrations and messaging payloads require that you select an assembly from which to map your data items.</span></span> <span data-ttu-id="8e72f-110">その後で、アセンブリから特定のオーケストレーションまたはメッセージ ペイロード スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e72f-110">You then select the specific orchestrations or message payload schemas of interest from the assembly.</span></span> <span data-ttu-id="8e72f-111">オーケストレーション スケジュールを使用するときは、アセンブリ内のオーケストレーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-111">For orchestration schedules you are given a list of the orchestrations in the assembly.</span></span> <span data-ttu-id="8e72f-112">メッセージング ペイロードは、メッセージング ペイロード スキーマの一覧から選択できます。コンテキスト プロパティを選択するときは、アセンブリ内のスキーマと、すべてのユーザーに公開されているシステム スキーマの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-112">Messaging payloads allow you to select from a list of messaging payload schemas, and context properties present a list of schemas in the assembly and in system schemas that are publicly available.</span></span>  
  
 <span data-ttu-id="8e72f-113">コンテキスト プロパティを選択すると、まずコンテキスト プロパティの名前の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-113">When you select context properties, you are first given a list of context property names.</span></span> <span data-ttu-id="8e72f-114">その中から 1 つを選択すると、そのコンテキスト プロパティに関連するスキーマが右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-114">When you select the context property, the related schema of the context property is shown in the right pane.</span></span> <span data-ttu-id="8e72f-115">コンテキスト プロパティをアクティビティ ノードにドラッグ アンド ドロップすることで、両者をマップできます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-115">You can then map the context property to your activity by dragging and dropping the property onto an activity node.</span></span>  
  
 <span data-ttu-id="8e72f-116">メッセージング プロパティを選択するときは、アクティビティにマップできる既知のメッセージ プロパティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e72f-116">When you select messaging properties you are given a list of the known messaging properties that you can then map to the activity.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e72f-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8e72f-117">In This Section</span></span>  
  
-   [<span data-ttu-id="8e72f-118">オーケストレーション スケジュール ビュー</span><span class="sxs-lookup"><span data-stu-id="8e72f-118">Orchestration Schedule View</span></span>](../core/orchestration-schedule-view.md)  
  
-   [<span data-ttu-id="8e72f-119">メッセージング ペイロード ビュー</span><span class="sxs-lookup"><span data-stu-id="8e72f-119">Messaging Payload View</span></span>](../core/messaging-payload-view.md)  
  
-   [<span data-ttu-id="8e72f-120">コンテキスト プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="8e72f-120">Context Property View</span></span>](../core/context-property-view.md)  
  
-   [<span data-ttu-id="8e72f-121">メッセージング プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="8e72f-121">Messaging Property View</span></span>](../core/messaging-property-view.md)