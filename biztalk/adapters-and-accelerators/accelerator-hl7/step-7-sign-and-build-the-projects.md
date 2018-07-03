---
title: '手順 7: サインインし、プロジェクトのビルド |Microsoft Docs'
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
ms.openlocfilehash: b34ad40b7ee8e083f53e18c34e65fa3c8699d352
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970123"
---
# <a name="step-7-sign-and-build-the-projects"></a><span data-ttu-id="c3ab7-102">手順 7: サインインし、プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="c3ab7-102">Step 7: Sign and Build the Projects</span></span>
<span data-ttu-id="c3ab7-103">この手順で、厳密な名前を割り当てるし、で作成したリソース (スキーマ) を含むアセンブリを生成するプロジェクトをビルド[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-103">In this step, you assign a strong name and build the project to generate an assembly that contains the resources (the schema) that you created in [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span> <span data-ttu-id="c3ab7-104">またこれにより、これまでに完了した作業でコンパイル エラーがないこと。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-104">This also ensures that there are no compile errors in the work you have completed so far.</span></span>  
  
### <a name="to-sign-the-btahl7-project"></a><span data-ttu-id="c3ab7-105">BTAHL7 プロジェクトに署名するには</span><span class="sxs-lookup"><span data-stu-id="c3ab7-105">To sign the BTAHL7 Project</span></span>  
  
1.  <span data-ttu-id="c3ab7-106">ソリューション エクスプ ローラーで右クリックして**BTAHL7 プロジェクト**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-106">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c3ab7-107">BTAHL7 プロジェクト プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-107">In the BTAHL7 Project Property Pages dialog box, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="c3ab7-108">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4.  <span data-ttu-id="c3ab7-109">アセンブリ キー ファイル ダイアログ ボックスを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk** (で作成した[手順 3: に厳密な名前を割り当てる、アセンブリ](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))、をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-109">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk** (as created in [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)), and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="c3ab7-110">クリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-110">Click **OK** to save changes.</span></span>  
  
### <a name="to-build-the-btahl7-project"></a><span data-ttu-id="c3ab7-111">BTAHL7 プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="c3ab7-111">To build the BTAHL7 Project</span></span>  
  
- <span data-ttu-id="c3ab7-112">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="c3ab7-113"> DLL ファイルにアセンブリをコンパイルし、保存します、 \<*ドライブ*\>: \Tutorial\BTAHL7V22Common\Bin\Development フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-113"> compiles the assembly into a DLL file and saves it in the \<*drive*\>:\Tutorial\BTAHL7V22Common\Bin\Development folder.</span></span>  
  
  <span data-ttu-id="c3ab7-114">続行する[手順 8: BizTalk マッパーでマップの作成](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3ab7-114">Proceed to [Step 8: Create a Map with BizTalk Mapper](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ab7-115">参照</span><span class="sxs-lookup"><span data-stu-id="c3ab7-115">See Also</span></span>  
 [<span data-ttu-id="c3ab7-116">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c3ab7-116">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)