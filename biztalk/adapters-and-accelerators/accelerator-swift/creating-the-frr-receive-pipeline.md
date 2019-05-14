---
title: 受信パイプラインの作成、FRR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f82aef718422dc00c80d9f22343873780380a801
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378319"
---
# <a name="creating-the-frr-receive-pipeline"></a><span data-ttu-id="99bc9-102">作成、FRR 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="99bc9-102">Creating the FRR Receive Pipeline</span></span>
<span data-ttu-id="99bc9-103">FIN Response Reconciliation を実行するには、SWIFT FRR デコーダーと SWIFT 逆アセンブラーに加え、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネントを含む受信パイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99bc9-103">To perform FIN Response Reconciliation, you must create a receive pipeline that contains the SWIFT FRR Decoder and SWIFT FRR CorrelationSet Resolver pipeline components, in addition to the SWIFT disassembler.</span></span>  

 <span data-ttu-id="99bc9-104">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="99bc9-104">**Summary**</span></span>  

 <span data-ttu-id="99bc9-105">次のステージ/プロパティを持つ受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-105">Create a receive pipeline with the following stages/properties:</span></span>  

|<span data-ttu-id="99bc9-106">ステージ/プロパティ</span><span class="sxs-lookup"><span data-stu-id="99bc9-106">Stage/Property</span></span>|<span data-ttu-id="99bc9-107">コンポーネント/設定</span><span class="sxs-lookup"><span data-stu-id="99bc9-107">Component/Setting</span></span>|  
|---------------------|------------------------|  
|<span data-ttu-id="99bc9-108">逆アセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="99bc9-108">Disassemble stage</span></span>|<span data-ttu-id="99bc9-109">SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="99bc9-109">SWIFT Disassembler</span></span>|  
|<span data-ttu-id="99bc9-110">BRE の検証プロパティ (SWIFT 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="99bc9-110">BRE Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="99bc9-111">True</span><span class="sxs-lookup"><span data-stu-id="99bc9-111">True</span></span>|  
|<span data-ttu-id="99bc9-112">XML 検証プロパティ (SWIFT 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="99bc9-112">XML Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="99bc9-113">True</span><span class="sxs-lookup"><span data-stu-id="99bc9-113">True</span></span>|  
|<span data-ttu-id="99bc9-114">SWIFT ヘッダー スキーマ プロパティ (SWIFT 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="99bc9-114">SWIFT Header Schema property (SWIFT Disassembler)</span></span>|<span data-ttu-id="99bc9-115">(なし)</span><span class="sxs-lookup"><span data-stu-id="99bc9-115">(None)</span></span>|  
|<span data-ttu-id="99bc9-116">デコーダーのステージ</span><span class="sxs-lookup"><span data-stu-id="99bc9-116">Decoder stage</span></span>|<span data-ttu-id="99bc9-117">SWIFT FRR MQSeries デコーダー</span><span class="sxs-lookup"><span data-stu-id="99bc9-117">SWIFT FRR MQSeries Decoder</span></span>|  
|<span data-ttu-id="99bc9-118">パーティの解決ステージ</span><span class="sxs-lookup"><span data-stu-id="99bc9-118">Party Resolution stage</span></span>|<span data-ttu-id="99bc9-119">SWIFT FRR 関連付けセットの競合回避モジュール</span><span class="sxs-lookup"><span data-stu-id="99bc9-119">SWIFT FRR Correlation Set Resolver</span></span>|  

### <a name="to-create-a-custom-receive-pipeline-for-frr"></a><span data-ttu-id="99bc9-120">FRR のカスタム受信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="99bc9-120">To create a custom receive pipeline for FRR</span></span>  

1. <span data-ttu-id="99bc9-121">ソリューション エクスプ ローラーの Visual Studio でプロジェクトを含むを右クリックし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パイプラインが指す**追加**、順にクリックします**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-121">In Solution Explorer of Visual Studio, right-click the project containing your [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] pipelines, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="99bc9-122">新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで選択し**受信パイプライン**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="99bc9-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** in the Templates pane.</span></span>  

3. <span data-ttu-id="99bc9-123">**名前**など、受信パイプラインの名前を入力ボックスに、 **FRRReceivePipeline.btp**します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-123">In the **Name** box, type a name for your receive pipeline, such as **FRRReceivePipeline.btp**.</span></span> <span data-ttu-id="99bc9-124">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99bc9-124">Click **Add**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="99bc9-125">手順 4 を実行する前に追加する必要があります、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 」の説明に従って、FRR がツールボックスにコンポーネントをパイプライン[をツールボックスに SWIFT パイプライン コンポーネントを追加する](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-125">Before you perform step 4, you must have added the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR pipeline components to the toolbox, as described in [Adding SWIFT Pipeline Components to the Toolbox](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span></span>  

4. <span data-ttu-id="99bc9-126">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ビュー**し**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then click **Toolbox**.</span></span>  

5. <span data-ttu-id="99bc9-127">BizTalk パイプライン コンポーネントのツールボックス ウィンドウからドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**パイプライン デザイナーで図形をステージングします。</span><span class="sxs-lookup"><span data-stu-id="99bc9-127">From the BizTalk Pipeline Components Toolbox pane, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in Pipeline Designer.</span></span>  

6. <span data-ttu-id="99bc9-128">**SWIFT 逆アセンブラー コンポーネント**でパイプライン デザイナーで選択されている**プロパティ**、いることを確認、 **BRE 検証**と**XMLの検証**プロパティに設定されます**True**、および**SWIFT ヘッダー スキーマ**プロパティに設定されて **(なし)** します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-128">With the **SWIFT Disassembler Component** selected in Pipeline Designer, in **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**, and the **SWIFT Header Schema** property is set to **(None)**.</span></span>  

7. <span data-ttu-id="99bc9-129">BizTalk パイプライン コンポーネントのツールボックスのドラッグ**SWIFT FRR MQSeries デコーダー**を**ここにドロップ**下のボックス、**デコーダー**パイプライン デザイナーで図形をステージングします。</span><span class="sxs-lookup"><span data-stu-id="99bc9-129">In the BizTalk Pipeline Components Toolbox, drag **SWIFT FRR MQSeries Decoder** to the **Drop Here** box below the **Decoder** stage shape in Pipeline Designer.</span></span>  

8. <span data-ttu-id="99bc9-130">BizTalk パイプライン コンポーネントのツールボックス ウィンドウからドラッグ**SWIFT FRR 相関設定リゾルバー**を**ここにドロップ**下のボックス、**パーティの解決**パイプライン内の図形をステージデザイナー。</span><span class="sxs-lookup"><span data-stu-id="99bc9-130">From the BizTalk Pipeline Components Toolbox pane, drag **SWIFT FRR Correlation Set Resolver** to the **Drop Here** box below the **ResolveParty** stage shape in Pipeline Designer.</span></span>  

9. <span data-ttu-id="99bc9-131">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**ファイル**、 をクリックし、**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="99bc9-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then click **Save All**.</span></span>
