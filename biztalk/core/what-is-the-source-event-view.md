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
ms.openlocfilehash: bfc45ad952dca12acb2c325399dc318ddf7dbf50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242929"
---
# <a name="what-is-the-source-event-view"></a><span data-ttu-id="c1f27-103">イベント ソース ビューについて</span><span class="sxs-lookup"><span data-stu-id="c1f27-103">What Is the Source Event View?</span></span>
<span data-ttu-id="c1f27-104">イベント ソース ビューは、追跡プロファイル エディター (TPE) がオーケストレーションまたはアセンブリまたはアクティビティの定義にマップするコンテキスト プロパティから選択するメッセージ スキーマを表示します。</span><span class="sxs-lookup"><span data-stu-id="c1f27-104">The Event Source View is where the Tracking Profile Editor (TPE) presents the orchestrations or message schemas selected from the assemblies or the context properties which you map to the activity definition.</span></span>  
  
 <span data-ttu-id="c1f27-105">イベント ソース ビューは、ユーザー インターフェイスの右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1f27-105">The Source Event View is presented in the right pane of user interface.</span></span> <span data-ttu-id="c1f27-106">ウィンドウの内容は、選択したデータ ソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c1f27-106">The contents of the pane vary based on the data source you selected.</span></span>  
  
## <a name="event-source-options"></a><span data-ttu-id="c1f27-107">イベント ソースのオプション</span><span class="sxs-lookup"><span data-stu-id="c1f27-107">Event source options</span></span>  
 <span data-ttu-id="c1f27-108">イベント ソースの 4 つのオプションがある: オーケストレーション スケジュール、メッセージング ペイロード、コンテキスト プロパティ、およびメッセージのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c1f27-108">You have four options for event sources: orchestration schedules, messaging payloads, context properties, and messaging properties.</span></span>  
  
 <span data-ttu-id="c1f27-109">オーケストレーションとメッセージング ペイロードからのデータ項目をマップ先となるアセンブリを選択することが必要です。</span><span class="sxs-lookup"><span data-stu-id="c1f27-109">Orchestrations and messaging payloads require that you select an assembly from which to map your data items.</span></span> <span data-ttu-id="c1f27-110">アセンブリから特定のオーケストレーションまたは関心のあるメッセージ ペイロード スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1f27-110">You then select the specific orchestrations or message payload schemas of interest from the assembly.</span></span> <span data-ttu-id="c1f27-111">オーケストレーション スケジュールのアセンブリでオーケストレーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1f27-111">For orchestration schedules you are given a list of the orchestrations in the assembly.</span></span> <span data-ttu-id="c1f27-112">メッセージング ペイロードを使用すると、メッセージング ペイロードのスキーマの一覧から選択できますし、コンテキスト プロパティとパブリックに使用できるシステム スキーマ アセンブリでのスキーマの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="c1f27-112">Messaging payloads allow you to select from a list of messaging payload schemas, and context properties present a list of schemas in the assembly and in system schemas that are publicly available.</span></span>  
  
 <span data-ttu-id="c1f27-113">コンテキスト プロパティを選択するとまずコンテキスト プロパティ名の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1f27-113">When you select context properties, you are first given a list of context property names.</span></span> <span data-ttu-id="c1f27-114">コンテキスト プロパティを選択すると、右側のウィンドウで、コンテキスト プロパティに関連するスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1f27-114">When you select the context property, the related schema of the context property is shown in the right pane.</span></span> <span data-ttu-id="c1f27-115">ドラッグ アンド ドロップ アクティビティ ノードにプロパティをアクティビティにし、コンテキスト プロパティをマップできます。</span><span class="sxs-lookup"><span data-stu-id="c1f27-115">You can then map the context property to your activity by dragging and dropping the property onto an activity node.</span></span>  
  
 <span data-ttu-id="c1f27-116">メッセージのプロパティを選択すると、アクティビティにマップできますし、既知のメッセージ プロパティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1f27-116">When you select messaging properties you are given a list of the known messaging properties that you can then map to the activity.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1f27-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c1f27-117">In This Section</span></span>  
  
-   [<span data-ttu-id="c1f27-118">オーケストレーション スケジュール ビュー</span><span class="sxs-lookup"><span data-stu-id="c1f27-118">Orchestration Schedule View</span></span>](../core/orchestration-schedule-view.md)  
  
-   [<span data-ttu-id="c1f27-119">メッセージング ペイロード ビュー</span><span class="sxs-lookup"><span data-stu-id="c1f27-119">Messaging Payload View</span></span>](../core/messaging-payload-view.md)  
  
-   [<span data-ttu-id="c1f27-120">コンテキスト プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="c1f27-120">Context Property View</span></span>](../core/context-property-view.md)  
  
-   [<span data-ttu-id="c1f27-121">メッセージング プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="c1f27-121">Messaging Property View</span></span>](../core/messaging-property-view.md)