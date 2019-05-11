---
title: ツールボックスに SWIFT パイプライン コンポーネントの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4594b3ed3ca1c348a9d903217d165f8f9d2380d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378641"
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="93605-102">ツールボックスに SWIFT パイプライン コンポーネントの追加</span><span class="sxs-lookup"><span data-stu-id="93605-102">Adding SWIFT Pipeline Components to the Toolbox</span></span>
<span data-ttu-id="93605-103">SWIFT パイプライン コンポーネントを追加する必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス、これらのコンポーネントを使用してカスタムのパイプラインを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="93605-103">You must add the SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox, so that you can create custom pipelines using these components.</span></span> <span data-ttu-id="93605-104">これは、Message Repair および New Submission または FIN Response Reconciliation のいずれかのパイプラインの作成に必要です。</span><span class="sxs-lookup"><span data-stu-id="93605-104">This is required to create pipelines for either Message Repair and New Submission or FIN Response Reconciliation.</span></span>  
  
 <span data-ttu-id="93605-105">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="93605-105">**Summary**</span></span>  
  
 <span data-ttu-id="93605-106">次の SWIFT パイプライン コンポーネントの追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ツールボックス。</span><span class="sxs-lookup"><span data-stu-id="93605-106">Add the following SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox:</span></span>  
  
-   <span data-ttu-id="93605-107">SWIFT アセンブラー (Message Repair および New Submission FIN Response Reconciliation (FRR) 用)</span><span class="sxs-lookup"><span data-stu-id="93605-107">SWIFT Assembler (for Message Repair and New Submission or FIN Response Reconciliation (FRR))</span></span>  
  
-   <span data-ttu-id="93605-108">(Message Repair および New Submission または FRR) 用に SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="93605-108">SWIFT Disassembler (for Message Repair and New Submission or FRR)</span></span>  
  
-   <span data-ttu-id="93605-109">SWIFT Frr 相関関係の設定 (用として FRR) 競合回避モジュール</span><span class="sxs-lookup"><span data-stu-id="93605-109">SWIFT Frr Correlation Set Resolver (for FRR)</span></span>  
  
-   <span data-ttu-id="93605-110">SWIFT Frr MQSeries のデコーダー (用として FRR)</span><span class="sxs-lookup"><span data-stu-id="93605-110">SWIFT Frr MQSeries Decoder (for FRR)</span></span>  
  
-   <span data-ttu-id="93605-111">SWIFT の Frr MQSeries の送信コンポーネント (用として FRR)</span><span class="sxs-lookup"><span data-stu-id="93605-111">SWIFT Frr MQSeries Send Component (for FRR)</span></span>  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="93605-112">A4SWIFT パイプライン コンポーネントをツールボックスに追加するには</span><span class="sxs-lookup"><span data-stu-id="93605-112">To add A4SWIFT pipeline components to the toolbox</span></span>  
  
1.  <span data-ttu-id="93605-113">Visual Studio での**ツール**] メニューのをクリックして **[ツールボックス アイテムの**します。</span><span class="sxs-lookup"><span data-stu-id="93605-113">In Visual Studio, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="93605-114">**ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **SWIFT アセンブラー**と**SWIFT 逆アセンブラー**.</span><span class="sxs-lookup"><span data-stu-id="93605-114">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Components** tab, select **SWIFT Assembler** and **SWIFT Disassembler**.</span></span> <span data-ttu-id="93605-115">FIN Response Reconciliation を使用する場合は選択**SWIFT Frr 相関設定リゾルバー**、 **SWIFT Frr MQSeries デコーダー**、および**SWIFT Frr MQSeries の送信コンポーネント**します。</span><span class="sxs-lookup"><span data-stu-id="93605-115">If you will be using FIN Response Reconciliation, select **SWIFT Frr Correlation Set Resolver**, **SWIFT Frr MQSeries Decoder**, and **SWIFT Frr MQSeries Send Component**.</span></span>  
  
3.  <span data-ttu-id="93605-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93605-116">Click **OK**.</span></span>