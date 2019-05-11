---
title: プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fdfe475-d9b4-4cf9-898f-dbd7e719c27c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9297660504bc5fddf9faa6ae43060a6c2a96fc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385639"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a><span data-ttu-id="09535-102">プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="09535-102">How to Copy Data to the Message Context as Property Fields</span></span>
<span data-ttu-id="09535-103">プロパティとして昇格させることができます、**プロパティ フィールド**はるかとしてプロパティを昇格させると同様に、**識別フィールド**、使用することもでき、**クイック昇格**機能をプロセスを合理化します。</span><span class="sxs-lookup"><span data-stu-id="09535-103">You can promote a property as a **Property Field** in much the same way as promoting a property as a **Distinguished Field**, and you can also use the **Quick Promotion** feature to streamline the process.</span></span>  
  
 <span data-ttu-id="09535-104">選択した可能性があります**プロパティ フィールド**経由での昇格**識別フィールド**次の理由の上位変換。</span><span class="sxs-lookup"><span data-stu-id="09535-104">You might choose **Property Field** promotion over **Distinguished Field** promotion for the following reasons:</span></span>  
  
- <span data-ttu-id="09535-105">昇格させる値は 255 文字の制限が適用されるよりも短い**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="09535-105">The values you want to promote are shorter than the 255 character limitation that applies to **Property Fields**.</span></span>  
  
- <span data-ttu-id="09535-106">昇格させる値に対して、オーケストレーションの外部 (パイプラインやポートなど) からアクセスできるようにする必要がある。</span><span class="sxs-lookup"><span data-stu-id="09535-106">You need the values that you promote to be accessible outside of orchestrations, such as within pipelines or ports.</span></span>  
  
  <span data-ttu-id="09535-107">このトピックではプロパティとして昇格させる手順、**プロパティ フィールド**以下の方法の両方でします。</span><span class="sxs-lookup"><span data-stu-id="09535-107">This topic provides step-by-step instructions for promoting a property as a **Property Field** in both of these ways.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a><span data-ttu-id="09535-108">[プロパティの昇格] ダイアログ ボックスを使用してプロパティを [プロパティ フィールド] として昇格させるには</span><span class="sxs-lookup"><span data-stu-id="09535-108">To promote a property as a Property Field using the Promote Properties dialog box</span></span>  
  
