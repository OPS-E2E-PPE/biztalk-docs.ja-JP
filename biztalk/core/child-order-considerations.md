---
title: "子の順序に関する注意事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0909a8d69f5079e493fbc579d6ef4b0ca56f9c61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="child-order-considerations"></a><span data-ttu-id="61b17-102">子の順序に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="61b17-102">Child Order Considerations</span></span>

## <a name="requirements-for-header-in-a-flat-file"></a><span data-ttu-id="61b17-103">フラット ファイルのヘッダーの要件</span><span class="sxs-lookup"><span data-stu-id="61b17-103">Requirements for header in a flat file</span></span>
<span data-ttu-id="61b17-104">設定するときに特別な考慮事項が適用される、区切られたフラット ファイルに関連する 2 つのシナリオがある、**子の順序**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="61b17-104">There are two scenarios related to delimited flat files for which special considerations apply when setting the **Child Order** property.</span></span> <span data-ttu-id="61b17-105">1 つ目のシナリオは、フラット ファイル ドキュメントにヘッダー、本文、およびトレーラー (省略可能) が含まれる状況に関連します。</span><span class="sxs-lookup"><span data-stu-id="61b17-105">The first such scenario concerns situations in which the flat file document has a header, a body, and optionally, a trailer.</span></span> <span data-ttu-id="61b17-106">このようなシナリオでは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="61b17-106">In these scenarios, you must observe the following requirements:</span></span>  
  
-   <span data-ttu-id="61b17-107">設定する必要があります、**子の順序**するヘッダーの (区切られた) ルート レコードのプロパティ**後置**です。</span><span class="sxs-lookup"><span data-stu-id="61b17-107">You must set the **Child Order** property of the (delimited) root record of the header to **Postfix**.</span></span>  
  
-   <span data-ttu-id="61b17-108">設定する必要があります、トレーラーが存在する場合、**子の順序**する本文の (区切られた) ルート レコードのプロパティ**後置**です。</span><span class="sxs-lookup"><span data-stu-id="61b17-108">If a trailer is present, you must set the **Child Order** property of the (delimited) root record of the body to **Postfix**.</span></span>  
  
-   <span data-ttu-id="61b17-109">設定することがあります、トレーラーが存在しない場合、**子の順序**する本文の (区切られた) ルート レコードのプロパティ**プレフィックス**、 **"挿入辞"**、または**後置**.</span><span class="sxs-lookup"><span data-stu-id="61b17-109">If a trailer is not present, you may set the **Child Order** property of the (delimited) root record of the body to **Prefix**, **InFix**, or **Postfix**.</span></span>  
  
-   <span data-ttu-id="61b17-110">設定することがあります、トレーラーが存在する場合、**子の順序**プロパティには、そのトレーラーの (区切られた) ルート レコード**プレフィックス**、 **"挿入辞"**、または**後置**.</span><span class="sxs-lookup"><span data-stu-id="61b17-110">If a trailer is present, you may set the **Child Order** property of the (delimited) root record of that trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  
  
-   <span data-ttu-id="61b17-111">設定することも、**子の順序**プロパティのヘッダー、ボディ、およびトレーラーの区切られた下位レコード**プレフィックス**、 **"挿入辞"**、または**後置**.</span><span class="sxs-lookup"><span data-stu-id="61b17-111">You may set the **Child Order** property of delimited subordinate records of the header, body, and trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  
  
 <span data-ttu-id="61b17-112">区切られたフラット ファイルの 2 番目のシナリオに関連して、**子の順序**プロパティは、期待どおりに、実行時コンポーネント、ノードのに従ってこのプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b17-112">The second scenario related to delimited flat files and the **Child Order** property is that this property must be set according to what the runtime components expect for the nodes.</span></span> <span data-ttu-id="61b17-113">正しい設定、**子の順序**プロパティが明らかでないルートとグループ ノードの場合は、次のシナリオに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="61b17-113">The correct setting for the **Child Order** property may not be apparent for root and group nodes, as illustrated in the following scenarios:</span></span>  
  
