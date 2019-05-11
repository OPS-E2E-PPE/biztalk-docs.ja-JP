---
title: ノードのプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec003c92f374489d59986bb5324f66100adf9e63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323538"
---
# <a name="node-properties"></a><span data-ttu-id="7451c-102">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-102">Node Properties</span></span>

## <a name="overview"></a><span data-ttu-id="7451c-103">概要</span><span class="sxs-lookup"><span data-stu-id="7451c-103">Overview</span></span>
<span data-ttu-id="7451c-104">BizTalk エディターでは、するを調べるし、Visual Studio プロパティ ウィンドウでノードのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7451c-104">In BizTalk Editor, you examine and set node properties in the Visual Studio Properties window.</span></span> <span data-ttu-id="7451c-105">スキーマ ツリー ビューでさまざまな種類のノードを選択すると、異なるプロパティのセットは、[プロパティ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7451c-105">As you select different types of nodes in the schema tree view, different sets of properties are displayed in the Properties window.</span></span> <span data-ttu-id="7451c-106">Standard は[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、カテゴリ、またはそのカテゴリが示されないアルファベット順に、これらのプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7451c-106">As is standard in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], these properties can be displayed either in categories or alphabetically with no indication of their categories.</span></span> <span data-ttu-id="7451c-107">[プロパティ] ウィンドウの上部にある標準のボタンを使用して、この設定を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="7451c-107">Use the standard buttons near the top of the Properties window to toggle this setting.</span></span>  
  
 <span data-ttu-id="7451c-108">特にが既定値以外の値に設定すると、ノードのプロパティは、属性として、XML スキーマ定義 (XSD) 言語で表される通常と属性の対応する要素に関連付けられている値。</span><span class="sxs-lookup"><span data-stu-id="7451c-108">Node properties, especially when set to values other than their defaults, are generally represented in the XML Schema definition (XSD) language as attributes and attribute values associated with the corresponding element.</span></span> <span data-ttu-id="7451c-109">たとえば、プロパティ設定されている場合の**Min Occurs**と**Max Occurs**のプロパティは、いくつかの別のノードの種類、設定されている値で使用できますが、の値として使用される**minOccurs**と**maxOccurs**属性はそれぞれ、対象のノードが表す要素に関連付けられた、 **Min Occurs**と**Max発生した**プロパティが設定されています。</span><span class="sxs-lookup"><span data-stu-id="7451c-109">For example, when properties are set for the **Min Occurs** and **Max Occurs** properties, which are available for several different node types, the values that are set are used as the values of the **minOccurs** and **maxOccurs** attributes, respectively, associated with the element that represents the node for which the **Min Occurs** and **Max Occurs** properties are being set.</span></span>  

## <a name="property-types"></a><span data-ttu-id="7451c-110">プロパティの型</span><span class="sxs-lookup"><span data-stu-id="7451c-110">Property types</span></span>
 <span data-ttu-id="7451c-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者向けリファレンスには、カテゴリ別およびアルファベット順に編成された、さまざまなノード型のプロパティのリファレンス セクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7451c-111">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] developer reference contains a reference section for the properties of the various node types, organized by category and alphabetically.</span></span> <span data-ttu-id="7451c-112">次に、各ノードの種類に関連付けられているプロパティをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="7451c-112">The following summarize the properties associated with each node type:</span></span>  
  
-   <span data-ttu-id="7451c-113">スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-113">Schema Node Properties</span></span>
  
-   <span data-ttu-id="7451c-114">レコード ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-114">Record Node Properties</span></span>
  
-   <span data-ttu-id="7451c-115">[フィールド要素] ノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-115">Field Element Node Properties</span></span>
  
-   <span data-ttu-id="7451c-116">[フィールド属性] ノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-116">Field Attribute Node Properties</span></span>
  
-   <span data-ttu-id="7451c-117">シーケンス グループ ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-117">Sequence Group Node Properties</span></span>
  
-   <span data-ttu-id="7451c-118">グループの選択 ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-118">Choice Group Node Properties</span></span> 
  
-   <span data-ttu-id="7451c-119">すべてのグループ ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-119">All Group Node Properties</span></span>
  
-   <span data-ttu-id="7451c-120">属性グループ ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-120">Attribute Group Node Properties</span></span>
  
-   <span data-ttu-id="7451c-121">すべての要素ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-121">Any Element Node Properties</span></span>
  
-   <span data-ttu-id="7451c-122">すべての属性ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-122">Any Attribute Node Properties</span></span>
  
-   <span data-ttu-id="7451c-123">等価のノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-123">Equivalent Node Properties</span></span>
  
-   <span data-ttu-id="7451c-124">[Equivalent Child] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-124">Equivalent Child Node Properties</span></span>

<span data-ttu-id="7451c-125">これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7451c-125">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="7451c-126">**ノードのプロパティ-アルファベット**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]すべてのノードの各プロパティのさまざまな種類のノードに適用うちいくつか個々 の参照トピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7451c-126">**Node Properties — Alphabetical Listings** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contains all of the individual reference topics for each node property, some of which apply to various types of nodes.</span></span> <span data-ttu-id="7451c-127">個々 の参照トピックは、すべての種類のスキーマに適用される基本的なプロパティまたはフラット ファイル拡張機能など、スキーマ エディタ拡張機能に関連付けられている特殊なプロパティは分類されます。</span><span class="sxs-lookup"><span data-stu-id="7451c-127">The individual reference topics are categorized according to whether they are basic properties that apply to all types of schemas, or a specialized properties that are associated with a schema editor extension, such as the flat file extension.</span></span> <span data-ttu-id="7451c-128">これらのカテゴリ内でこれらがアルファベット順の一覧します。</span><span class="sxs-lookup"><span data-stu-id="7451c-128">Within these categories, they are listed alphabetically.</span></span>  
  
 <span data-ttu-id="7451c-129">BizTalk エディターを使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを使用すると、確認し、スキーマ ツリーで、ノードのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7451c-129">BizTalk Editor uses the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window to enable you to examine and set the properties of the nodes in the schema tree.</span></span> <span data-ttu-id="7451c-130">このセクションの特別な考慮事項を含め、プロパティ ウィンドウでプロパティの操作の一部の特性を説明します、**ノード名**プロパティ間の相互依存関係の説明、プロパティとプロパティまたはプロパティの型については、最大の長さが特定の許可。</span><span class="sxs-lookup"><span data-stu-id="7451c-130">This section describes some characteristics of working with properties in the Properties window, including special considerations for the **Node Name** property, an explanation of the interdependencies between properties, and information about the maximum lengths allowed for certain properties or types of properties.</span></span>  
  
 <span data-ttu-id="7451c-131">このセクションの残りの部分では、特定、特殊なノードのプロパティに関する追加情報およびノードのプロパティに通常適用されるその他の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7451c-131">The remainder of this section provides additional information about particular, special node properties and other information that applies generally to node properties.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7451c-132">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7451c-132">Next steps</span></span>
  
-   [<span data-ttu-id="7451c-133">ノード名プロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-133">Node Name Property</span></span>](../core/node-name-property.md)  
  
-   [<span data-ttu-id="7451c-134">プロパティの相互依存性</span><span class="sxs-lookup"><span data-stu-id="7451c-134">Property Interdependencies</span></span>](../core/property-interdependencies.md)  
  
-   [<span data-ttu-id="7451c-135">追加のフラット ファイル プロパティ</span><span class="sxs-lookup"><span data-stu-id="7451c-135">Additional Flat File Properties</span></span>](../core/additional-flat-file-properties.md)