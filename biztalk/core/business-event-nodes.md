---
title: "ビジネス イベント ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events, Tracking Profile Editor
- events, date specific
- events, time specific
- Tracking Profile Editor, node descriptions
- Business Event nodes [Tracking Profile Editor]
- Tracking Profile Editor, events
ms.assetid: 177bc3c4-e762-42fe-80bc-edede5cd4fcd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c3d06e553f129abb36eb53c4dde9c5ab9c25f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="business-event-nodes"></a><span data-ttu-id="9306a-102">ビジネス イベント ノード</span><span class="sxs-lookup"><span data-stu-id="9306a-102">Business Event Nodes</span></span>
<span data-ttu-id="9306a-103">ビジネス イベント ノードまたはマイルストーン ノードでは、特定の日付または時刻に発生するイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="9306a-103">Business Event or milestone nodes define events that are date- or time-specific.</span></span> <span data-ttu-id="9306a-104">定義済みのビジネス イベントとマイルストーンのフォルダーは、ビジネス エンド ユーザーからインポートしたアクティビティの定義に含まれています。そのため、これらを削除するには、アクティビティ定義ファイルを再インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9306a-104">Pre-defined business event and milestone folders exist in the activity definition you import from the business end user, and you cannot delete them without reimporting the activity definition file.</span></span>  
  
## <a name="working-with-business-event-nodes"></a><span data-ttu-id="9306a-105">ビジネス イベント ノードの操作</span><span class="sxs-lookup"><span data-stu-id="9306a-105">Working with business event nodes</span></span>  
 <span data-ttu-id="9306a-106">図形をオーケストレーションから [Business Events] フォルダーにドラッグして、図形の実行完了時にイベントを追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="9306a-106">You can drag shapes from the orchestration into the Business Events folder to track those events as the execution of the shapes is completed.</span></span>  
  
 <span data-ttu-id="9306a-107">TPE では、イベント フォルダー名に図形の名前を使用し、フォルダーには一意のアイコンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9306a-107">TPE uses the name of the shape for the name of the event folder, and this folder will have a unique icon.</span></span> <span data-ttu-id="9306a-108">たとえば、ローン処理のサンプル シナリオでは、TPE によりイベント フォルダーには [承認済み] や [拒否] などイベントに応じた名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="9306a-108">For example, in the sample loan-process scenario, TPE names them according to the event, such as Approved or Denied.</span></span> <span data-ttu-id="9306a-109">あるビジネス プロセスが複数の追跡プロファイルにまたがっている場合、ビジネス イベントは 1 つのビジネス プロセスにつき 1 回だけ追跡するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9306a-109">You should only track business events once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="9306a-110">オーケストレーションに条件付きのパスが含まれている場合、イベントは 1 つしか実行されないので、両方のパスからビジネス イベントを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="9306a-110">If you have a conditional path in your orchestration, you can select the business event from both paths, as only one will ever execute.</span></span> <span data-ttu-id="9306a-111">ただし、ループ内の図形は選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="9306a-111">You should not select a shape inside a loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9306a-112">フォルダーを削除するにはアクティビティ定義を再インポートする必要がありますが、図形 (イベント) はアクティビティ定義を再インポートせずに削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9306a-112">While you cannot delete folders without reimporting the activity definition, you can delete shapes (events).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9306a-113">参照</span><span class="sxs-lookup"><span data-stu-id="9306a-113">See Also</span></span>  
 [<span data-ttu-id="9306a-114">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="9306a-114">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)