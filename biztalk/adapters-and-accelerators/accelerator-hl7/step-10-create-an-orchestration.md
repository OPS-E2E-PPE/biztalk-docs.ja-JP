---
title: "手順 10: オーケストレーションを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, creating
- creating, orchestrations
- message enrichment tutorial, orchestrations
ms.assetid: 10f5cf3d-4a34-4c80-89d1-c390552cfc09
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc554a6f3c94a077b34ae79a36b8e484eadcd5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-10-create-an-orchestration"></a><span data-ttu-id="39dd8-102">手順 10: オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-102">Step 10: Create an Orchestration</span></span>
<span data-ttu-id="39dd8-103">このステップでは、患者 ADT_A04 メッセージを完全に作成される追加の詳細を取得するためのビジネス プロセスを表すオーケストレーションを作成するのにオーケストレーション デザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-103">In this step, you use Orchestration Designer to create an orchestration to represent the business process for retrieving additional patient details to fully populate an ADT_A04 message.</span></span> <span data-ttu-id="39dd8-104">オーケストレーション デザイナーを使用して、このビジネス プロセスのアクションを表すために必要なオーケストレーション図形を選択します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-104">Using Orchestration Designer, you select the orchestration shapes required to represent actions for this business process.</span></span> <span data-ttu-id="39dd8-105">以降の演習では、それらが正しく機能できるように、図形を構成する追加の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-105">In later exercises, you provide additional information to configure the shapes so that they can function properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39dd8-106">次の手順で作成されたオーケストレーションは、このチュートリアルのコンテキストでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-106">The orchestration created in the following steps only works in the context of this tutorial.</span></span> <span data-ttu-id="39dd8-107">オーケストレーションが正しく機能するためには、アセンブリ参照、マップ、およびその他の成果物をこのチュートリアルを使用しているときに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39dd8-107">In order for the orchestration to work correctly, it needs the assembly references, maps, and the other artifacts that you create while using this tutorial.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="39dd8-108">オーケストレーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="39dd8-108">To create an orchestration</span></span>  
  
1.  <span data-ttu-id="39dd8-109">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-109">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="39dd8-110">**新しい項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**オーケストレーション ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-110">In the **Add New Item** dialog box, in the **Categories** pane, click **Orchestration Files**.</span></span>  
  
3.  <span data-ttu-id="39dd8-111">**テンプレート** ウィンドウで、をクリックして**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-111">In the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
4.  <span data-ttu-id="39dd8-112">**名前**フィールドに「**ドアベル Orchestration.odx** (、単語の間にスペースがあることに注意してください**ドアベル**と**オーケストレーション**) をクリックし、オーケストレーションの名前として**追加**新しいオーケストレーション ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="39dd8-112">In the **Name** field, type **Doorbell Orchestration.odx** (note that there is a space between the word **Doorbell** and **Orchestration**) as the orchestration name, and then click **Add** to create a new orchestration file.</span></span>  
  
5.  <span data-ttu-id="39dd8-113">**ビュー**  メニューのをクリックして**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-113">In the **View** menu, click **Toolbox**.</span></span>  
  
6.  <span data-ttu-id="39dd8-114">**ツールボックス** ウィンドウで、ドラッグ、**受信**図形をデザイン ビュー画面にし、ラベルが付いた領域にドロップ**ツールボックスからここに図形をドロップ**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-114">In the **Toolbox** pane, drag the **Receive** shape to the Design view surface and drop it on the area labeled **Drop a shape from the toolbox here**.</span></span>  
  
7.  <span data-ttu-id="39dd8-115">(上、画面の右下) の [プロパティ] ウィンドウでをクリックして、**名前**プロパティと型**DoorbellReceive**の名前として、**受信**図形、およびキーを押します**入力**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-115">In the Properties window (on the bottom right of your screen), click the **Name** property and type **DoorbellReceive** as the name of the **Receive** shape, and then press **Enter**.</span></span>  
  
8.  <span data-ttu-id="39dd8-116">[プロパティ] ウィンドウで変更、 **Activate**プロパティを**True**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-116">In the Properties window, change the **Activate** property to **True**.</span></span>  
  
9. <span data-ttu-id="39dd8-117">ドラッグ、**変換**図形をツールボックスから、直接の下にドロップして、 **DoorbellReceive**図形です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-117">Drag the **Transform** shape from the Toolbox and drop it directly below the **DoorbellReceive** shape.</span></span>  
  
10. <span data-ttu-id="39dd8-118">(上、画面の右下) の [プロパティ] ウィンドウでをクリックして、**名前**の名前を変更するプロパティ、**変換**図形を**DoorbellTransform**、キーを押します**入力**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-118">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Transform** shape to **DoorbellTransform**, and then press **Enter**.</span></span>  
  
11. <span data-ttu-id="39dd8-119">**ツールボックス** ウィンドウで、ドラッグ、**メッセージの割り当て**図形をデザイン ビュー画面にし、領域のすぐ下にドロップ、 **ConstructMessage_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-119">In the **Toolbox** pane, drag the **Message Assignment** shape to the Design view surface and drop it on the area directly below the **ConstructMessage_1** shape.</span></span>  
  
12. <span data-ttu-id="39dd8-120">オーケストレーションのデザイン ビュー サーフェイスでをクリックして、 **MessageAssignment_1**図形、し、[、**プロパティ**] ウィンドウで、をクリックして**名前**新しい名前を入力し、 **DoorbellFinalTransform**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-120">In the orchestration Design view surface, click the **MessageAssignment_1** shape, and in the **Properties** pane, click **Name** and type the new name **DoorbellFinalTransform**, and then press **Enter**.</span></span>  
  
13. <span data-ttu-id="39dd8-121">ドラッグ、**送信**図形をツールボックスから、直接の下の区分線にドロップ、 **DoorbellFinalTransform**図形です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-121">Drag the **Send** shape from the Toolbox and drop it on the connecting line directly below the **DoorbellFinalTransform** shape.</span></span>  
  
14. <span data-ttu-id="39dd8-122">(上、画面の右下) の [プロパティ] ウィンドウでをクリックして、**名前**の名前を変更するプロパティ、**送信**図形を**DoorbellSend**、キーを押します**入力**です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-122">In the Properties window (on the bottom right of your screen), click the **Name** property to change the name of the **Send** shape to **DoorbellSend**, and then press **Enter**.</span></span>  
  
 <span data-ttu-id="39dd8-123">進みます[手順 11: オーケストレーション変数を作成する](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)です。</span><span class="sxs-lookup"><span data-stu-id="39dd8-123">Proceed to [Step 11: Create Orchestration Variables](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39dd8-124">参照</span><span class="sxs-lookup"><span data-stu-id="39dd8-124">See Also</span></span>  
 [<span data-ttu-id="39dd8-125">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="39dd8-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)