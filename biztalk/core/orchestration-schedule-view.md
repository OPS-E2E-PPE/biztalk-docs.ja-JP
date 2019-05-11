---
title: オーケストレーション スケジュール ビュー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration view [Tracking Profile Editor]
- orchestrations, Tracking Profile Editor
- Tracking Profile Editor, Orchestration view
- Tracking Profile Editor, orchestrations
ms.assetid: b3e0014b-000e-4f58-9f70-d331d78e487e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18eee656246069db7bfecfa3c32815628a1db256
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323047"
---
# <a name="orchestration-schedule-view"></a><span data-ttu-id="fa184-102">オーケストレーション スケジュール ビュー</span><span class="sxs-lookup"><span data-stu-id="fa184-102">Orchestration Schedule View</span></span>
<span data-ttu-id="fa184-103">オーケストレーション ビューには、選択したオーケストレーションに含まれているビジネス プロセスを BAM でトランザクション処理する手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa184-103">The Orchestration View displays the steps by which BAM transacts the business process contained within the selected orchestration.</span></span> <span data-ttu-id="fa184-104">このビューは、追跡プロファイル エディター (TPE) のユーザー インターフェイスの右ペインにあります。</span><span class="sxs-lookup"><span data-stu-id="fa184-104">The view is located on the right pane of the Tracking Profile Editor (TPE) user interface.</span></span>  
  
## <a name="working-with-the-orchestration-schedule-view"></a><span data-ttu-id="fa184-105">オーケストレーション スケジュール ビューの操作</span><span class="sxs-lookup"><span data-stu-id="fa184-105">Working with the Orchestration Schedule view</span></span>  
 <span data-ttu-id="fa184-106">クリックして、オーケストレーション ビューを選択、**イベント ソースの選択**クリックし、 **オーケストレーション スケジュール**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="fa184-106">You select your orchestration view by clicking the **Select Event Source** button and clicking the **Select Orchestration Schedule** menu item.</span></span> <span data-ttu-id="fa184-107">次に、オーケストレーションの選択元になるアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa184-107">You then choose an assembly from which to select an orchestration.</span></span> <span data-ttu-id="fa184-108">オーケストレーションを選択すると、オーケストレーションのコンストラクターまたはアクションを表すオーケストレーション図形を、そのオーケストレーションからアクティビティ ビュー内のビジネス マイルストーン フォルダーへドラッグして、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa184-108">Once you select the orchestration, you can drag orchestration shapes that represent orchestration constructs or actions from the orchestration into the business milestone folders in the activity view to do the following:</span></span>  
  
- <span data-ttu-id="fa184-109">実装レベルの低いビジネス プロセスと BAM アクティビティ間のマッピングを作成する。</span><span class="sxs-lookup"><span data-stu-id="fa184-109">Create a mapping between the low-level implementation of the business process and the BAM activity.</span></span>  
  
- <span data-ttu-id="fa184-110">関連する基になるコンストラクターまたはアクションが完了したタイミングを追跡するためのタイムスタンプを指定する。</span><span class="sxs-lookup"><span data-stu-id="fa184-110">Indicate the time stamp to track when the associated underlying construct or action has completed.</span></span>  
  
  <span data-ttu-id="fa184-111">オーケストレーション スケジュール ビュー内の図形を右クリックすると、メッセージ ペイロード、コンテキスト プロパティ、または図形に関連付けられているメッセージのプロパティを表示することができるコンテキスト メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="fa184-111">Right-clicking a shape in the orchestration schedule view opens a context menu that allows you to view any message payloads, context properties, or message properties that are associated with the shape.</span></span>  
  
  <span data-ttu-id="fa184-112">オーケストレーション ビューで表示の詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa184-112">For an explanation of the displayed in the Orchestration View, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
  <span data-ttu-id="fa184-113">使用できるオーケストレーションの一覧は広範にわたる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa184-113">The list of available orchestrations can be extensive.</span></span> <span data-ttu-id="fa184-114">検索対象のオーケストレーションの名前の一部がわかっている場合でを入力、**文字列**テキスト ボックスをクリックして、**検索**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa184-114">If you know part of the name of the orchestration for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="fa184-115">このように検索すると、入力した文字列が名前に含まれているオーケストレーションのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="fa184-115">This will select only those orchestrations that contain the partial string you have entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa184-116">参照</span><span class="sxs-lookup"><span data-stu-id="fa184-116">See Also</span></span>  
 <span data-ttu-id="fa184-117">[イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="fa184-117">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="fa184-118">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="fa184-118">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)