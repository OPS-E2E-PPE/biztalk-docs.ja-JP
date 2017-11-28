---
title: "イベント ソースにマップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 588a394fb3404872554fc786efa3fe24fdd9b47a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-event-sources"></a><span data-ttu-id="d399d-102">イベント ソースをマップする方法</span><span class="sxs-lookup"><span data-stu-id="d399d-102">How to Map Event Sources</span></span>
<span data-ttu-id="d399d-103">イベント ソースをマップすると、BAM による追跡と警告の対象となるデータ項目へのアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="d399d-103">You map event sources to gain access to data items that BAM tracks to generate alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d399d-104">データ項目は、オーケストレーション スケジュール、メッセージ ペイロード、コンテキスト プロパティ、メッセージング プロパティという 4 種類のイベント ソースからマップできます。</span><span class="sxs-lookup"><span data-stu-id="d399d-104">You can map data items from four different event source types: orchestration schedules, message payloads, context properties, or messaging properties.</span></span> <span data-ttu-id="d399d-105">このトピックの手順では、オーケストレーション スケジュールからデータ項目をマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d399d-105">The procedure in this topic outlines mapping data items from an orchestration schedule.</span></span>  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a><span data-ttu-id="d399d-106">オーケストレーション スケジュールをイベント ソースとしてマップするには</span><span class="sxs-lookup"><span data-stu-id="d399d-106">To map an orchestration schedule as an event source</span></span>  
  
1.  <span data-ttu-id="d399d-107">既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d399d-107">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="d399d-108">追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。</span><span class="sxs-lookup"><span data-stu-id="d399d-108">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="d399d-109">クリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のペインの上にある) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d399d-109">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="d399d-110">選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="d399d-110">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="d399d-111">オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**ボックスの一覧し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="d399d-111">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
     <span data-ttu-id="d399d-112">![親アセンブリを TPE 内のイベント ソースとして選択](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span><span class="sxs-lookup"><span data-stu-id="d399d-112">![Select Parent Assembly as event Source in the TPE](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span></span>  
  
5.  <span data-ttu-id="d399d-113">データ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**ボックスの一覧し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d399d-113">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d399d-114">右ペインでデータ項目を選択し、左ペインにあるアクティビティの適切なノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d399d-114">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d399d-115">参照</span><span class="sxs-lookup"><span data-stu-id="d399d-115">See Also</span></span>  
 <span data-ttu-id="d399d-116">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="d399d-116">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="d399d-117">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d399d-117">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)