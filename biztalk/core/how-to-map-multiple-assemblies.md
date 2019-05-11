---
title: 複数のアセンブリをマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bdd70b7790599255ccd802d7f0e290df763982c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336340"
---
# <a name="how-to-map-multiple-assemblies"></a><span data-ttu-id="18841-102">複数のアセンブリをマップする方法</span><span class="sxs-lookup"><span data-stu-id="18841-102">How to Map Multiple Assemblies</span></span>
<span data-ttu-id="18841-103">BizTalk アプリケーションは、BAM アクティビティを参照するデータ項目が存在する複数のアセンブリで構成できます。</span><span class="sxs-lookup"><span data-stu-id="18841-103">BizTalk applications can consist of multiple assemblies in which the data items that a BAM activity references reside.</span></span> <span data-ttu-id="18841-104">次の手順では、追跡プロファイルを複数のアセンブリをマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="18841-104">The following procedure shows you how to map multiple assemblies to a tracking profile.</span></span>  
  
### <a name="to-map-multiple-assemblies"></a><span data-ttu-id="18841-105">複数のアセンブリをマップするには</span><span class="sxs-lookup"><span data-stu-id="18841-105">To map multiple assemblies</span></span>  
  
1.  <span data-ttu-id="18841-106">既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="18841-106">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="18841-107">追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。</span><span class="sxs-lookup"><span data-stu-id="18841-107">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="18841-108">をクリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のウィンドウの上にある) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18841-108">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="18841-109">選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="18841-109">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="18841-110">オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**、ボックスの一覧をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="18841-110">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="18841-111">内のデータ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**、ボックスの一覧をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="18841-111">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="18841-112">右側のペインで、データ項目を選択し、左側のウィンドウで、アクティビティ内の適切なノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="18841-112">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
7.  <span data-ttu-id="18841-113">手順 2 ~ 6 の他のアセンブリをマップします。</span><span class="sxs-lookup"><span data-stu-id="18841-113">Repeat steps 2 through 6 to map additional assemblies.</span></span>  
  
### <a name="to-map-the-second-assembly"></a><span data-ttu-id="18841-114">2 番目のアセンブリをマップするには</span><span class="sxs-lookup"><span data-stu-id="18841-114">To map the second assembly</span></span>  
  
1.  <span data-ttu-id="18841-115">をクリックして、**イベント ソースの選択**します。</span><span class="sxs-lookup"><span data-stu-id="18841-115">Click the **Select Event Source**.</span></span>  
  
2.  <span data-ttu-id="18841-116">選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="18841-116">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
3.  <span data-ttu-id="18841-117">元のオーケストレーションを含むアセンブリをクリックして、オーケストレーションを描画するために、[次へ] の親アセンブリの選択、**アセンブリ名**、ボックスの一覧をクリックして、 **[次へ]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18841-117">Select the next parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click the **Next** button.</span></span>  
  
4.  <span data-ttu-id="18841-118">内のデータ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**、ボックスの一覧をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="18841-118">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="18841-119">右側のペインで、データ項目を選択し、左側のウィンドウで、アクティビティ内の適切なノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="18841-119">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18841-120">参照</span><span class="sxs-lookup"><span data-stu-id="18841-120">See Also</span></span>  
 <span data-ttu-id="18841-121">[イベント ソースにマップする方法](../core/how-to-map-event-sources.md) </span><span class="sxs-lookup"><span data-stu-id="18841-121">[How to Map Event Sources](../core/how-to-map-event-sources.md) </span></span>  
 [<span data-ttu-id="18841-122">追跡プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="18841-122">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)