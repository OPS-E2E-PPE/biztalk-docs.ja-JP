---
title: リンクの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10050c28-0944-4073-afd2-54cd6c8d79a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9926a7bdd890f75935014a79ff3994230c2378c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015699"
---
# <a name="configuring-links"></a><span data-ttu-id="d8195-102">リンクの構成</span><span class="sxs-lookup"><span data-stu-id="d8195-102">Configuring Links</span></span>

## <a name="overview"></a><span data-ttu-id="d8195-103">概要</span><span class="sxs-lookup"><span data-stu-id="d8195-103">Overview</span></span>
<span data-ttu-id="d8195-104">リンクにはプロパティがあり、表示されているグリッド ページでリンクを選択すると、これらのプロパティが [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8195-104">Links have properties that are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window when a link is selected in the displayed grid page.</span></span> <span data-ttu-id="d8195-105">参照リンクに関連付けられているプロパティについては、**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8195-105">For reference information about the properties associated with links, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="source-target-and-label"></a><span data-ttu-id="d8195-106">ソース、ターゲット、およびラベル</span><span class="sxs-lookup"><span data-stu-id="d8195-106">Source, target and label</span></span>  
 <span data-ttu-id="d8195-107">マップ内のリンクは次のプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d8195-107">The following properties configure links in a map:</span></span>  
  
- <span data-ttu-id="d8195-108">**ソース リンク**します。</span><span class="sxs-lookup"><span data-stu-id="d8195-108">**Source Links**.</span></span> <span data-ttu-id="d8195-109">使用する、**ソース リンク**プロパティを出力インスタンス メッセージの構築に使用される入力インスタンス メッセージからのデータの性質を構成します。</span><span class="sxs-lookup"><span data-stu-id="d8195-109">You use the **Source Links** property to configure the nature of the data from an input instance message that will be used to construct the output instance message.</span></span> <span data-ttu-id="d8195-110">既定 (最も一般的な選択) では、入力インスタンス メッセージの要素または属性の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8195-110">The default, and most common choice, is to use the element or attribute value from the input instance message.</span></span> <span data-ttu-id="d8195-111">他の選択肢としては、入力インスタンス メッセージの要素または属性の名前の使用などがあります。</span><span class="sxs-lookup"><span data-stu-id="d8195-111">Other choices are possible, including the use of the name of the element or attribute from the input instance message.</span></span> <span data-ttu-id="d8195-112">このプロパティは、使用可能な選択肢の詳細については、**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8195-112">For more information about this property and its available choices, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="d8195-113">**ターゲット リンク**します。</span><span class="sxs-lookup"><span data-stu-id="d8195-113">**Target Links**.</span></span> <span data-ttu-id="d8195-114">使用する、**ターゲット リンク**プロパティを BizTalk マッパーがノード階層レベルを照合する方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="d8195-114">You use the **Target Links** property to configure how BizTalk Mapper will match node-hierarchy levels.</span></span> <span data-ttu-id="d8195-115">既定では、送信元スキーマの階層がフラット化されて、出力インスタンス メッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8195-115">By default, source schema hierarchies are flattened as the output instance message is created.</span></span> <span data-ttu-id="d8195-116">また階層を維持して、リンクを上から順に一致させるか、下から順に一致させるかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8195-116">You can also choose to have hierarchies preserved, matching links from either the top down or from the bottom up.</span></span> <span data-ttu-id="d8195-117">このプロパティは、使用可能な選択肢の詳細については、**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8195-117">For more information about this property and its available choices, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="d8195-118">**ラベル**します。</span><span class="sxs-lookup"><span data-stu-id="d8195-118">**Label**.</span></span> <span data-ttu-id="d8195-119">使用する、**ラベル**プロパティを既定で使用される XPath 値よりも、リンクのわかりやすい名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="d8195-119">You use the **Label** property to create a more readable name for the link than the XPath value that is used by default.</span></span> <span data-ttu-id="d8195-120">このプロパティを構成すると、テーブルドリブン ループの入力としてリンクを使用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="d8195-120">Configuring this property is especially helpful when the link is used as an input for table-driven looping.</span></span> <span data-ttu-id="d8195-121">このプロパティは、使用可能な選択肢とテーブルドリブン ループについての詳細については、**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8195-121">For more information about this property and its available choices, and about table-driven looping, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="d8195-122">参照してください[テーブル ループ functoid およびテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="d8195-122">Also see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md), respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8195-123">参照</span><span class="sxs-lookup"><span data-stu-id="d8195-123">See Also</span></span>  
  [<span data-ttu-id="d8195-124">リンクのプロパティを編集する方法</span><span class="sxs-lookup"><span data-stu-id="d8195-124">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)