-   <span data-ttu-id="61b17-114">**ルート ノードです。**</span><span class="sxs-lookup"><span data-stu-id="61b17-114">**Root node.**</span></span> <span data-ttu-id="61b17-115">レコードと CR/LF の組み合わせで構成される構造の一般的なフラット ファイルを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="61b17-115">Consider a typical flat file whose structure consists of records followed by a CR/LF combination.</span></span> <span data-ttu-id="61b17-116">区切り記号によって、ファイル内のレコードが分割されます。また通常は、レコード、区切り記号、レコード、区切り記号といった順序になります。</span><span class="sxs-lookup"><span data-stu-id="61b17-116">The delimiter separates records in the file, and the sequence is typically record, delimiter, record, delimiter, and so on.</span></span> <span data-ttu-id="61b17-117">このような状況の区切り記号常にに従って、データに対応する、**子の順序**プロパティの設定**後置**です。</span><span class="sxs-lookup"><span data-stu-id="61b17-117">In this situation, the delimiter always follows the data, which corresponds to a **Child Order** property setting of **Postfix**.</span></span>  
  
-   <span data-ttu-id="61b17-118">**グループ ノード:**</span><span class="sxs-lookup"><span data-stu-id="61b17-118">**Group nodes.**</span></span> <span data-ttu-id="61b17-119">BizTalk Server および XSD 表記のスキーマに表示されるグループ ノードは、フラット ファイル表記のインスタンス メッセージでは、明示的に示されません。</span><span class="sxs-lookup"><span data-stu-id="61b17-119">The group nodes shown in the BizTalk Server and XSD representation of the schema are not explicitly present in the flat file representation of the instance message.</span></span> <span data-ttu-id="61b17-120">たとえば、品目ごとにレコードがまとめられている注文書 (PO) があり、1 つの PO で複数の品目を表すために、レコードが何度も繰り返されている場合を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="61b17-120">Consider a purchase order (PO) that contains a collection of records for each line item, and those records repeat numerous times to represent multiple line items in a single PO.</span></span> <span data-ttu-id="61b17-121">このようなメッセージのスキーマは、繰り返しセット (場合によっては概念) のコンテナーとして機能する LineItems というノードを含める可能性があります: フラット ファイル表記のインスタンス メッセージには、LineItems コンテナーはによって表される、本質的に概念適切な一連のデータと区切り記号です。インスタンス メッセージの XML 表記では、LineItems コンテナーの形式で明示的に存在する**LineItems** XML 内の要素。</span><span class="sxs-lookup"><span data-stu-id="61b17-121">The schema for such a message would likely include a node named LineItems to serve as the (sometimes conceptual) container for the repeating set: in the flat file representation of the instance message, the LineItems container is conceptual in nature, represented by the appropriate sequence of data and delimiters; in the XML representation of the instance message, the LineItems container is explicitly present in the form of a **LineItems** element in XML.</span></span>  
  
 <span data-ttu-id="61b17-122">ルート ノードおよび単一のグループ ノードだけを含むメッセージを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="61b17-122">Consider a message containing a root node and only one group node.</span></span> <span data-ttu-id="61b17-123">この場合、入力ストリームの最後の区切り記号がルート ノードのどの位置に属しているかを確認することは簡単です。</span><span class="sxs-lookup"><span data-stu-id="61b17-123">It is easy to see where the last delimiter in the input stream would belong to the root node.</span></span> <span data-ttu-id="61b17-124">これは、データ/区切り記号の組み合わせの単純な繰り返しによって、1 つ以上の品目レコードが表されると考えることができるためです。</span><span class="sxs-lookup"><span data-stu-id="61b17-124">Therefore, the data/delimiter sequence in the conceptual loop would merely be one or more line item records.</span></span> <span data-ttu-id="61b17-125">ここでは、複数の品目レコードが存在する場合にのみ、レコードを分割するための区切り記号が含まれることになります。</span><span class="sxs-lookup"><span data-stu-id="61b17-125">Only in the case where there are more than one line item records would there be a delimiter to separate them.</span></span> <span data-ttu-id="61b17-126">この場合、区切り記号の数は、区切られる項目セットの数よりも 1 個少なくなります。この区切り記号は、挿入辞と呼ばれる構造に含まれる、項目と項目の間に配置されます。</span><span class="sxs-lookup"><span data-stu-id="61b17-126">In that case, the number of delimiters is one less than the sets of things being delimited, and the delimiters are located between the delimited items in a structure known as Infix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b17-127">参照</span><span class="sxs-lookup"><span data-stu-id="61b17-127">See Also</span></span>  
-  [<span data-ttu-id="61b17-128">区切り記号付きレコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="61b17-128">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
-  <span data-ttu-id="61b17-129">**子の順序 (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="61b17-129">**Child Order (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>