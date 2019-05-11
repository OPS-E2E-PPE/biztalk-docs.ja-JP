---
title: ノードのプロパティを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c79eac-d9ba-45e2-a6e9-770b2bcb2067
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3bd08285230f48c44e75b7eca47a4c6038df413
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383904"
---
# <a name="how-to-set-node-properties"></a><span data-ttu-id="d28ee-102">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="d28ee-102">How to Set Node Properties</span></span>
<span data-ttu-id="d28ee-103">BizTalk スキーマにノードを挿入した後にするは、既定値からそのノードのプロパティを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d28ee-103">After inserting a node into a BizTalk schema, you will often need to change the properties of that node from their default values.</span></span> <span data-ttu-id="d28ee-104">ノードの種類ごとに異なる一連のプロパティ、および 1 つのプロパティの設定内でこれらのセットのいずれか、他のプロパティの可用性に影響ことができます。</span><span class="sxs-lookup"><span data-stu-id="d28ee-104">Each type of node has a distinct set of properties, and within one of those sets, the settings of one property can affect the availability of other properties.</span></span> <span data-ttu-id="d28ee-105">たとえば、設定する前に、**既定の囲み文字**のプロパティ、**スキーマ**ノードが設定する必要があります、**既定の囲み文字の種類**プロパティをいずれかの**文字**または**16 進数**のため、前者のプロパティを表す形式を確立します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-105">For example, before setting the **Default Wrap Character** property of the **Schema** node, you must set the **Default Wrap Character Type** property to either **Character** or **Hexadecimal**, thereby establishing the format in which you intend to represent the former property.</span></span> <span data-ttu-id="d28ee-106">さらに、どちらもこれらのプロパティが使用可能な全体も**解析**プロパティのカテゴリに属する、しない限り、**フラット ファイル拡張子**を使用して、**スキーマ エディター拡張機能**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d28ee-106">Further, neither of these properties is available, nor is the entire **Parse** property category to which they belong, unless **Flat File Extension** is enabled by using the **Schema Editor Extensions** property.</span></span>  

 <span data-ttu-id="d28ee-107">ノードのプロパティは、広範なサポートされる XML スキーマ定義 (XSD) 言語は、複雑にできます。</span><span class="sxs-lookup"><span data-stu-id="d28ee-107">Node properties are extensive and can be complex, as is the XML Schema definition (XSD) language that they support.</span></span> <span data-ttu-id="d28ee-108">ごく簡単に確認およびノードのプロパティの設定に関係する一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-108">This topic only briefly describes the general steps involved in examining and setting node properties.</span></span> <span data-ttu-id="d28ee-109">これらのプロパティの詳細については、情報を含むなどの既定値と値を許可するを参照してください、**スキーマ プロパティのリファレンス**します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-109">For detailed information about these properties, including, for example, information about their default and allowed values, see the **Schema Property Reference**.</span></span> <span data-ttu-id="d28ee-110">さらに多くな XSD 概念とこれらのノード プロパティのほとんどを基になる要素については、に関する情報を直接参照[Web 上の XSD](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-110">For even more detailed information about the XSD concepts and elements that underlie most of these node properties, refer directly to information about [XSD on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

<span data-ttu-id="d28ee-111">詳細については、これらのプロパティとスキーマのプロパティのリファレンスで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-111">More info on these properties, and the schema property reference [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

  
## <a name="examine-a-node-property-value"></a><span data-ttu-id="d28ee-112">ノード プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-112">Examine a node property value</span></span>  
  
1. <span data-ttu-id="d28ee-113">BizTalk エディターを調べるには、対象のプロパティを含むスキーマを開き、そのプロパティを含むノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-113">In BizTalk Editor, open the schema that contains the property you want to examine, and then select the node that contains that property.</span></span>  
  
2. <span data-ttu-id="d28ee-114">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d28ee-114">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3. <span data-ttu-id="d28ee-115">必要に応じて、関心のあるプロパティを検索する [プロパティ] ウィンドウをスクロールし、その値に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d28ee-115">If necessary, scroll the Properties window to find the property of interest, and note its value.</span></span>  
  
    <span data-ttu-id="d28ee-116">[プロパティ] ウィンドウの上部にあるボタンを使用するには、プロパティが並べ替えられている、それぞれのカテゴリ内でアルファベット順またはアルファベット順にせずに関係 (またはの表示) する方法を変更するカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="d28ee-116">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
## <a name="set-a-node-property-value"></a><span data-ttu-id="d28ee-117">ノードのプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-117">Set a node property value</span></span>  
  
1. <span data-ttu-id="d28ee-118">BizTalk エディターを設定するプロパティを含むスキーマを開き、そのプロパティを含むノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-118">In BizTalk Editor, open the schema that contains the property you want to set, and then select the node that contains that property.</span></span>  
  
2. <span data-ttu-id="d28ee-119">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d28ee-119">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3. <span data-ttu-id="d28ee-120">必要に応じて、目的のプロパティを検索する [プロパティ] ウィンドウをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="d28ee-120">If necessary, scroll the Properties window to find the property of interest.</span></span>  
  
    <span data-ttu-id="d28ee-121">[プロパティ] ウィンドウの上部にあるボタンを使用するには、プロパティが並べ替えられている、それぞれのカテゴリ内でアルファベット順またはアルファベット順にせずに関係 (またはの表示) する方法を変更するカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="d28ee-121">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
4. <span data-ttu-id="d28ee-122">値フィールドには、プロパティ名の右側には、プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-122">Set the value of the property in the value field, which is to the right of the property name.</span></span> <span data-ttu-id="d28ee-123">プロパティの型によっては、値を入力したり、[値] フィールドが選択されているときに表示されるドロップダウン リストから値を選択可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d28ee-123">Depending on the type of the property, you might type a value or choose a value from the drop-down list that is displayed when the value field is selected.</span></span> <span data-ttu-id="d28ee-124">一部のプロパティは、いずれかの操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-124">Some properties allow either operation.</span></span> <span data-ttu-id="d28ee-125">一部のプロパティは、省略記号を表示 (**.**) ボタンをより複雑なコレクションなどの値をダイアログ ボックスがクリックされたが開きますを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d28ee-125">Some properties display an ellipsis (**...**) button that when clicked opens a dialog box in which more complicated values, such as collections, can be set.</span></span>  
  
5. <span data-ttu-id="d28ee-126">プロパティの新しい値を入力した場合は、ENTER キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-126">If you have typed a new value for the property, finish by pressing ENTER.</span></span>  
  
##  <a name="clear-a-node-property-value"></a><span data-ttu-id="d28ee-127">ノード プロパティの値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="d28ee-127">Clear a node property value</span></span>  
  
1.  <span data-ttu-id="d28ee-128">目的のプロパティを含むノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-128">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="d28ee-129">[プロパティ] ウィンドウで、clear、プロパティ値を右クリックしておよびクリックするプロパティの値をダブルクリックします。**削除**します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-129">In the Properties window, double-click the property value that you want to clear, right-click the property value, and then click **Delete**.</span></span>  
  
## <a name="restore-a-node-property-to-its-default-value"></a><span data-ttu-id="d28ee-130">ノードのプロパティを既定値に復元します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-130">Restore a node property to its default value</span></span>  
  
1.  <span data-ttu-id="d28ee-131">目的のプロパティを含むノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-131">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="d28ee-132">[プロパティ] ウィンドウでクリックして、その既定値にリセットするプロパティ名を右クリックして**リセット**します。</span><span class="sxs-lookup"><span data-stu-id="d28ee-132">In the Properties window, right-click the property name that you want to reset to its default value, and then click **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28ee-133">参照</span><span class="sxs-lookup"><span data-stu-id="d28ee-133">See Also</span></span>  
 [<span data-ttu-id="d28ee-134">既存のノードの操作</span><span class="sxs-lookup"><span data-stu-id="d28ee-134">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)