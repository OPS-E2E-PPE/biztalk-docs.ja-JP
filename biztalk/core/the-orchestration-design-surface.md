---
title: オーケストレーション デザイン画面 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5fb190b-60d7-45e4-9883-7b3d2ed6b0c0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f943c1543cf50e4ecb1f25627cbccd7b4d72eab5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279810"
---
# <a name="the-orchestration-design-surface"></a><span data-ttu-id="4c495-102">オーケストレーション デザイン画面</span><span class="sxs-lookup"><span data-stu-id="4c495-102">The Orchestration Design Surface</span></span>
<span data-ttu-id="4c495-103">オーケストレーション デザイン画面は、BizTalk オーケストレーションの作成に使用できるビジュアル デザイナーであり、オーケストレーション デザイナーの中心的なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4c495-103">The Orchestration Design Surface is a visual designer that you can use to create a BizTalk Orchestration, and is the central component of Orchestration Designer.</span></span> <span data-ttu-id="4c495-104">このキャンバスにツールボックスから図形をドラッグした後、この図形を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4c495-104">It is a canvas that you can drag shapes onto from the Toolbox, and then configure the shapes.</span></span> <span data-ttu-id="4c495-105">Visual Studio エディター ウィンドウの 1 つとして、他の Visual Studio エディター ウィンドウと同様に、メイン ウィンドウ領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c495-105">As a Visual Studio editor window, it occupies the main window area used by other Visual Studio editor windows.</span></span>  
  
 <span data-ttu-id="4c495-106">![オーケストレーション デザイナー](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span><span class="sxs-lookup"><span data-stu-id="4c495-106">![Orchestration Designers](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span></span>  
<span data-ttu-id="4c495-107">オーケストレーション デザイン画面</span><span class="sxs-lookup"><span data-stu-id="4c495-107">Orchestration Design Surface</span></span>  
  
 <span data-ttu-id="4c495-108">オーケストレーション デザイン画面ウィンドウの上部タブと、Visual Studio ウィンドウのタイトル バーに、オーケストレーションの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c495-108">The name of the orchestration is displayed on the top tab of the Orchestration Design Surface window and in the Visual Studio window title bar.</span></span>  
  
 <span data-ttu-id="4c495-109">デザイン サーフェイス自体は 3 つの領域に分かれています。 処理領域および 2 つのポート画面です。</span><span class="sxs-lookup"><span data-stu-id="4c495-109">The design surface itself is divided into three areas: the Process Area and two Port Surfaces.</span></span> <span data-ttu-id="4c495-110">中央の処理領域には、オーケストレーションの実際のプロセス フローを表す図形が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c495-110">The central Process Area contains shapes that describe the actual process flow of the orchestration.</span></span> <span data-ttu-id="4c495-111">ポートおよびロール リンク図形だけやり取りすることが含まれているポート画面で両方の側で両側には、**送信**と**受信**プロセス領域内の図形です。</span><span class="sxs-lookup"><span data-stu-id="4c495-111">It is flanked on both sides by Port Surfaces, which contain only Port and Role Link shapes that interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="4c495-112">**プロセス領域**</span><span class="sxs-lookup"><span data-stu-id="4c495-112">**Process Area**</span></span>  
  
 <span data-ttu-id="4c495-113">処理領域は、オーケストレーション デザイナーのオーケストレーション デザイン画面の主要部分であり、常に、オーケストレーション デザイン画面の水平方向に中央揃えで表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c495-113">The Process Area is the main part of the Orchestration Design Surface of Orchestration Designer, and is always horizontally centered in the Orchestration Design Surface.</span></span>  
  
 <span data-ttu-id="4c495-114">処理領域の両側には、ポート画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c495-114">On either side of the Process Area you see Port Surfaces.</span></span> <span data-ttu-id="4c495-115">**開始**図形は、デザイン画面の上部に配置され、図形を追加すると、オーケストレーションは下方に拡大します。</span><span class="sxs-lookup"><span data-stu-id="4c495-115">The **Begin** shape is placed at the top of the design surface and the orchestration grows downward as you add shapes.</span></span>  
  
 <span data-ttu-id="4c495-116">**ポート画面**</span><span class="sxs-lookup"><span data-stu-id="4c495-116">**Port Surfaces**</span></span>  
  
 <span data-ttu-id="4c495-117">オーケストレーション デザイン画面には、処理領域の両側に 1 つずつ、合計 2 つのポート画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c495-117">Two Port Surfaces are displayed in the Orchestration Design Surface, one on either side of the Process Area.</span></span> <span data-ttu-id="4c495-118">ポート画面が 2 つの種類の図形を含めることができます:**ポート**と**ロール リンク**です。</span><span class="sxs-lookup"><span data-stu-id="4c495-118">Port Surfaces can contain two kinds of shapes: **Ports** and **Role Links**.</span></span> <span data-ttu-id="4c495-119">これらの図形との対話、**送信**と**受信**プロセス領域内の図形です。</span><span class="sxs-lookup"><span data-stu-id="4c495-119">These shapes interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="4c495-120">図形にどちらのポート画面を使用しても同じです。左右どちらのポート画面にあっても、図形の機能は変わりません。</span><span class="sxs-lookup"><span data-stu-id="4c495-120">It makes no difference which Port Surface you use for a shape; that is, the shape functions identically on either the right or the left Port Surface.</span></span> <span data-ttu-id="4c495-121">新しいポートを配置するポート画面が 2 つあることにより、作成するオーケストレーションにおけるコネクタの交差を減らすことができ、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4c495-121">Having two Port Surfaces on which to place new ports lets you create orchestrations with fewer crisscrossing connectors that therefore are easier to read.</span></span>  
  
 <span data-ttu-id="4c495-122">どちらのポート画面も、ダブルクリックするか、二重矢印アイコンをクリックして、折りたたんだり展開できます。</span><span class="sxs-lookup"><span data-stu-id="4c495-122">Both Port Surfaces can be collapsed or expanded by double-clicking on them or by clicking on the double arrow icon.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c495-123">オーケストレーション デザイナーの多くのタスクでは、スキーマやオーケストレーションなど、さまざまなアイテムを選択する必要が生じます。</span><span class="sxs-lookup"><span data-stu-id="4c495-123">Many Orchestration Designer tasks require you to select various items such as schemas or orchestrations.</span></span> <span data-ttu-id="4c495-124">こうしたアイテムが現在のプロジェクトに存在しない場合、選択対象のアイテムが含まれたアセンブリへの参照をプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c495-124">If these items are not in the current project, you must remember to add a reference in your project to the assembly that contains the item that you want to select.</span></span> <span data-ttu-id="4c495-125">これを行うには、プロジェクトを右クリックし **参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="4c495-125">To do this, right-click the project and select **Add Reference**.</span></span>  
  
 <span data-ttu-id="4c495-126">**ズーム機能のサポート**</span><span class="sxs-lookup"><span data-stu-id="4c495-126">**Zoom Support**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4c495-127"> では、オーケストレーション デザイナー画面の拡大や縮小が可能です。</span><span class="sxs-lookup"><span data-stu-id="4c495-127"> provides the ability to zoom in or zoom out of the Orchestration designer surface.</span></span> <span data-ttu-id="4c495-128">ズーム機能を使用するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4c495-128">You can use zoom support by completing one of the following steps:</span></span>  
  
-   <span data-ttu-id="4c495-129">オーケストレーション デザイナー画面を右クリックし、をクリックして、**ズーム**メニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="4c495-129">Right-click the Orchestration designer surface and click the **Zoom** menu option.</span></span> <span data-ttu-id="4c495-130">次に、適用する拡大率を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c495-130">You can then select the percentage of magnification that you would like to apply.</span></span>  
  
-   <span data-ttu-id="4c495-131">Ctrl キーとマウス ホイールを組み合わせて使用し、拡大または縮小します。Ctrl キーを押しながら、マウス ホイールを上下に回転させます。</span><span class="sxs-lookup"><span data-stu-id="4c495-131">Use the CTRL + MWHEEL combination to zoom in or zoom out. Hold down the CTRL button and simultaneously rotate the mouse wheel up or down.</span></span> <span data-ttu-id="4c495-132">Ctrl キーを押しながら、マウス ホイールを上へ回転させると縮小し、下へ回転させると拡大します。</span><span class="sxs-lookup"><span data-stu-id="4c495-132">Use the CTRL+MWHEELUP combination to zoom out and the CTRL+MWHEELDOWN combination to zoom in.</span></span>