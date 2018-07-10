---
title: 送信パイプラインの作成、FRR |Microsoft Docs
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
ms.openlocfilehash: d16003e489944016a7b840b870d33d8ebcf671d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005747"
---
# <a name="creating-the-frr-send-pipeline"></a><span data-ttu-id="ff5ef-102">FRR 送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-102">Creating the FRR Send Pipeline</span></span>
<span data-ttu-id="ff5ef-103">FIN Response Reconciliation を実行するには、SWIFT アセンブラーに加え、SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントを含む送信パイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-103">To perform FIN Response Reconciliation, you need to create a send pipeline that contains the SWIFTAsmFrrMQSeriesHelper pipeline component, in addition to the SWIFT assembler.</span></span>  

 <span data-ttu-id="ff5ef-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="ff5ef-104">**Summary**</span></span>  

 <span data-ttu-id="ff5ef-105">次の段階では、送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-105">Create a send pipeline with the following stages:</span></span>  

|<span data-ttu-id="ff5ef-106">段階</span><span class="sxs-lookup"><span data-stu-id="ff5ef-106">Stage</span></span>|<span data-ttu-id="ff5ef-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ff5ef-107">Component</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="ff5ef-108">アセンブル ステージ</span><span class="sxs-lookup"><span data-stu-id="ff5ef-108">Assemble stage</span></span>|<span data-ttu-id="ff5ef-109">SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="ff5ef-109">SWIFT assembler</span></span>|  
|<span data-ttu-id="ff5ef-110">エンコード ステージ</span><span class="sxs-lookup"><span data-stu-id="ff5ef-110">Encode stage</span></span>|<span data-ttu-id="ff5ef-111">SWIFT Frr MQSeries の送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ff5ef-111">SWIFT Frr MQSeries Send Component</span></span>|  

### <a name="to-create-a-custom-send-pipeline-for-frr"></a><span data-ttu-id="ff5ef-112">FRR 用カスタム送信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="ff5ef-112">To create a custom send pipeline for FRR</span></span>  

1. <span data-ttu-id="ff5ef-113">ソリューション エクスプ ローラーの Visual Studio で、パイプライン プロジェクトを右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-113">In Solution Explorer of Visual Studio, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="ff5ef-114">新しい項目の追加 ダイアログ ボックスで、**送信パイプライン**テンプレート ペインから。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-114">In the Add New Item dialog box, select **Send Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="ff5ef-115">**名前**など、受信パイプラインの名前を入力ボックスに、 **FRRSendPipeline.btp**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-115">In the **Name** box, type a name for your receive pipeline, such as **FRRSendPipeline.btp**.</span></span> <span data-ttu-id="ff5ef-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-116">Click **Add**.</span></span>  

4. <span data-ttu-id="ff5ef-117">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ビュー**し**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-117">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

5. <span data-ttu-id="ff5ef-118">BizTalk パイプライン コンポーネントのツールボックスからドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプラインデザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-118">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  

6. <span data-ttu-id="ff5ef-119">BizTalk パイプライン コンポーネントのツールボックスからドラッグ**SWIFT Frr MQSeries の送信コンポーネント**を**ここにドロップ**下のボックス、**エンコード**で図形をステージ**BizTalk パイプライン デザイナ**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-119">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Frr MQSeries Send Component** to the **Drop Here** box below the **Encode** stage shape in **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="ff5ef-120">BizTalk エクスプ ローラーで、パイプライン プロジェクトを右クリックして**Undeploy**、順にクリックします**はい**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-120">In BizTalk Explorer, right-click your pipeline project, click **Undeploy**, and then click **Yes**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ff5ef-121">展開解除して、パイプライン プロジェクトを再デプロイし後、は、送信ポートをリセットか、以前に配置されたプロジェクトでパイプラインを使用する受信場所必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-121">After undeploying and then redeploying your pipeline project, you must reset any send ports or receive locations that use pipelines in the previously deployed project.</span></span>  

8. <span data-ttu-id="ff5ef-122">ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックし をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-122">In Solution Explorer, right-click your pipeline project, and then click **Build**.</span></span>  

9. <span data-ttu-id="ff5ef-123">ビルドが成功した後、パイプライン プロジェクトを右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="ff5ef-123">After the build has succeeded, right-click your pipeline project, and then click **Deploy**.</span></span>
