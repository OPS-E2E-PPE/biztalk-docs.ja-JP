---
title: "識別フィールドを使用してインスタンス メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b8f3f77-5385-4294-b441-bcb28bdc51b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4dca22ff1b09a0d1cfb261a9d5726da8b1b17b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-processing-using-distinguished-fields"></a><span data-ttu-id="02998-102">識別フィールドを使用したインスタンス メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="02998-102">Instance Message Processing Using Distinguished Fields</span></span>
<span data-ttu-id="02998-103">使用してプロパティの昇格、**識別フィールド**メカニズムでは、プロパティ スキーマの作成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="02998-103">Promoting properties by using the **Distinguished Field** mechanism does not require the creation of a property schema.</span></span> <span data-ttu-id="02998-104">すべてのプロパティの昇格を使用すると、**プロパティの昇格**を使用してアクセスされる ダイアログ ボックス、**プロパティの昇格**のプロパティ、**スキーマ**内のノードメッセージ スキーマ、またはを使用して、**昇格 & #124 です。プロモーションを表示する**コマンドを**BizTalk**またはショートカット メニュー。</span><span class="sxs-lookup"><span data-stu-id="02998-104">As with all property promotion, you use the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node in message schemas, or by using the **Promote &#124; Show Promotions** command on the **BizTalk** or shortcut menus.</span></span>  
  
 <span data-ttu-id="02998-105">**プロパティの昇格** ダイアログ ボックスで、確認、**識別フィールド** ダイアログ ボックスの右側にあるタブが選択されています。</span><span class="sxs-lookup"><span data-stu-id="02998-105">In the **Promote Properties** dialog box, ensure the **Distinguished Fields** tab is selected in the right side of the dialog box.</span></span> <span data-ttu-id="02998-106">検索して選択 ダイアログ ボックスの左側にあるスキーマ ツリーのノードを展開し、**フィールド要素**ノードまたは**フィールド属性**識別フィールドとして昇格するノードし、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="02998-106">Then you expand the nodes in the schema tree on the left side of the dialog box to find and select the **Field Element** node or **Field Attribute** node that you want to promote as a distinguished field, and then click **Add**.</span></span> <span data-ttu-id="02998-107">操作手順については、プロパティを昇格させる**識別フィールド**を使用して、**プロパティの昇格**ダイアログ ボックスを参照してください[Distinguished としてメッセージ コンテキストへのデータのコピーフィールド](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)です。</span><span class="sxs-lookup"><span data-stu-id="02998-107">For step-by-step instructions about promoting properties to **Distinguished Fields** using the **Promote Properties** dialog, see [Copying Data to the Message Context as Distinguished Fields](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02998-108">昇格することも、**レコード**場合に限り、プロパティ スキーマで、[フィールド要素] ノードにノード、**コンテンツ タイプ**のプロパティ、**レコード**に設定されているノード**SimpleContent**です。</span><span class="sxs-lookup"><span data-stu-id="02998-108">You can also promote a **Record** node to a Field Element node in the property schema, but only if the **Content Type** property of the **Record** node is set to **SimpleContent**.</span></span>  
  
 <span data-ttu-id="02998-109">識別フィールドとして昇格されるプロパティのセットからノードを削除するには、上、昇格させたプロパティを選択、**識別フィールド**タブをクリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="02998-109">To remove a node from the set of properties being promoted as distinguished fields, select the promoted property on the **Distinguished Fields** tab, and click **Remove**.</span></span>  
  
 <span data-ttu-id="02998-110">識別フィールドのメカニズムを使ってプロパティを昇格させると、ルート要素の注釈サブ要素内に、XSD (XML Schema Definition) 言語のコードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="02998-110">When you promote properties by using the distinguished field mechanism, an XML Schema definition (XSD) language fragment is added within the annotation subelement of the root element.</span></span> <span data-ttu-id="02998-111">次の例は、識別フィールドのメカニズムを使って昇格させた 2 つのプロパティのコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="02998-111">In the following example, the fragment shows two properties promoted by using the distinguished field mechanism.</span></span>  
  
```  
<b:properties>  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field1']" />  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field5' and position()='1']" />  
</b:properties>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02998-112">参照</span><span class="sxs-lookup"><span data-stu-id="02998-112">See Also</span></span>  
 <span data-ttu-id="02998-113">[メッセージ処理を制御するメッセージの内容を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="02998-113">[Ways to Use Message Content to Control Message Processing](../core/ways-to-use-message-content-to-control-message-processing.md) </span></span>  
 [<span data-ttu-id="02998-114">識別フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="02998-114">How to Copy Data to the Message Context as Distinguished Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)