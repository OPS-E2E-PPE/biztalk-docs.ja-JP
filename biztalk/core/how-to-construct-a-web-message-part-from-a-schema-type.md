---
title: スキーマの種類から Web メッセージ部分を構築する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3a31fab048a1f6d7c52416b7e02b634803c0eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385748"
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a><span data-ttu-id="fde21-102">スキーマの種類から Web メッセージ部分を構築する方法</span><span class="sxs-lookup"><span data-stu-id="fde21-102">How to Construct a Web Message Part from a Schema Type</span></span>
<span data-ttu-id="fde21-103">使用して、スキーマの種類から Web メッセージ部分を作成、**変換**図形。</span><span class="sxs-lookup"><span data-stu-id="fde21-103">You create a Web message part from a schema type by using a **Transform** shape.</span></span> <span data-ttu-id="fde21-104">または、Web メッセージ部分を設定する .NET ヘルパー クラスを使用して、スキーマの種類から Web メッセージ部分を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fde21-104">Alternatively, you can create a Web message part from a schema type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="fde21-105">.NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="fde21-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a><span data-ttu-id="fde21-106">スキーマの種類から Web メッセージ部分を構築するには</span><span class="sxs-lookup"><span data-stu-id="fde21-106">To construct a Web message part from a schema type</span></span>  
  
1. <span data-ttu-id="fde21-107">新しいマップを追加します。</span><span class="sxs-lookup"><span data-stu-id="fde21-107">Add a new map.</span></span> <span data-ttu-id="fde21-108">マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="fde21-108">For information about creating maps, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
2. <span data-ttu-id="fde21-109">BizTalk マッパーでは、クリックして**送信先スキーマを開く**で、**送信先スキーマ**ペインのマップし、 **BizTalk 型の選択** ダイアログ ボックスで、展開、 **スキーマ**ノードが Web 参照の追加のスキーマを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-109">In BizTalk Mapper, click **Open Destination Schema** in the **Destination Schema** pane of the map and in the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the schema for the added Web reference, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fde21-110">Web 参照スキーマの形式が**\<プロジェクトの既定の名前空間\>.\<Web 参照名\>します。参照**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-110">The format of the Web reference schema is **\<project default namespace\>.\<Web reference name\>.Reference**.</span></span>  
  
3. <span data-ttu-id="fde21-111">**ターゲット スキーマのルート ノード** ダイアログ ボックスで、送信先スキーマのルート ノードを選択し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-111">In the **Root Node for Target Schema** dialog box, select a root node for the destination schema, and then click **OK**.</span></span> <span data-ttu-id="fde21-112">Web メッセージ部分の型のルート ノードを確認する方法の詳細については、次を参照してください。 [Web メッセージ部分の型を確認する方法](../core/how-to-determine-a-web-message-part-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="fde21-112">For more information about how to determine a root node for a Web message part type, see [How to Determine a Web Message Part Type](../core/how-to-determine-a-web-message-part-type.md).</span></span>  
  
4. <span data-ttu-id="fde21-113">をクリックして**ソース スキーマを開く**で、**送信元スキーマ**ペインのマップし、 **BizTalk 型の選択** ダイアログ ボックスで、展開、**スキーマ**ノードからのデータをマップするソース スキーマを選択およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-113">Click **Open Source Schema** in the **Source Schema** pane of the map and in the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the source schema to map data from, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="fde21-114">BizTalk マッパーで、送信元スキーマと送信先スキーマの間のリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="fde21-114">In the BizTalk Mapper, create links between the source schema and target schema.</span></span>  
  
6. <span data-ttu-id="fde21-115">既存のオーケストレーションを開きます (または、新しいオーケストレーションを作成) を開く、**ツールボックス**、 をクリックし、 **BizTalk オーケストレーション**タブ。</span><span class="sxs-lookup"><span data-stu-id="fde21-115">Open an existing orchestration (or create a new orchestration), open the **Toolbox**, and click the **BizTalk Orchestrations** tab.</span></span>  
  
7. <span data-ttu-id="fde21-116">ドラッグ、**メッセージの構築**オーケストレーションへの図形。</span><span class="sxs-lookup"><span data-stu-id="fde21-116">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
8. <span data-ttu-id="fde21-117">編集、**メッセージ構築**Web メッセージの種類用に作成したメッセージを含めるプロパティをインスタンスします。</span><span class="sxs-lookup"><span data-stu-id="fde21-117">Edit the **Message Constructed** property to include the message instance that yo created for the Web message type.</span></span>  
  
9. <span data-ttu-id="fde21-118">ドラッグ、**変換**図形の上に、**メッセージの構築**図形しをダブルクリックして開きます、**変換の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="fde21-118">Drag a **Transform** shape onto the **Construct Message** shape and double-click to open the **Transform Configuration** dialog box.</span></span>  
  
10. <span data-ttu-id="fde21-119">をクリックして、**既存のマップ**ボタンをクリックし、手順 1 で作成したマップを選択、**完全修飾マップ名**ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="fde21-119">Click the **Existing Map** button and select the map that you created in step one in the **Fully Qualified Map Name** list box.</span></span>  
  
11. <span data-ttu-id="fde21-120">**変換**ペインで、**ソース**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-120">In the **Transform** pane, select **Source**.</span></span> <span data-ttu-id="fde21-121">**送信元の変換**ウィンドウで、有効なメッセージが、リスト ボックスからインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="fde21-121">In the **Source Transform** pane, select a valid message instance from the list box.</span></span>  
  
12. <span data-ttu-id="fde21-122">**変換**ペインで、**先**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-122">In the **Transform** pane, select **Destination**.</span></span> <span data-ttu-id="fde21-123">**送信先の変換**ウィンドウで、Web メッセージ インスタンスをリスト ボックスから、クリックして選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fde21-123">In the **Destination Transform** pane, select the Web message instance from the list box, and then click **OK**.</span></span>  
  
    <span data-ttu-id="fde21-124">使用しての詳細については、**変換の構成**ダイアログ ボックスを参照してください[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="fde21-124">For more information about using the **Transform Configuration** dialog box, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span>  
  
    <span data-ttu-id="fde21-125">この手順を使用して、Web メソッドの応答メッセージ インスタンスを別の Web メッセージ インスタンスにマップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fde21-125">You can also use this procedure to map the Web method response message instance to another Web message instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde21-126">参照</span><span class="sxs-lookup"><span data-stu-id="fde21-126">See Also</span></span>  
 [<span data-ttu-id="fde21-127">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="fde21-127">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)