---
title: 識別フィールドのデータとしてメッセージ コンテキストにコピーする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd5708fb972c21c84ae70f258c46e2d4cbcced9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340122"
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a><span data-ttu-id="e3fbe-102">識別フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="e3fbe-102">How to Copy Data to the Message Context as Distinguished Fields</span></span>
<span data-ttu-id="e3fbe-103">このトピックではプロパティとして昇格させる手順、**識別フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-103">This topic provides step-by-step instructions for promoting a property as a **Distinguished Field**.</span></span>  
  
 <span data-ttu-id="e3fbe-104">選択した可能性があります**識別フィールド**経由での昇格**プロパティ フィールド**次の理由の上位変換。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-104">You might choose **Distinguished Field** promotion over **Property Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="e3fbe-105">**プロパティ フィールド**値は、長さが 255 文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-105">**Property Field** values are limited to 255 characters in length.</span></span>  
  
-   <span data-ttu-id="e3fbe-106">**プロパティ フィールド**値がデータベースに格納されよりも多くのオーバーヘッドがあるため**識別フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-106">**Property Field** values are stored in a database, and therefore have more overhead than **Distinguished Fields**.</span></span> <span data-ttu-id="e3fbe-107">**識別フィールド**追加のストレージが必要としないのエイリアスでは基本的には、 **XPath**を可能にするために複数のオーケストレーションがメッセージから直接、関連する値に簡単にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-107">**Distinguished Fields** do not require any additional storage; they are essentially an alias for an **XPath**, thereby allowing orchestrations to more easily access the relevant values directly from the message.</span></span>  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a><span data-ttu-id="e3fbe-108">プロパティを識別フィールドとして昇格させる</span><span class="sxs-lookup"><span data-stu-id="e3fbe-108">To promote a property as a Distinguished Field</span></span>  
  
1.  <span data-ttu-id="e3fbe-109">BizTalk エディターでは、1 つまたは複数のプロパティを昇格するスキーマを開き、(最初の) を選択**フィールド要素**、**フィールド属性**、または**レコード**ノードとして昇格する、**識別フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-109">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Distinguished Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3fbe-110">[レコード] ノードは、としては昇格されません**識別フィールド**が含まれているコンテンツの種類に関係なく、します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-110">Record nodes can never be promoted as **Distinguished Fields**, regardless of the type of content they contain.</span></span>  
  
2.  <span data-ttu-id="e3fbe-111">選択したノードを右クリックし、をクリックして**昇格**、] をクリックし、 **[昇格の表示**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-111">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="e3fbe-112">**プロパティの昇格**] ダイアログ ボックスの左側にあるスキーマ ツリーで選択した [選択したノードが表示されたダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-112">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
3.  <span data-ttu-id="e3fbe-113">**プロパティの昇格**ダイアログ ボックスで、**識別フィールド**タブ。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-113">In the **Promote Properties** dialog box, select the **Distinguished Fields** tab.</span></span>  
  
4.  <span data-ttu-id="e3fbe-114">左側にあるスキーマ ツリーで選択されている昇格するノードで、**プロパティの昇格**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-114">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="e3fbe-115">選択したノードを一覧に追加が許可されている場合、**識別フィールド**タブ。昇格できない場合は、その説明を示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-115">If allowed, the selected node is added to the list on the **Distinguished Fields** tab. If not allowed, a message box provides an explanation.</span></span>  
  
5.  <span data-ttu-id="e3fbe-116">プロモーションの追加のノードを選択するをクリックすると、ダイアログ ボックスの左側にあるスキーマ ツリーで**追加**選択後します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-116">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** after each selection.</span></span>  
  
6.  <span data-ttu-id="e3fbe-117">完了したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-117">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="e3fbe-118">昇格対象として選択したノードになった**識別フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="e3fbe-118">The nodes that you selected to promote are now **Distinguished Fields**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fbe-119">参照</span><span class="sxs-lookup"><span data-stu-id="e3fbe-119">See Also</span></span>  
 <span data-ttu-id="e3fbe-120">[プロパティの昇格](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e3fbe-120">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="e3fbe-121">[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e3fbe-121">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="e3fbe-122">メッセージ処理を管理するためのメッセージの内容の使用方法</span><span class="sxs-lookup"><span data-stu-id="e3fbe-122">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)