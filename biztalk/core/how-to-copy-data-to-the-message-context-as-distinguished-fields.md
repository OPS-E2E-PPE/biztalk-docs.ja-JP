---
title: "識別フィールドのデータとしてメッセージ コンテキストにコピーする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea68bc0b83c5a8f886416107e1dc98ea8ad8d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a><span data-ttu-id="cacc3-102">識別フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="cacc3-102">How to Copy Data to the Message Context as Distinguished Fields</span></span>
<span data-ttu-id="cacc3-103">このトピックでは、プロパティとして昇格させる手順について、**識別フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="cacc3-103">This topic provides step-by-step instructions for promoting a property as a **Distinguished Field**.</span></span>  
  
 <span data-ttu-id="cacc3-104">できます**識別フィールド**経由で昇格**プロパティ フィールド**次の理由で昇格します。</span><span class="sxs-lookup"><span data-stu-id="cacc3-104">You might choose **Distinguished Field** promotion over **Property Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="cacc3-105">**プロパティ フィールド**値は 255 文字の長さに制限されます。</span><span class="sxs-lookup"><span data-stu-id="cacc3-105">**Property Field** values are limited to 255 characters in length.</span></span>  
  
-   <span data-ttu-id="cacc3-106">**プロパティ フィールド**値、データベースに格納されていて、したがってよりもオーバーヘッドが大きく**識別フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="cacc3-106">**Property Field** values are stored in a database, and therefore have more overhead than **Distinguished Fields**.</span></span> <span data-ttu-id="cacc3-107">**識別フィールド**; 追加のストレージを必要としないのエイリアスでは基本的には、 **XPath**ことのできるので、オーケストレーションをより簡単に、メッセージから直接、関連する値にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cacc3-107">**Distinguished Fields** do not require any additional storage; they are essentially an alias for an **XPath**, thereby allowing orchestrations to more easily access the relevant values directly from the message.</span></span>  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a><span data-ttu-id="cacc3-108">プロパティを識別フィールドとして昇格させるには</span><span class="sxs-lookup"><span data-stu-id="cacc3-108">To promote a property as a Distinguished Field</span></span>  
  
1.  <span data-ttu-id="cacc3-109">BizTalk エディターで、1 つ以上のプロパティを昇格させるスキーマを開き (最初の) を選択し、**フィールド要素**、**フィールド属性**、または**レコード**ノードとして昇格する、**識別フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="cacc3-109">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Distinguished Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cacc3-110">レコード ノードは、としては昇格されません**識別フィールド**が含まれているコンテンツの種類に関係なく、します。</span><span class="sxs-lookup"><span data-stu-id="cacc3-110">Record nodes can never be promoted as **Distinguished Fields**, regardless of the type of content they contain.</span></span>  
  
2.  <span data-ttu-id="cacc3-111">選択したノードを右クリックし、をクリックして**昇格**、クリックして**昇格の**します。</span><span class="sxs-lookup"><span data-stu-id="cacc3-111">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="cacc3-112">**プロパティの昇格**] ダイアログ ボックスの左側にあるスキーマ ツリーで選択した [選択したノードを示すダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="cacc3-112">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
3.  <span data-ttu-id="cacc3-113">**プロパティの昇格**ダイアログ ボックスで、**識別フィールド**タブです。</span><span class="sxs-lookup"><span data-stu-id="cacc3-113">In the **Promote Properties** dialog box, select the **Distinguished Fields** tab.</span></span>  
  
4.  <span data-ttu-id="cacc3-114">左側にあるスキーマ ツリーで選択されている昇格するノードで、**プロパティの昇格**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="cacc3-114">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="cacc3-115">許可された場合、選択したノードが一覧に追加、**識別フィールド**タブです。昇格できない場合は、その説明を示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cacc3-115">If allowed, the selected node is added to the list on the **Distinguished Fields** tab. If not allowed, a message box provides an explanation.</span></span>  
  
5.  <span data-ttu-id="cacc3-116">プロモーションの追加のノードをクリックすると、ダイアログ ボックスの左側にあるスキーマ ツリーで選択できる**追加**選択するたびにします。</span><span class="sxs-lookup"><span data-stu-id="cacc3-116">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** after each selection.</span></span>  
  
6.  <span data-ttu-id="cacc3-117">完了したら、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cacc3-117">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="cacc3-118">昇格対象として選択したノードは、今すぐ**識別フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="cacc3-118">The nodes that you selected to promote are now **Distinguished Fields**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacc3-119">参照</span><span class="sxs-lookup"><span data-stu-id="cacc3-119">See Also</span></span>  
 <span data-ttu-id="cacc3-120">[プロパティの昇格](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="cacc3-120">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="cacc3-121">[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="cacc3-121">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="cacc3-122">メッセージ処理を制御するメッセージの内容を使用する方法</span><span class="sxs-lookup"><span data-stu-id="cacc3-122">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)