---
title: BizTalk プロジェクトに含まれる BizTalk Namespace 参照について |Microsoft ドキュメント
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
ms.openlocfilehash: 820e15eb3524713dfd7d3f86311ca262fde191d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225178"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a><span data-ttu-id="b0659-102">BizTalk プロジェクト内の BizTalk 名前空間参照について</span><span class="sxs-lookup"><span data-stu-id="b0659-102">About BizTalk Namespace References Included in BizTalk Projects</span></span>
<span data-ttu-id="b0659-103">新しい BizTalk プロジェクトを追加すると、既定で次の名前空間が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0659-103">When you add a new BizTalk project, the following namespaces are included by default:</span></span>  
  
-   <span data-ttu-id="b0659-104">**Microsoft.BizTalk.DefaultPipelines**</span><span class="sxs-lookup"><span data-stu-id="b0659-104">**Microsoft.BizTalk.DefaultPipelines**</span></span>  
  
-   <span data-ttu-id="b0659-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span><span class="sxs-lookup"><span data-stu-id="b0659-105">**Microsoft.BizTalk.GlobalPropertySchemas**</span></span>  
  
-   <span data-ttu-id="b0659-106">**システム**</span><span class="sxs-lookup"><span data-stu-id="b0659-106">**System**</span></span>  
  
-   <span data-ttu-id="b0659-107">**System.Xml**</span><span class="sxs-lookup"><span data-stu-id="b0659-107">**System.Xml**</span></span>  
  
 <span data-ttu-id="b0659-108">また、新しい参照および Web 参照をプロジェクトに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0659-108">You can also add new references and Web references to your project.</span></span> <span data-ttu-id="b0659-109">使用して追加する方法についての参照を**プロジェクト**] メニューの [を参照してください[Visual Studio を使って](../core/using-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0659-109">For more information about adding references using the **Project** menu, see [Using Visual Studio](../core/using-visual-studio.md).</span></span> <span data-ttu-id="b0659-110">Web 参照を追加する方法については、次を参照してください。 [Web 参照を追加する](../core/adding-web-references.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0659-110">For information about adding Web references, see [Adding Web References](../core/adding-web-references.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b0659-111">既定の参照は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="b0659-111">Do not remove the default references.</span></span> <span data-ttu-id="b0659-112">既定の参照を削除すると、プロジェクト内の BizTalk アイテムを参照するときに問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0659-112">If you remove the default references, you might encounter problems when referencing BizTalk items in your project.</span></span> <span data-ttu-id="b0659-113">ソリューション エクスプローラーで既定の参照を復元できます。</span><span class="sxs-lookup"><span data-stu-id="b0659-113">You can restore default references in Solution Explorer.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b0659-114">BizTalk プロジェクトが別のアセンブリを参照したときに、そのアセンブリが更新されている場合、その更新または変更は BizTalk プロジェクトに自動的には反映されません。</span><span class="sxs-lookup"><span data-stu-id="b0659-114">If your BizTalk project references another assembly, and that assembly is updated, the updates or changes are not automatically picked up in your BizTalk project.</span></span> <span data-ttu-id="b0659-115">ソリューション エクスプローラーで期限切れの参照を削除してから、参照を追加する必要があります (アセンブリの再参照)。</span><span class="sxs-lookup"><span data-stu-id="b0659-115">You should remove the outdated reference in Solution Explorer, and then add the reference back (re-reference the assembly).</span></span> <span data-ttu-id="b0659-116">または、ソリューションを閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="b0659-116">Alternatively, you can close your solution and reopen it.</span></span> <span data-ttu-id="b0659-117">いずれの場合も、参照されるアセンブリの最新の更新がプロジェクトで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b0659-117">In either case, the latest updates to the referenced assembly are available to your project.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0659-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0659-118">In This Section</span></span>  
  
-   [<span data-ttu-id="b0659-119">Microsoft.BizTalk.DefaultPipelines の参照</span><span class="sxs-lookup"><span data-stu-id="b0659-119">Microsoft.BizTalk.DefaultPipelines Reference</span></span>](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [<span data-ttu-id="b0659-120">Microsoft.BizTalk.GlobalPropertySchemas 参照</span><span class="sxs-lookup"><span data-stu-id="b0659-120">Microsoft.BizTalk.GlobalPropertySchemas Reference</span></span>](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [<span data-ttu-id="b0659-121">システムのリファレンス</span><span class="sxs-lookup"><span data-stu-id="b0659-121">System Reference</span></span>](../core/system-reference.md)  
  
-   [<span data-ttu-id="b0659-122">System.Xml 参照</span><span class="sxs-lookup"><span data-stu-id="b0659-122">System.Xml Reference</span></span>](../core/system-xml-reference.md)