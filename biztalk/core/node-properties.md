---
title: ノードのプロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: d41f0f3b0fe0b302a763629b8777669b54f6cc86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264218"
---
# <a name="node-properties"></a><span data-ttu-id="5b06e-102">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-102">Node Properties</span></span>

## <a name="overview"></a><span data-ttu-id="5b06e-103">概要</span><span class="sxs-lookup"><span data-stu-id="5b06e-103">Overview</span></span>
<span data-ttu-id="5b06e-104">BizTalk エディターでノードのプロパティを調べたり設定したりする場合は、Visual Studio の [プロパティ] ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b06e-104">In BizTalk Editor, you examine and set node properties in the Visual Studio Properties window.</span></span> <span data-ttu-id="5b06e-105">スキーマ ツリー ビューで別の種類のノードを選択すると、それに応じたプロパティが [プロパティ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b06e-105">As you select different types of nodes in the schema tree view, different sets of properties are displayed in the Properties window.</span></span> <span data-ttu-id="5b06e-106">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では、これらのプロパティをカテゴリ別またはアルファベット順に表示できます。アルファベット順に表示した場合、カテゴリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5b06e-106">As is standard in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], these properties can be displayed either in categories or alphabetically with no indication of their categories.</span></span> <span data-ttu-id="5b06e-107">この設定は、[プロパティ] ウィンドウの上部にあるボタンを使って切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="5b06e-107">Use the standard buttons near the top of the Properties window to toggle this setting.</span></span>  
  
 <span data-ttu-id="5b06e-108">通常、ノードのプロパティは、XSD (XML Schema Definition) 言語では、対応する要素に関連付けられた属性および属性値として表されます (特にノードのプロパティが既定値以外に設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="5b06e-108">Node properties, especially when set to values other than their defaults, are generally represented in the XML Schema definition (XSD) language as attributes and attribute values associated with the corresponding element.</span></span> <span data-ttu-id="5b06e-109">たとえば、プロパティ設定されている場合の**Min Occurs**と**Max Occurs**プロパティで、いくつかの別のノード型、設定されている値に対して使用できる、の値として使用されます**minOccurs**と**maxOccurs**属性はそれぞれ、対象のノードが表す要素に関連付けられている、 **Min Occurs**と**Max発生**プロパティが設定されています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-109">For example, when properties are set for the **Min Occurs** and **Max Occurs** properties, which are available for several different node types, the values that are set are used as the values of the **minOccurs** and **maxOccurs** attributes, respectively, associated with the element that represents the node for which the **Min Occurs** and **Max Occurs** properties are being set.</span></span>  

## <a name="property-types"></a><span data-ttu-id="5b06e-110">プロパティの種類</span><span class="sxs-lookup"><span data-stu-id="5b06e-110">Property types</span></span>
 <span data-ttu-id="5b06e-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者向けリファレンスには、さまざまなノード型をカテゴリ別およびアルファベット順に整理されているプロパティのリファレンス セクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-111">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] developer reference contains a reference section for the properties of the various node types, organized by category and alphabetically.</span></span> <span data-ttu-id="5b06e-112">次の例は、各ノードの種類に関連付けられたプロパティをまとめています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-112">The following summarize the properties associated with each node type:</span></span>  
  
-   <span data-ttu-id="5b06e-113">スキーマ ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-113">Schema Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-114">[レコード] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-114">Record Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-115">[フィールド要素] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-115">Field Element Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-116">[フィールド属性] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-116">Field Attribute Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-117">[シーケンス グループ] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-117">Sequence Group Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-118">[グループの選択] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-118">Choice Group Node Properties</span></span> 
  
-   <span data-ttu-id="5b06e-119">[すべてのグループ] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-119">All Group Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-120">[属性グループ] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-120">Attribute Group Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-121">[すべての要素] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-121">Any Element Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-122">[すべての属性] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-122">Any Attribute Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-123">[Equivalent] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-123">Equivalent Node Properties</span></span>
  
-   <span data-ttu-id="5b06e-124">[Equivalent Child] ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-124">Equivalent Child Node Properties</span></span>

<span data-ttu-id="5b06e-125">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5b06e-125">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="5b06e-126">**ノードのプロパティ-アルファベット順**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]のすべてのさまざまな種類のノードに適用するいくつかのノードの各プロパティの個別の参照トピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-126">**Node Properties — Alphabetical Listings** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contains all of the individual reference topics for each node property, some of which apply to various types of nodes.</span></span> <span data-ttu-id="5b06e-127">各リファレンス トピックは、すべての種類のスキーマに適用される基本的なプロパティであるか、スキーマ エディター拡張機能 (フラット ファイル拡張機能など) に関連した特別なプロパティであるかによって分類されています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-127">The individual reference topics are categorized according to whether they are basic properties that apply to all types of schemas, or a specialized properties that are associated with a schema editor extension, such as the flat file extension.</span></span> <span data-ttu-id="5b06e-128">カテゴリ内では、各トピックがアルファベット順に記載されています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-128">Within these categories, they are listed alphabetically.</span></span>  
  
 <span data-ttu-id="5b06e-129">BizTalk エディターでは、スキーマ ツリーに含まれるノードのプロパティを、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウで確認または設定できます。</span><span class="sxs-lookup"><span data-stu-id="5b06e-129">BizTalk Editor uses the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window to enable you to examine and set the properties of the nodes in the schema tree.</span></span> <span data-ttu-id="5b06e-130">ここには、いくつかの特性などの特別な考慮事項 [プロパティ] ウィンドウでプロパティの操作がについて説明します、**ノード名**プロパティ間の依存関係の説明、プロパティとについての最大長は許可されている特定のプロパティまたはプロパティの型。</span><span class="sxs-lookup"><span data-stu-id="5b06e-130">This section describes some characteristics of working with properties in the Properties window, including special considerations for the **Node Name** property, an explanation of the interdependencies between properties, and information about the maximum lengths allowed for certain properties or types of properties.</span></span>  
  
 <span data-ttu-id="5b06e-131">また、特殊なノード プロパティに関する補足情報や、ノードのプロパティ全般に関連するその他の情報についても説明しています。</span><span class="sxs-lookup"><span data-stu-id="5b06e-131">The remainder of this section provides additional information about particular, special node properties and other information that applies generally to node properties.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5b06e-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="5b06e-132">Next steps</span></span>
  
-   [<span data-ttu-id="5b06e-133">ノード名プロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-133">Node Name Property</span></span>](../core/node-name-property.md)  
  
-   [<span data-ttu-id="5b06e-134">プロパティの相互依存性</span><span class="sxs-lookup"><span data-stu-id="5b06e-134">Property Interdependencies</span></span>](../core/property-interdependencies.md)  
  
-   [<span data-ttu-id="5b06e-135">追加のフラット ファイル プロパティ</span><span class="sxs-lookup"><span data-stu-id="5b06e-135">Additional Flat File Properties</span></span>](../core/additional-flat-file-properties.md)