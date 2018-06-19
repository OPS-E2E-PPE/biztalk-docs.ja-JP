---
title: XML ドキュメントのマージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML, documents
- process management solution tutorial, merging XML documents
ms.assetid: 444c983a-397a-4342-85e1-80bb152986d9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94684cd9bf1992a592efd7b97c46838c9c9a3134
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262642"
---
# <a name="merging-xml-documents"></a><span data-ttu-id="18814-102">XML ドキュメントのマージ</span><span class="sxs-lookup"><span data-stu-id="18814-102">Merging XML Documents</span></span>
<span data-ttu-id="18814-103">いずれかのメッセージを**OrderBroker**オーケストレーションを作成、SQL Server 履歴データベースを更新する 1 つです。</span><span class="sxs-lookup"><span data-stu-id="18814-103">One of the messages that the **OrderBroker** orchestration creates is one to update the SQL Server history database.</span></span> <span data-ttu-id="18814-104">このメッセージには、元の注文メッセージと注文メッセージのフィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="18814-104">This message contains fields from the order message as well as the original order message.</span></span> <span data-ttu-id="18814-105">元の注文は、このメッセージに文字列として表示されます。</span><span class="sxs-lookup"><span data-stu-id="18814-105">The original order appears in this message a string.</span></span> <span data-ttu-id="18814-106">これは、データベースの注文履歴のデータ型と一致します。</span><span class="sxs-lookup"><span data-stu-id="18814-106">This matches the data type for the order history in the database.</span></span>  
  
 <span data-ttu-id="18814-107">メッセージを取得し、文字列に変換して、マップと一緒に別のメッセージに配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="18814-107">It isn't possible to take a message, convert it to a string, and place it in another message with a map.</span></span> <span data-ttu-id="18814-108">オーケストレーションで使用するヘルパー関数**InsertOrderBody**、元の注文メッセージを文字列としてベースの履歴メッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="18814-108">The orchestration uses a helper function, **InsertOrderBody**, to add the original order message as a string to the base history message.</span></span>  
  
 <span data-ttu-id="18814-109">**OrderBroker**オーケストレーションは、マップを使用して**CSR_OrderRequest_To_SQLHistoryInsert**、注文メッセージ ベースの履歴メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="18814-109">The **OrderBroker** orchestration uses the map, **CSR_OrderRequest_To_SQLHistoryInsert**, to convert the order message into the base history message.</span></span> <span data-ttu-id="18814-110">属性として、注文の情報が表示されます、 **OrderLog**要素。</span><span class="sxs-lookup"><span data-stu-id="18814-110">The information for an order appears as attributes of an **OrderLog** element.</span></span> <span data-ttu-id="18814-111">元のメッセージは、この要素の別の属性として表示されます。</span><span class="sxs-lookup"><span data-stu-id="18814-111">The original message appears as another attribute of this element.</span></span>  
  
 <span data-ttu-id="18814-112">**InsertOrderBody**メソッド引数として、元の注文メッセージ ベースの履歴メッセージを受け取り、完成された履歴メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="18814-112">The **InsertOrderBody** method takes as arguments the original order message, the base history message, and returns the completed history message.</span></span> <span data-ttu-id="18814-113">次のコードは、文字列としてメッセージを挿入するメソッドの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="18814-113">The following code shows the portions of the method that inserts the message as a string:</span></span>  
  
```  
public static XmlDocument InsertOrderBody( XmlDocument orderDoc,   
                                    XmlDocument historyInsertDoc)  
{  
...  
    XmlNode root = historyInsertDoc.FirstChild;  
  
    //Create a new attribute.  
    XmlNode attr = historyInsertDoc.CreateNode(XmlNodeType.Attribute,  
                                     "OriginalMsg", root.NamespaceURI);  
    attr.Value = orderDoc.OuterXml;  
  
    try  
    {  
        // XPath expression not shown for formatting reasons and  
        // replaces ".." in the following code  
        XmlNode destnode = historyInsertDoc.SelectSingleNode("..");  
        //Add the attribute to the document.  
        destnode.Attributes.SetNamedItem(attr);  
    }  
...  
  
    return historyInsertDoc;  
}  
```  
  
 <span data-ttu-id="18814-114">両方の引数が受信したことを確認した後、 **InsertOrderBody**メソッドは、履歴更新メッセージのルート ノードを検索します。</span><span class="sxs-lookup"><span data-stu-id="18814-114">After verifying that it received both arguments, the **InsertOrderBody** method finds the root node of the history update message.</span></span> <span data-ttu-id="18814-115">これは、後、作成、ノードを含む、 **OriginalMsg**属性し、属性の値を元の注文メッセージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="18814-115">It then creates a node containing the **OriginalMsg** attribute and assigns the original order message to the attribute's value.</span></span> <span data-ttu-id="18814-116">この時点では、ノードは単に存在しているだけです。</span><span class="sxs-lookup"><span data-stu-id="18814-116">At this point, the node simply exists.</span></span> <span data-ttu-id="18814-117">ノードは、まだ要素の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="18814-117">It is not yet part of a element.</span></span>  
  
 <span data-ttu-id="18814-118">属性ノードを作成すると、このメソッドは、XPath 式で属性を追加するノードを検索します。</span><span class="sxs-lookup"><span data-stu-id="18814-118">After creating the attribute node, the method finds the node where it will attach the attribute using an XPath expression.</span></span> <span data-ttu-id="18814-119">ノードを検出すると、このメソッドは、ノードの Attributes コレクションに属性ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="18814-119">After it locates the node, the method adds the attribute node to the attributes collection of the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18814-120">ただし、 **OriginalMsg**属性は、ベースの履歴メッセージに最初に存在しません、これは、もちろん、スキーマで指定します。</span><span class="sxs-lookup"><span data-stu-id="18814-120">Although the **OriginalMsg** attribute does not initially exist in the base history message, it is, of course, specified in the schema.</span></span> <span data-ttu-id="18814-121">コードでメッセージに追加する XML 要素は、そのメッセージ用のスキーマで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18814-121">XML elements that you add to your messages in code should be specified in the schemas for those messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18814-122">参照</span><span class="sxs-lookup"><span data-stu-id="18814-122">See Also</span></span>  
 [<span data-ttu-id="18814-123">ビジネス プロセス管理ソリューションの実装の要点</span><span class="sxs-lookup"><span data-stu-id="18814-123">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)