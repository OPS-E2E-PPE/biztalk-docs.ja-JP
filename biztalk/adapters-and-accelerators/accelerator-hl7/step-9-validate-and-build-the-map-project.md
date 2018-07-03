---
title: '手順 9: 検証し、マップ プロジェクトのビルド |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb542ffd185cfa0f84c1e73ce17becfacdb709f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966651"
---
# <a name="step-9-validate-and-build-the-map-project"></a><span data-ttu-id="7bfb6-102">手順 9: 検証し、マップ プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="7bfb6-102">Step 9: Validate and Build the Map Project</span></span>
<span data-ttu-id="7bfb6-103">この手順で使用する、**マップの検証**コマンドをマップ、内部の不整合が含まれていますかを妨げる、マッピング スキーマを効果的に使用されているその他の問題があるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-103">In this step, you use the **Validate Map** command to determine if the map contains any internal inconsistencies, or has other issues that would prevent it from being used effectively for mapping schemas.</span></span> <span data-ttu-id="7bfb6-104">また、作成したリソース (スキーマおよびマップ) を含むアセンブリを生成するプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-104">You also build the project to generate an assembly that contains the resources (schemas and the map) that you created.</span></span> <span data-ttu-id="7bfb6-105">またこれにより、これまでに完了した作業でコンパイル エラーがないこと。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-105">This also ensures that there are no compile errors in the work that you have completed so far.</span></span>  
  
### <a name="to-validate-the-map-project"></a><span data-ttu-id="7bfb6-106">マップのプロジェクトを検証するには</span><span class="sxs-lookup"><span data-stu-id="7bfb6-106">To validate the map project</span></span>  
  
1.  <span data-ttu-id="7bfb6-107">ソリューション エクスプ ローラーで右クリックし、 **DoorbellMap.btm**マップ、およびクリックして**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-107">In Solution Explorer, right-click the **DoorbellMap.btm** map, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="7bfb6-108">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-108">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="7bfb6-109">送信先スキーマ内のすべての利用可能な要素にマップしているのではないために、いくつかの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-109">Some warnings may appear because you are not mapping to all available elements in the destination schema.</span></span>  
  
     <span data-ttu-id="7bfb6-110">成功メッセージが表示されない場合は、マップのプロジェクトをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-110">If no success message appears, troubleshoot the map project.</span></span>  
  
### <a name="to-build-the-map-project"></a><span data-ttu-id="7bfb6-111">マップのプロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="7bfb6-111">To build the map project</span></span>  
  
- <span data-ttu-id="7bfb6-112">ソリューション エクスプ ローラーで右クリックして**BTAHL7 プロジェクト**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Build**.</span></span> <span data-ttu-id="7bfb6-113">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-113">Ensure that a success message appears in the output window.</span></span>  
  
   <span data-ttu-id="7bfb6-114">成功メッセージが表示されない場合は、マップのプロジェクトをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-114">If no success message appears, troubleshoot the map project.</span></span>  
  
  <span data-ttu-id="7bfb6-115">続行する[手順 10: オーケストレーションを作成する](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="7bfb6-115">Proceed to [Step 10: Create an Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bfb6-116">参照</span><span class="sxs-lookup"><span data-stu-id="7bfb6-116">See Also</span></span>  
 [<span data-ttu-id="7bfb6-117">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="7bfb6-117">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)