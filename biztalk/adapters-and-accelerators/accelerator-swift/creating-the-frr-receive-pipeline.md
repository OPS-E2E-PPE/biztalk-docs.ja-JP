---
title: "受信パイプラインの作成、FRR |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad31a69d579cf2bbe9f646fc87be1bea9f561a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-pipeline"></a><span data-ttu-id="16e6c-102">受信パイプラインの FRR の作成</span><span class="sxs-lookup"><span data-stu-id="16e6c-102">Creating the FRR Receive Pipeline</span></span>
<span data-ttu-id="16e6c-103">FIN 対応調整を実行するには、SWIFT FRR デコーダーと SWIFT の逆アセンブラーに加え、SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネントを含む受信パイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e6c-103">To perform FIN Response Reconciliation, you must create a receive pipeline that contains the SWIFT FRR Decoder and SWIFT FRR CorrelationSet Resolver pipeline components, in addition to the SWIFT disassembler.</span></span>  
  
 <span data-ttu-id="16e6c-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="16e6c-104">**Summary**</span></span>  
  
 <span data-ttu-id="16e6c-105">次のステージ/プロパティで、受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="16e6c-105">Create a receive pipeline with the following stages/properties:</span></span>  
  
|<span data-ttu-id="16e6c-106">ステージ/プロパティ</span><span class="sxs-lookup"><span data-stu-id="16e6c-106">Stage/Property</span></span>|<span data-ttu-id="16e6c-107">コンポーネント/設定</span><span class="sxs-lookup"><span data-stu-id="16e6c-107">Component/Setting</span></span>|  
|---------------------|------------------------|  
|<span data-ttu-id="16e6c-108">逆アセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="16e6c-108">Disassemble stage</span></span>|<span data-ttu-id="16e6c-109">SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="16e6c-109">SWIFT Disassembler</span></span>|  
|<span data-ttu-id="16e6c-110">BRE の検証プロパティ (SWIFT 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="16e6c-110">BRE Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="16e6c-111">True</span><span class="sxs-lookup"><span data-stu-id="16e6c-111">True</span></span>|  
|<span data-ttu-id="16e6c-112">XML 検証プロパティ (SWIFT 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="16e6c-112">XML Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="16e6c-113">True</span><span class="sxs-lookup"><span data-stu-id="16e6c-113">True</span></span>|  
|<span data-ttu-id="16e6c-114">SWIFT ヘッダー スキーマ プロパティ (SWIFT 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="16e6c-114">SWIFT Header Schema property (SWIFT Disassembler)</span></span>|<span data-ttu-id="16e6c-115">(なし)</span><span class="sxs-lookup"><span data-stu-id="16e6c-115">(None)</span></span>|  
|<span data-ttu-id="16e6c-116">デコーダーのステージ</span><span class="sxs-lookup"><span data-stu-id="16e6c-116">Decoder stage</span></span>|<span data-ttu-id="16e6c-117">SWIFT FRR MQSeries デコーダー</span><span class="sxs-lookup"><span data-stu-id="16e6c-117">SWIFT FRR MQSeries Decoder</span></span>|  
|<span data-ttu-id="16e6c-118">パーティの解決ステージ</span><span class="sxs-lookup"><span data-stu-id="16e6c-118">Party Resolution stage</span></span>|<span data-ttu-id="16e6c-119">SWIFT FRR 相関関係の設定の競合回避モジュール</span><span class="sxs-lookup"><span data-stu-id="16e6c-119">SWIFT FRR Correlation Set Resolver</span></span>|  
  
### <a name="to-create-a-custom-receive-pipeline-for-frr"></a><span data-ttu-id="16e6c-120">FRR のカスタム受信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="16e6c-120">To create a custom receive pipeline for FRR</span></span>  
  
1.  <span data-ttu-id="16e6c-121">ソリューション エクスプ ローラーの Visual Studio で、含まれているプロジェクトを右クリックし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パイプライン、順にポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="16e6c-121">In Solution Explorer of Visual Studio, right-click the project containing your [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] pipelines, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="16e6c-122">新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで、選択**受信パイプライン**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="16e6c-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="16e6c-123">**名前**ボックスで、受信パイプラインの名前を入力します。 **FRRReceivePipeline.btp**です。</span><span class="sxs-lookup"><span data-stu-id="16e6c-123">In the **Name** box, type a name for your receive pipeline, such as **FRRReceivePipeline.btp**.</span></span> <span data-ttu-id="16e6c-124">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16e6c-124">Click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16e6c-125">追加する必要があります手順 4. を実行する前に、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 」の説明に従って、FRR がツールボックスにコンポーネントをパイプライン[をツールボックスに SWIFT パイプライン コンポーネントを追加する](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)です。</span><span class="sxs-lookup"><span data-stu-id="16e6c-125">Before you perform step 4, you must have added the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR pipeline components to the toolbox, as described in [Adding SWIFT Pipeline Components to the Toolbox](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span></span>  
  
4.  <span data-ttu-id="16e6c-126">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー** をクリックし、**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="16e6c-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then click **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="16e6c-127">BizTalk パイプライン コンポーネント [ツールボックス] ウィンドウからドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**パイプライン デザイナーで図形をステージです。</span><span class="sxs-lookup"><span data-stu-id="16e6c-127">From the BizTalk Pipeline Components Toolbox pane, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in Pipeline Designer.</span></span>  
  
6.  <span data-ttu-id="16e6c-128">**SWIFT 逆アセンブラー コンポーネント**でパイプライン デザイナーで選択した**プロパティ**、いることを確認、 **BRE 検証**と**XML 検証**プロパティに設定されます**True**、および**SWIFT ヘッダー スキーマ**プロパティに設定されている**(なし)**です。</span><span class="sxs-lookup"><span data-stu-id="16e6c-128">With the **SWIFT Disassembler Component** selected in Pipeline Designer, in **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**, and the **SWIFT Header Schema** property is set to **(None)**.</span></span>  
  
7.  <span data-ttu-id="16e6c-129">BizTalk パイプライン コンポーネント [ツールボックス] で、ドラッグ**SWIFT FRR MQSeries デコーダー**を**ここにドロップ**下のボックス、**デコーダー**パイプライン デザイナーで図形をステージです。</span><span class="sxs-lookup"><span data-stu-id="16e6c-129">In the BizTalk Pipeline Components Toolbox, drag **SWIFT FRR MQSeries Decoder** to the **Drop Here** box below the **Decoder** stage shape in Pipeline Designer.</span></span>  
  
8.  <span data-ttu-id="16e6c-130">BizTalk パイプライン コンポーネント [ツールボックス] ウィンドウからドラッグ**SWIFT FRR 相関関係設定の競合回避モジュール**を**ここにドロップ**下のボックス、**パーティの解決**パイプライン内の図形をステージデザイナー。</span><span class="sxs-lookup"><span data-stu-id="16e6c-130">From the BizTalk Pipeline Components Toolbox pane, drag **SWIFT FRR Correlation Set Resolver** to the **Drop Here** box below the **ResolveParty** stage shape in Pipeline Designer.</span></span>  
  
9. <span data-ttu-id="16e6c-131">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ファイル**、順にクリック**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="16e6c-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then click **Save All**.</span></span>