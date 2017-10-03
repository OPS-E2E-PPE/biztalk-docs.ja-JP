---
title: "SWIFT パイプライン コンポーネントをツールボックスに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaef345994a1d849e09025d9ad1bb0f133c1b224
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="4905b-102">SWIFT パイプライン コンポーネントをツールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="4905b-102">Adding SWIFT Pipeline Components to the Toolbox</span></span>
<span data-ttu-id="4905b-103">SWIFT パイプライン コンポーネントを追加する必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス、これらのコンポーネントを使用してカスタム パイプラインを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4905b-103">You must add the SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox, so that you can create custom pipelines using these components.</span></span> <span data-ttu-id="4905b-104">これは、Message Repair および New Submission または FIN 対応調整のいずれかのパイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4905b-104">This is required to create pipelines for either Message Repair and New Submission or FIN Response Reconciliation.</span></span>  
  
 <span data-ttu-id="4905b-105">**概要**</span><span class="sxs-lookup"><span data-stu-id="4905b-105">**Summary**</span></span>  
  
 <span data-ttu-id="4905b-106">次の SWIFT パイプライン コンポーネントを追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス。</span><span class="sxs-lookup"><span data-stu-id="4905b-106">Add the following SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox:</span></span>  
  
-   <span data-ttu-id="4905b-107">SWIFT アセンブラー (Message Repair および New Submission FIN 対応調整 (FRR) 用)</span><span class="sxs-lookup"><span data-stu-id="4905b-107">SWIFT Assembler (for Message Repair and New Submission or FIN Response Reconciliation (FRR))</span></span>  
  
-   <span data-ttu-id="4905b-108">SWIFT の逆アセンブラー (Message Repair および New Submission FRR 用)</span><span class="sxs-lookup"><span data-stu-id="4905b-108">SWIFT Disassembler (for Message Repair and New Submission or FRR)</span></span>  
  
-   <span data-ttu-id="4905b-109">SWIFT Frr 相関関係の設定 (FRR) の競合回避モジュール</span><span class="sxs-lookup"><span data-stu-id="4905b-109">SWIFT Frr Correlation Set Resolver (for FRR)</span></span>  
  
-   <span data-ttu-id="4905b-110">SWIFT Frr MQSeries デコーダー (用 FRR)</span><span class="sxs-lookup"><span data-stu-id="4905b-110">SWIFT Frr MQSeries Decoder (for FRR)</span></span>  
  
-   <span data-ttu-id="4905b-111">SWIFT Frr MQSeries 送信コンポーネント (FRR)</span><span class="sxs-lookup"><span data-stu-id="4905b-111">SWIFT Frr MQSeries Send Component (for FRR)</span></span>  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="4905b-112">A4SWIFT パイプライン コンポーネントをツールボックスに追加するには</span><span class="sxs-lookup"><span data-stu-id="4905b-112">To add A4SWIFT pipeline components to the toolbox</span></span>  
  
1.  <span data-ttu-id="4905b-113">Visual Studio での**ツール** メニューのをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="4905b-113">In Visual Studio, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="4905b-114">**ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **SWIFT アセンブラー**と**SWIFT 逆アセンブラー**.</span><span class="sxs-lookup"><span data-stu-id="4905b-114">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Components** tab, select **SWIFT Assembler** and **SWIFT Disassembler**.</span></span> <span data-ttu-id="4905b-115">FIN 対応調整を使用する場合は、選択**SWIFT Frr 相関関係設定の競合回避モジュール**、 **SWIFT Frr MQSeries デコーダー**、および**SWIFT Frr MQSeries の送信コンポーネント**です。</span><span class="sxs-lookup"><span data-stu-id="4905b-115">If you will be using FIN Response Reconciliation, select **SWIFT Frr Correlation Set Resolver**, **SWIFT Frr MQSeries Decoder**, and **SWIFT Frr MQSeries Send Component**.</span></span>  
  
3.  <span data-ttu-id="4905b-116">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4905b-116">Click **OK**.</span></span>