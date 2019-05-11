---
title: BizTalk プロジェクトに含まれる BizTalk Namespace 参照について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- System.Xml namespace
- Microsoft.BizTalk.GlobalPropertySchemas namespace
- namespaces, System.Xml namespace
- System namespace
- namespaces, System namespace
- namespaces, Microsoft.BizTalk.GlobalPropertySchemas namespace
- Microsoft.BizTalk.DefaultPipelines namespace
- projects, namespaces
- namespaces, warnings
- namespaces, Microsoft.BIzTalk.DefaultPipelines namespace
- namespaces
ms.assetid: cb642eac-7307-44f8-bbba-3ae364e11ea2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01344253a75033650b0e6326ff11420d0ed6fef5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362402"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a><span data-ttu-id="4673c-102">BizTalk プロジェクト内の BizTalk 名前空間参照について</span><span class="sxs-lookup"><span data-stu-id="4673c-102">About BizTalk Namespace References Included in BizTalk Projects</span></span>
<span data-ttu-id="4673c-103">新しい BizTalk プロジェクトを追加すると、既定で次の名前空間が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4673c-103">When you add a new BizTalk project, the following namespaces are included by default:</span></span>  
  
- <span data-ttu-id="4673c-104">**Microsoft.BizTalk.DefaultPipelines**</span><span class="sxs-lookup"><span data-stu-id="4673c-104">**Microsoft.BizTalk.DefaultPipelines**</span></span>  
  
- <span data-ttu-id="4673c-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span><span class="sxs-lookup"><span data-stu-id="4673c-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span></span>  
  
- <span data-ttu-id="4673c-106">**システム**</span><span class="sxs-lookup"><span data-stu-id="4673c-106">**System**</span></span>  
  
- <span data-ttu-id="4673c-107">**System.Xml**</span><span class="sxs-lookup"><span data-stu-id="4673c-107">**System.Xml**</span></span>  
  
  <span data-ttu-id="4673c-108">また、新しい参照および Web 参照をプロジェクトに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4673c-108">You can also add new references and Web references to your project.</span></span> <span data-ttu-id="4673c-109">追加の詳細については参照を使用して、**プロジェクト**] メニューの [を参照してください[Visual Studio を使って](../core/using-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="4673c-109">For more information about adding references using the **Project** menu, see [Using Visual Studio](../core/using-visual-studio.md).</span></span> <span data-ttu-id="4673c-110">Web 参照を追加する方法の詳細については、次を参照してください。 [Web 参照を追加する](../core/adding-web-references.md)します。</span><span class="sxs-lookup"><span data-stu-id="4673c-110">For information about adding Web references, see [Adding Web References](../core/adding-web-references.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4673c-111">既定の参照は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="4673c-111">Do not remove the default references.</span></span> <span data-ttu-id="4673c-112">既定の参照を削除すると、プロジェクト内の BizTalk アイテムを参照するときに問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4673c-112">If you remove the default references, you might encounter problems when referencing BizTalk items in your project.</span></span> <span data-ttu-id="4673c-113">ソリューション エクスプローラーで既定の参照を復元できます。</span><span class="sxs-lookup"><span data-stu-id="4673c-113">You can restore default references in Solution Explorer.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4673c-114">BizTalk プロジェクトが別のアセンブリを参照したときに、そのアセンブリが更新されている場合、その更新または変更は BizTalk プロジェクトに自動的には反映されません。</span><span class="sxs-lookup"><span data-stu-id="4673c-114">If your BizTalk project references another assembly, and that assembly is updated, the updates or changes are not automatically picked up in your BizTalk project.</span></span> <span data-ttu-id="4673c-115">ソリューション エクスプローラーで期限切れの参照を削除してから、参照を追加する必要があります (アセンブリの再参照)。</span><span class="sxs-lookup"><span data-stu-id="4673c-115">You should remove the outdated reference in Solution Explorer, and then add the reference back (re-reference the assembly).</span></span> <span data-ttu-id="4673c-116">または、ソリューションを閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="4673c-116">Alternatively, you can close your solution and reopen it.</span></span> <span data-ttu-id="4673c-117">いずれの場合も、参照されるアセンブリの最新の更新がプロジェクトで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="4673c-117">In either case, the latest updates to the referenced assembly are available to your project.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4673c-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4673c-118">In This Section</span></span>  
  
-   [<span data-ttu-id="4673c-119">Microsoft.BizTalk.DefaultPipelines の参照</span><span class="sxs-lookup"><span data-stu-id="4673c-119">Microsoft.BizTalk.DefaultPipelines Reference</span></span>](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [<span data-ttu-id="4673c-120">Microsoft.BizTalk.GlobalPropertySchemas 参照</span><span class="sxs-lookup"><span data-stu-id="4673c-120">Microsoft.BizTalk.GlobalPropertySchemas Reference</span></span>](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [<span data-ttu-id="4673c-121">System 参照</span><span class="sxs-lookup"><span data-stu-id="4673c-121">System Reference</span></span>](../core/system-reference.md)  
  
-   [<span data-ttu-id="4673c-122">System.Xml 参照</span><span class="sxs-lookup"><span data-stu-id="4673c-122">System.Xml Reference</span></span>](../core/system-xml-reference.md)