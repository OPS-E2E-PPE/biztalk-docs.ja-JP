---
title: 送信パイプラインの作成、FRR |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87733b6b3a93d2543d26cd6d11b366b84218d207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209458"
---
# <a name="creating-the-frr-send-pipeline"></a><span data-ttu-id="cd712-102">FRR 送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd712-102">Creating the FRR Send Pipeline</span></span>
<span data-ttu-id="cd712-103">FIN 対応調整を実行するには、SWIFT アセンブラーだけでなく、SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントを含む送信パイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd712-103">To perform FIN Response Reconciliation, you need to create a send pipeline that contains the SWIFTAsmFrrMQSeriesHelper pipeline component, in addition to the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="cd712-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="cd712-104">**Summary**</span></span>  
  
 <span data-ttu-id="cd712-105">次の段階で、送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd712-105">Create a send pipeline with the following stages:</span></span>  
  
|<span data-ttu-id="cd712-106">段階</span><span class="sxs-lookup"><span data-stu-id="cd712-106">Stage</span></span>|<span data-ttu-id="cd712-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cd712-107">Component</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="cd712-108">アセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="cd712-108">Assemble stage</span></span>|<span data-ttu-id="cd712-109">SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="cd712-109">SWIFT assembler</span></span>|  
|<span data-ttu-id="cd712-110">エンコード ステージ</span><span class="sxs-lookup"><span data-stu-id="cd712-110">Encode stage</span></span>|<span data-ttu-id="cd712-111">SWIFT Frr MQSeries の送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cd712-111">SWIFT Frr MQSeries Send Component</span></span>|  
  
### <a name="to-create-a-custom-send-pipeline-for-frr"></a><span data-ttu-id="cd712-112">FRR のカスタムの送信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="cd712-112">To create a custom send pipeline for FRR</span></span>  
  
1.  <span data-ttu-id="cd712-113">ソリューション エクスプ ローラーの Visual Studio で、パイプライン プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="cd712-113">In Solution Explorer of Visual Studio, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="cd712-114">[新しい項目の追加] ダイアログ ボックスで選択**送信パイプライン**[テンプレート] ペインからです。</span><span class="sxs-lookup"><span data-stu-id="cd712-114">In the Add New Item dialog box, select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="cd712-115">**名前**ボックスで、受信パイプラインの名前を入力します。 **FRRSendPipeline.btp**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-115">In the **Name** box, type a name for your receive pipeline, such as **FRRSendPipeline.btp**.</span></span> <span data-ttu-id="cd712-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd712-116">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="cd712-117">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー**し**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-117">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="cd712-118">BizTalk パイプライン コンポーネント [ツールボックス] からドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプラインデザイナー**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-118">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
6.  <span data-ttu-id="cd712-119">BizTalk パイプライン コンポーネント [ツールボックス] からドラッグ**SWIFT Frr MQSeries の送信コンポーネント**を**ここにドロップ**下のボックス、**エンコード**で図形をステージ**BizTalk パイプライン デザイナ**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-119">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Frr MQSeries Send Component** to the **Drop Here** box below the **Encode** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="cd712-120">BizTalk エクスプ ローラーで、パイプライン プロジェクトを右クリックし、をクリックして**Undeploy**、順にクリック**はい**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-120">In BizTalk Explorer, right-click your pipeline project, click **Undeploy**, and then click **Yes**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd712-121">展開解除と、パイプライン プロジェクトを再、後に、送信ポートをリセットするか、以前に配置されたプロジェクトでパイプラインを使用する受信場所できます。</span><span class="sxs-lookup"><span data-stu-id="cd712-121">After undeploying and then redeploying your pipeline project, you must reset any send ports or receive locations that use pipelines in the previously deployed project.</span></span>  
  
8.  <span data-ttu-id="cd712-122">ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-122">In Solution Explorer, right-click your pipeline project, and then click **Build**.</span></span>  
  
9. <span data-ttu-id="cd712-123">ビルドが成功した後、パイプライン プロジェクトを右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="cd712-123">After the build has succeeded, right-click your pipeline project, and then click **Deploy**.</span></span>