1.  <span data-ttu-id="09535-109">必要に応じて、昇格させたプロパティ用の適切なプロパティ スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="09535-109">If necessary, create an appropriate property schema into which you will promote a property.</span></span> <span data-ttu-id="09535-110">プロパティ スキーマの作成手順については、次を参照してください。[プロパティ スキーマの作成](../core/how-to-create-property-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="09535-110">For step-by-step instructions for creating property schemas, see [Creating Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09535-111">この手順が不要になる場合は、既にプロパティ スキーマを作成し、適切な挿入**フィールド要素**ノードの子ノードとして、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="09535-111">This step might not be necessary if you have already created a property schema and inserted the appropriate **Field Element** nodes as child nodes of the **Schema** node.</span></span>  
  
2.  <span data-ttu-id="09535-112">BizTalk エディターでは、1 つまたは複数のプロパティを昇格するスキーマを開き、(最初の) を選択**フィールド要素**、**フィールド属性**、または**レコード**ノードとして昇格する、**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="09535-112">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09535-113">のみを昇格することができます**レコード**ノードにすることで単純なコンテンツのみを含めることが構成されている場合、 **Content-type**プロパティに設定**SimpleContent**します。</span><span class="sxs-lookup"><span data-stu-id="09535-113">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
3.  <span data-ttu-id="09535-114">選択したノードを右クリックし、をクリックして**昇格**、] をクリックし、 **[昇格の表示**します。</span><span class="sxs-lookup"><span data-stu-id="09535-114">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="09535-115">**プロパティの昇格**] ダイアログ ボックスの左側にあるスキーマ ツリーで選択した [選択したノードが表示されたダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="09535-115">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
4.  <span data-ttu-id="09535-116">**プロパティの昇格**ダイアログ ボックスで、**プロパティ フィールド**タブ。</span><span class="sxs-lookup"><span data-stu-id="09535-116">In the **Promote Properties** dialog box, select the **Property Fields** tab.</span></span>  
  
5.  <span data-ttu-id="09535-117">プロパティを昇格するプロパティ スキーマがあることを確認、**プロパティ スキーマの一覧**プロパティ フィールド タブにします。存在する場合は、手順 8. に進みます。</span><span class="sxs-lookup"><span data-stu-id="09535-117">Confirm that the property schema into which you want to promote a property is present in the **Property Schemas List** in the Property Fields tab. If it is present, skip to step 8.</span></span>  
  
6.  <span data-ttu-id="09535-118">**プロパティ スキーマの一覧**セクションで、、**フォルダー**アイコン。</span><span class="sxs-lookup"><span data-stu-id="09535-118">In the **Property Schemas List** section, click the **Folder** icon.</span></span> <span data-ttu-id="09535-119">**BizTalk 型の選択** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09535-119">The **BizTalk Type Picker** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="09535-120">**BizTalk 型の選択** ダイアログ ボックスで、(手順 1 で作成した可能性があります) を適切なプロパティ スキーマに移動し、そのスキーマを選択してクリックして**ok**します。</span><span class="sxs-lookup"><span data-stu-id="09535-120">In the **BizTalk Type Picker** dialog box, navigate to the appropriate property schema (that you may have created in step 1), select that schema, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09535-121">必要に応じて、適切な文字列を変更することで、プロパティ スキーマに関連付けられている名前空間プレフィックスを変更できます**プレフィックス**列フィールド。</span><span class="sxs-lookup"><span data-stu-id="09535-121">Optionally, you can change the namespace prefix associated with the property schema by changing the string in the appropriate **Prefix** column field.</span></span>  
  
8.  <span data-ttu-id="09535-122">左側にあるスキーマ ツリーで選択されている昇格するノードで、**プロパティの昇格**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="09535-122">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="09535-123">選択したノードがの末尾に追加して、許可されている場合、**プロパティ フィールドの一覧**上、**プロパティ フィールド**タブ。昇格できない場合は、その説明を示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09535-123">If allowed, the selected node is added to the end of the **Property Fields List** on the **Property Fields** tab. If not allowed, a message box provides an explanation.</span></span> <span data-ttu-id="09535-124">許可されていない場合、**追加**ボタンが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="09535-124">If not allowed, the **Add** button is not enabled.</span></span>  
  
9. <span data-ttu-id="09535-125">ダブルクリック**プロパティ**列のセルに追加した行を**プロパティ フィールドの一覧**、ボックスの一覧を選択し、**プロパティ スキーマ**と対応する**フィールド要素**選択したノードを昇格するノード。</span><span class="sxs-lookup"><span data-stu-id="09535-125">Double-click **Property** column cell for the row you just added to the **Property Fields List**, and then in the drop-down list, select the **Property Schema** and corresponding **Field Element** node into which you want to promote the selected node.</span></span> <span data-ttu-id="09535-126">ドロップダウン リストの値がある X 内のプロパティ スキーマの名前空間プレフィックスは、X:Y の形式、**プロパティ スキーマの一覧**、Y のノード名であり、**フィールド要素**そのプロパティ スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="09535-126">Drop-down list values have the form X:Y, where X is the namespace prefix of a property schema in the **Property Schemas List**, and Y is the node name of a **Field Element** node in that property schema.</span></span>  
  
     <span data-ttu-id="09535-127">ドロップダウン リストで、既定値は、最初にプロパティ スキーマ **(Field 要素)** がまだ昇格されていない、ノードは、すべての関連するプロパティ スキーマの間でアルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="09535-127">The default value in the drop-down list is the first property schema **(Field Element)** node that has not yet been promoted, sorted alphabetically across all relevant property schemas.</span></span> <span data-ttu-id="09535-128">多くの場合、この既定値は、指定したスキーマ ノードの昇格先となるプロパティ スキーマ ノードではないので、注意してください。</span><span class="sxs-lookup"><span data-stu-id="09535-128">This will rarely be the property schema node into which you intend to promote a given schema node.</span></span>  
  
10. <span data-ttu-id="09535-129">プロモーションの追加のノードを選択するをクリックすると、ダイアログ ボックスの左側にあるスキーマ ツリーで**追加**し選択するたびに 9 にステップを実行することです。</span><span class="sxs-lookup"><span data-stu-id="09535-129">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** and then performing step 9 after each selection.</span></span>  
  
11. <span data-ttu-id="09535-130">完了したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="09535-130">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="09535-131">昇格対象として選択したノードになった**プロパティ フィールド**、特定の関連付けられている**フィールド要素**プロパティ スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="09535-131">The nodes that you selected to promote are now **Property Fields** and are associated with a particular **Field Element** node in a property schema.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a><span data-ttu-id="09535-132">[クイック昇格] コマンドを使用してプロパティを [プロパティ フィールド] として昇格させるには</span><span class="sxs-lookup"><span data-stu-id="09535-132">To promote a property as a Property Field using the Quick Promotion command</span></span>  
  
1.  <span data-ttu-id="09535-133">BizTalk エディターでは、1 つまたは複数のプロパティを昇格するスキーマを開き、(最初の) を選択**フィールド要素**、**フィールド属性**、または**レコード**ノードとして昇格する、**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="09535-133">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09535-134">のみを昇格することができます**レコード**ノードにすることで単純なコンテンツのみを含めることが構成されている場合、 **Content-type**プロパティに設定**SimpleContent**します。</span><span class="sxs-lookup"><span data-stu-id="09535-134">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
2.  <span data-ttu-id="09535-135">選択したノードを右クリックし、をクリックして**昇格**、 をクリックし、**クイック昇格**します。</span><span class="sxs-lookup"><span data-stu-id="09535-135">Right-click the selected node, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
     <span data-ttu-id="09535-136">場合、既定のプロパティ スキーマで定義されている、**既定のプロパティ スキーマ名**プロパティを**プロパティ ページ**、関連するスキーマが存在しない をクリックする必要があります**OK**を既定のプロパティ スキーマを作成し、適切な構成の確認のダイアログ ボックスで**フィールド要素**プロパティの昇格に対応するノード。</span><span class="sxs-lookup"><span data-stu-id="09535-136">If the default property schema, as defined by the **Default Property Schema Name** property on the **Property Pages** for the relevant schema, does not exist, you must click **OK** in the confirmation dialog to create the default property schema and configure it with an appropriate **Field Element** node to accommodate your property promotion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09535-137">表示して管理を使用して昇格させたプロパティ、**クイック昇格**を開いて機能、**プロパティの昇格** ダイアログ ボックスをクリックして、**プロパティ フィールド**タブ。開始する手順について、**プロパティの昇格**ダイアログ ボックスを参照してください[プロパティの昇格 ダイアログ ボックスを開く](../core/how-to-open-the-promote-properties-dialog-box.md)します。</span><span class="sxs-lookup"><span data-stu-id="09535-137">You can view and manage properties promoted using the **Quick Promotions** feature by opening the **Promote Properties** dialog box and then clicking the **Property Fields** tab. For step-by-step instructions for opening the **Promote Properties** dialog box, see [Opening the Promote Properties Dialog Box](../core/how-to-open-the-promote-properties-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09535-138">参照</span><span class="sxs-lookup"><span data-stu-id="09535-138">See Also</span></span>  
 <span data-ttu-id="09535-139">[プロパティの昇格](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="09535-139">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="09535-140">[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="09535-140">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="09535-141">メッセージ処理を管理するためのメッセージの内容の使用方法</span><span class="sxs-lookup"><span data-stu-id="09535-141">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)