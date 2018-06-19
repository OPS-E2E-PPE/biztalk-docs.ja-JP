---
title: '手順 7: 署名し、プロジェクトをビルド |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, projects
- projects, building
- projects, signing
ms.assetid: b66e4dc1-4ec6-4ec0-a69a-419b116b19c1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f62a37da291bdc148369a28149cdfe29ed7fe446
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961768"
---
# <a name="step-7-sign-and-build-the-projects"></a><span data-ttu-id="4c518-102">手順 7: 署名し、プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="4c518-102">Step 7: Sign and Build the Projects</span></span>
<span data-ttu-id="4c518-103">この手順で、厳密な名前を割り当てるし、で作成したリソース (スキーマ) を含むアセンブリを生成するプロジェクトをビルド[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c518-103">In this step, you assign a strong name and build the project to generate an assembly that contains the resources (the schema) that you created in [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span> <span data-ttu-id="4c518-104">またこれにより、これまでに完了した作業ではコンパイル エラーがないこと。</span><span class="sxs-lookup"><span data-stu-id="4c518-104">This also ensures that there are no compile errors in the work you have completed so far.</span></span>  
  
### <a name="to-sign-the-btahl7-project"></a><span data-ttu-id="4c518-105">BTAHL7 プロジェクトに署名するには</span><span class="sxs-lookup"><span data-stu-id="4c518-105">To sign the BTAHL7 Project</span></span>  
  
1.  <span data-ttu-id="4c518-106">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="4c518-106">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="4c518-107">BTAHL7 プロジェクト プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="4c518-107">In the BTAHL7 Project Property Pages dialog box, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="4c518-108">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c518-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4.  <span data-ttu-id="4c518-109">アセンブリ キー ファイル ダイアログ ボックスでを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk** (で作成されるよう[手順 3: に厳密な名前を割り当てる、アセンブリ](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="4c518-109">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk** (as created in [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)), and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="4c518-110">をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="4c518-110">Click **OK** to save changes.</span></span>  
  
### <a name="to-build-the-btahl7-project"></a><span data-ttu-id="4c518-111">BTAHL7 プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="4c518-111">To build the BTAHL7 Project</span></span>  
  
-   <span data-ttu-id="4c518-112">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="4c518-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="4c518-113">DLL ファイルにアセンブリをコンパイルしで保存、 \<*ドライブ*\>: \Tutorial\BTAHL7V22Common\Bin\Development フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4c518-113"> compiles the assembly into a DLL file and saves it in the \<*drive*\>:\Tutorial\BTAHL7V22Common\Bin\Development folder.</span></span>  
  
 <span data-ttu-id="4c518-114">進みます[手順 8: BizTalk マッパーでマップの作成](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c518-114">Proceed to [Step 8: Create a Map with BizTalk Mapper](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c518-115">参照</span><span class="sxs-lookup"><span data-stu-id="4c518-115">See Also</span></span>  
 [<span data-ttu-id="4c518-116">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="4c518-116">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)