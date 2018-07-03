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
ms.openlocfilehash: 8e70a1c6797379c81c22d1fc38a503974d8ac795
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022544"
---
# <a name="how-to-set-node-properties"></a><span data-ttu-id="db5f4-102">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="db5f4-102">How to Set Node Properties</span></span>
<span data-ttu-id="db5f4-103">BizTalk スキーマにノードを挿入した後で、そのノードのプロパティを既定値から変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db5f4-103">After inserting a node into a BizTalk schema, you will often need to change the properties of that node from their default values.</span></span> <span data-ttu-id="db5f4-104">ノードの種類ごとに、固有の一連のプロパティがあります。また、これらのプロパティでは、あるプロパティの設定が他のプロパティの使用に影響を与える場合もあります。</span><span class="sxs-lookup"><span data-stu-id="db5f4-104">Each type of node has a distinct set of properties, and within one of those sets, the settings of one property can affect the availability of other properties.</span></span> <span data-ttu-id="db5f4-105">たとえば、設定する前に、**既定の囲み文字**のプロパティ、**スキーマ**ノードが設定する必要があります、**既定の囲み文字の種類**プロパティをいずれかの**文字**または**16 進数**のため、前者のプロパティを表す形式を確立します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-105">For example, before setting the **Default Wrap Character** property of the **Schema** node, you must set the **Default Wrap Character Type** property to either **Character** or **Hexadecimal**, thereby establishing the format in which you intend to represent the former property.</span></span> <span data-ttu-id="db5f4-106">さらに、どちらもこれらのプロパティが使用可能な全体も**解析**プロパティのカテゴリに属する、しない限り、**フラット ファイル拡張子**を使用して、**スキーマ エディター拡張機能**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="db5f4-106">Further, neither of these properties is available, nor is the entire **Parse** property category to which they belong, unless **Flat File Extension** is enabled by using the **Schema Editor Extensions** property.</span></span>  

 <span data-ttu-id="db5f4-107">ノードのプロパティは広範にわたり、複雑です。サポートする XSD (XML Schema Definition) 言語についても同様です。</span><span class="sxs-lookup"><span data-stu-id="db5f4-107">Node properties are extensive and can be complex, as is the XML Schema definition (XSD) language that they support.</span></span> <span data-ttu-id="db5f4-108">このトピックでは、ノードのプロパティの確認および設定に関する一般的な手順ついて、簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-108">This topic only briefly describes the general steps involved in examining and setting node properties.</span></span> <span data-ttu-id="db5f4-109">これらのプロパティの詳細については、情報を含むなどの既定値と値を許可するを参照してください、**スキーマ プロパティのリファレンス**します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-109">For detailed information about these properties, including, for example, information about their default and allowed values, see the **Schema Property Reference**.</span></span> <span data-ttu-id="db5f4-110">さらに多くな XSD 概念とこれらのノード プロパティのほとんどを基になる要素については、に関する情報を直接参照[Web 上の XSD](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-110">For even more detailed information about the XSD concepts and elements that underlie most of these node properties, refer directly to information about [XSD on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

<span data-ttu-id="db5f4-111">詳細については、これらのプロパティとスキーマのプロパティのリファレンスで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-111">More info on these properties, and the schema property reference [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

  
## <a name="examine-a-node-property-value"></a><span data-ttu-id="db5f4-112">ノード プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-112">Examine a node property value</span></span>  
  
1. <span data-ttu-id="db5f4-113">BizTalk エディターで、確認するプロパティを含むスキーマを開いて、そのプロパティが含まれるノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-113">In BizTalk Editor, open the schema that contains the property you want to examine, and then select the node that contains that property.</span></span>  
  
2. <span data-ttu-id="db5f4-114">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="db5f4-114">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3. <span data-ttu-id="db5f4-115">必要に応じて、目的のプロパティが表示されるように [プロパティ] ウィンドウをスクロールし、値を確認します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-115">If necessary, scroll the Properties window to find the property of interest, and note its value.</span></span>  
  
    <span data-ttu-id="db5f4-116">プロパティ ウィンドウの上部のボタンを使用して、プロパティの表示方法を、カテゴリ別でアルファベット順に、またはカテゴリに関係なく (カテゴリを表示しないで) アルファベット順に並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="db5f4-116">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
## <a name="set-a-node-property-value"></a><span data-ttu-id="db5f4-117">ノードのプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-117">Set a node property value</span></span>  
  
1. <span data-ttu-id="db5f4-118">BizTalk エディターで、設定するプロパティを含むスキーマを開いて、そのプロパティが含まれるノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-118">In BizTalk Editor, open the schema that contains the property you want to set, and then select the node that contains that property.</span></span>  
  
2. <span data-ttu-id="db5f4-119">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="db5f4-119">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3. <span data-ttu-id="db5f4-120">必要に応じて、目的のプロパティが表示されるように [プロパティ] ウィンドウをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="db5f4-120">If necessary, scroll the Properties window to find the property of interest.</span></span>  
  
    <span data-ttu-id="db5f4-121">プロパティ ウィンドウの上部のボタンを使用して、プロパティの表示方法を、カテゴリ別でアルファベット順に、またはカテゴリに関係なく (カテゴリを表示しないで) アルファベット順に並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="db5f4-121">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
4. <span data-ttu-id="db5f4-122">プロパティ名の右の値フィールドに、プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-122">Set the value of the property in the value field, which is to the right of the property name.</span></span> <span data-ttu-id="db5f4-123">プロパティの種類によって、値を入力する場合と、ドロップダウン リスト (値フィールドを選択すると表示される) から値を選択する場合があります。</span><span class="sxs-lookup"><span data-stu-id="db5f4-123">Depending on the type of the property, you might type a value or choose a value from the drop-down list that is displayed when the value field is selected.</span></span> <span data-ttu-id="db5f4-124">両方の操作ができるプロパティもあります。</span><span class="sxs-lookup"><span data-stu-id="db5f4-124">Some properties allow either operation.</span></span> <span data-ttu-id="db5f4-125">一部のプロパティは、省略記号を表示 (**.**) ボタンをより複雑なコレクションなどの値をダイアログ ボックスがクリックされたが開きますを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="db5f4-125">Some properties display an ellipsis (**...**) button that when clicked opens a dialog box in which more complicated values, such as collections, can be set.</span></span>  
  
5. <span data-ttu-id="db5f4-126">プロパティに新しい値を入力したら、最後に <localizedText>Enter</localizedText> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-126">If you have typed a new value for the property, finish by pressing ENTER.</span></span>  
  
##  <a name="clear-a-node-property-value"></a><span data-ttu-id="db5f4-127">ノード プロパティの値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="db5f4-127">Clear a node property value</span></span>  
  
1.  <span data-ttu-id="db5f4-128">目的のプロパティが含まれるノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-128">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="db5f4-129">[プロパティ] ウィンドウで、clear、プロパティ値を右クリックしておよびクリックするプロパティの値をダブルクリックします。**削除**します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-129">In the Properties window, double-click the property value that you want to clear, right-click the property value, and then click **Delete**.</span></span>  
  
## <a name="restore-a-node-property-to-its-default-value"></a><span data-ttu-id="db5f4-130">ノードのプロパティを既定値に復元します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-130">Restore a node property to its default value</span></span>  
  
1.  <span data-ttu-id="db5f4-131">目的のプロパティが含まれるノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-131">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="db5f4-132">[プロパティ] ウィンドウでクリックして、その既定値にリセットするプロパティ名を右クリックして**リセット**します。</span><span class="sxs-lookup"><span data-stu-id="db5f4-132">In the Properties window, right-click the property name that you want to reset to its default value, and then click **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5f4-133">参照</span><span class="sxs-lookup"><span data-stu-id="db5f4-133">See Also</span></span>  
 [<span data-ttu-id="db5f4-134">既存のノードの操作</span><span class="sxs-lookup"><span data-stu-id="db5f4-134">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)