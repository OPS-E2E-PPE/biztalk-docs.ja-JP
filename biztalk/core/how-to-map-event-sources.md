---
title: イベント ソースにマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, alerts
- orchestrations, schedules
- events, mapping sources
- orchestrations, tracking profiles
- events, orchestration schedules
- tracking profiles, orchestrations
- tracking profiles, alerts
- alerts, tracking profiles
- alerts, BAM
- tracking profiles, mapping event sources
- events, tracking profiles
ms.assetid: 507f1624-2cd8-4960-8c63-7797ab22519e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56f9d85d0ac3509eb954f6c2d50496ce5979769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336632"
---
# <a name="how-to-map-event-sources"></a><span data-ttu-id="32e45-102">イベント ソースをマップする方法</span><span class="sxs-lookup"><span data-stu-id="32e45-102">How to Map Event Sources</span></span>
<span data-ttu-id="32e45-103">BAM は、アラートを生成する追跡データ項目にアクセスするイベント ソースをマップします。</span><span class="sxs-lookup"><span data-stu-id="32e45-103">You map event sources to gain access to data items that BAM tracks to generate alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32e45-104">4 つの異なるイベント ソースの種類からのデータ項目にマップすることができます。 オーケストレーション スケジュール、メッセージ ペイロード、コンテキスト プロパティ、またはメッセージ プロパティ。</span><span class="sxs-lookup"><span data-stu-id="32e45-104">You can map data items from four different event source types: orchestration schedules, message payloads, context properties, or messaging properties.</span></span> <span data-ttu-id="32e45-105">このトピックの手順では、オーケストレーション スケジュールからデータ項目のマッピングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="32e45-105">The procedure in this topic outlines mapping data items from an orchestration schedule.</span></span>  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a><span data-ttu-id="32e45-106">イベント ソースとして、オーケストレーション スケジュールをマップするには</span><span class="sxs-lookup"><span data-stu-id="32e45-106">To map an orchestration schedule as an event source</span></span>  
  
1.  <span data-ttu-id="32e45-107">既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="32e45-107">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="32e45-108">追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。</span><span class="sxs-lookup"><span data-stu-id="32e45-108">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="32e45-109">をクリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のウィンドウの上にある) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="32e45-109">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="32e45-110">選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="32e45-110">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="32e45-111">オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**、ボックスの一覧をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="32e45-111">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
     <span data-ttu-id="32e45-112">![TPE 内のイベント ソースとして親アセンブリの選択](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span><span class="sxs-lookup"><span data-stu-id="32e45-112">![Select Parent Assembly as event Source in the TPE](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span></span>  
  
5.  <span data-ttu-id="32e45-113">内のデータ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**、ボックスの一覧をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32e45-113">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="32e45-114">右側のペインで、データ項目を選択し、左側のウィンドウで、アクティビティ内の適切なノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="32e45-114">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e45-115">参照</span><span class="sxs-lookup"><span data-stu-id="32e45-115">See Also</span></span>  
 <span data-ttu-id="32e45-116">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="32e45-116">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="32e45-117">追跡プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="32e45-117">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)