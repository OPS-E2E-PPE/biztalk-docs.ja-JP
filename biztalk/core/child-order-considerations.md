---
title: 子の順序に関する注意事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ee4c9bf7fe2b6a43951032f5043489f73d94bde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357354"
---
# <a name="child-order-considerations"></a><span data-ttu-id="c2915-102">子の順序に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="c2915-102">Child Order Considerations</span></span>

## <a name="requirements-for-header-in-a-flat-file"></a><span data-ttu-id="c2915-103">フラット ファイルのヘッダーにするための要件</span><span class="sxs-lookup"><span data-stu-id="c2915-103">Requirements for header in a flat file</span></span>
<span data-ttu-id="c2915-104">設定するときに特別な考慮事項を適用する、区切られたフラット ファイルに関連する 2 つのシナリオがある、**子の順序**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c2915-104">There are two scenarios related to delimited flat files for which special considerations apply when setting the **Child Order** property.</span></span> <span data-ttu-id="c2915-105">このようなシナリオがフラット ファイル ドキュメントが、ヘッダー、本文、および必要に応じて、トレーラーである状況に関係する最初。</span><span class="sxs-lookup"><span data-stu-id="c2915-105">The first such scenario concerns situations in which the flat file document has a header, a body, and optionally, a trailer.</span></span> <span data-ttu-id="c2915-106">これらのシナリオで、次の要件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2915-106">In these scenarios, you must observe the following requirements:</span></span>  

- <span data-ttu-id="c2915-107">設定する必要があります、**子の順序**するヘッダーの (区切られた) ルート レコードのプロパティ**後置**します。</span><span class="sxs-lookup"><span data-stu-id="c2915-107">You must set the **Child Order** property of the (delimited) root record of the header to **Postfix**.</span></span>  

- <span data-ttu-id="c2915-108">設定する必要があります、トレーラーが存在する場合、**子の順序**プロパティ本体の (区切られた) ルート レコード**後置**します。</span><span class="sxs-lookup"><span data-stu-id="c2915-108">If a trailer is present, you must set the **Child Order** property of the (delimited) root record of the body to **Postfix**.</span></span>  

- <span data-ttu-id="c2915-109">設定することがあります、トレーラーが存在しない場合、**子の順序**プロパティ本体の (区切られた) ルート レコード**プレフィックス**、 **"挿入辞"**、または**後置**.</span><span class="sxs-lookup"><span data-stu-id="c2915-109">If a trailer is not present, you may set the **Child Order** property of the (delimited) root record of the body to **Prefix**, **InFix**, or **Postfix**.</span></span>  

- <span data-ttu-id="c2915-110">トレーラーが存在する場合は、設定、**子の順序**プロパティには、そのトレーラーの (区切られた) ルート レコード**プレフィックス**、 **"挿入辞"**、または**後置**.</span><span class="sxs-lookup"><span data-stu-id="c2915-110">If a trailer is present, you may set the **Child Order** property of the (delimited) root record of that trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  

- <span data-ttu-id="c2915-111">設定することがあります、**子の順序**ヘッダー、本文、およびトレーラーの区切られた下位レコード プロパティ**プレフィックス**、 **"挿入辞"**、または**後置**.</span><span class="sxs-lookup"><span data-stu-id="c2915-111">You may set the **Child Order** property of delimited subordinate records of the header, body, and trailer to **Prefix**, **InFix**, or **Postfix**.</span></span>  

  <span data-ttu-id="c2915-112">区切られたフラット ファイルの 2 番目のシナリオに関連して、**子の順序**プロパティは、ノードのランタイム コンポーネントの想定に従ってこのプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2915-112">The second scenario related to delimited flat files and the **Child Order** property is that this property must be set according to what the runtime components expect for the nodes.</span></span> <span data-ttu-id="c2915-113">正しい設定、**子の順序**プロパティが明らかでないルートとグループ ノードの場合、次のシナリオに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="c2915-113">The correct setting for the **Child Order** property may not be apparent for root and group nodes, as illustrated in the following scenarios:</span></span>  

- <span data-ttu-id="c2915-114">**ルート ノードです。**</span><span class="sxs-lookup"><span data-stu-id="c2915-114">**Root node.**</span></span> <span data-ttu-id="c2915-115">一般的なフラット ファイル構造を持つは、レコードと CR/LF の組み合わせで構成されていますを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c2915-115">Consider a typical flat file whose structure consists of records followed by a CR/LF combination.</span></span> <span data-ttu-id="c2915-116">区切り記号は、ファイル内のレコードを分離し、レコード、区切り記号、レコード、区切り記号、および具合に、シーケンスが通常はします。</span><span class="sxs-lookup"><span data-stu-id="c2915-116">The delimiter separates records in the file, and the sequence is typically record, delimiter, record, delimiter, and so on.</span></span> <span data-ttu-id="c2915-117">このような状況で、区切り記号常に依存してに対応するデータを**子の順序**プロパティの設定の**後置**します。</span><span class="sxs-lookup"><span data-stu-id="c2915-117">In this situation, the delimiter always follows the data, which corresponds to a **Child Order** property setting of **Postfix**.</span></span>  

- <span data-ttu-id="c2915-118">**グループ ノード:**</span><span class="sxs-lookup"><span data-stu-id="c2915-118">**Group nodes.**</span></span> <span data-ttu-id="c2915-119">スキーマの BizTalk Server および XSD 表記に示すように、グループ ノードのインスタンス メッセージのフラット ファイル表記で明示的に存在していません。</span><span class="sxs-lookup"><span data-stu-id="c2915-119">The group nodes shown in the BizTalk Server and XSD representation of the schema are not explicitly present in the flat file representation of the instance message.</span></span> <span data-ttu-id="c2915-120">行アイテムごとに、レコードのコレクションを格納する注文書 (PO) を考慮し、それらのレコードの繰り返しを 1 つの PO に複数の行項目を表す何度もします。</span><span class="sxs-lookup"><span data-stu-id="c2915-120">Consider a purchase order (PO) that contains a collection of records for each line item, and those records repeat numerous times to represent multiple line items in a single PO.</span></span> <span data-ttu-id="c2915-121">このようなメッセージのスキーマには、繰り返しの一連の (場合によっては概念) のコンテナーとして機能する LineItems というノードが含まれます可能性があります: フラット ファイル表記のインスタンス メッセージには、LineItems コンテナーはによって表される、本質的に概念データと区切り記号の適切な順序インスタンス メッセージの XML 表現、LineItems コンテナーの形式で明示的に存在する、 **LineItems** XML 内の要素。</span><span class="sxs-lookup"><span data-stu-id="c2915-121">The schema for such a message would likely include a node named LineItems to serve as the (sometimes conceptual) container for the repeating set: in the flat file representation of the instance message, the LineItems container is conceptual in nature, represented by the appropriate sequence of data and delimiters; in the XML representation of the instance message, the LineItems container is explicitly present in the form of a **LineItems** element in XML.</span></span>  

  <span data-ttu-id="c2915-122">ルート ノードと 1 つだけのグループ ノードを含むメッセージを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c2915-122">Consider a message containing a root node and only one group node.</span></span> <span data-ttu-id="c2915-123">ルート ノードへの入力ストリームの最後の区切り記号が属する場所を簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c2915-123">It is easy to see where the last delimiter in the input stream would belong to the root node.</span></span> <span data-ttu-id="c2915-124">そのため、概念のループでデータ/区切り記号シーケンスでは、1 つまたは複数の品目レコードがだけです。</span><span class="sxs-lookup"><span data-stu-id="c2915-124">Therefore, the data/delimiter sequence in the conceptual loop would merely be one or more line item records.</span></span> <span data-ttu-id="c2915-125">場合にのみ 1 つ以上の品目レコードがこれらを分離する区切り記号はあるがある場合。</span><span class="sxs-lookup"><span data-stu-id="c2915-125">Only in the case where there are more than one line item records would there be a delimiter to separate them.</span></span> <span data-ttu-id="c2915-126">ある場合は、区切り記号の数が 1 つ未満れるのセットと区切り記号が挿入辞と呼ばれる構造で区切られた項目の間に配置します。</span><span class="sxs-lookup"><span data-stu-id="c2915-126">In that case, the number of delimiters is one less than the sets of things being delimited, and the delimiters are located between the delimited items in a structure known as Infix.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c2915-127">参照</span><span class="sxs-lookup"><span data-stu-id="c2915-127">See Also</span></span>  
- [<span data-ttu-id="c2915-128">区切り記号付きレコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="c2915-128">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="c2915-129">**子の順序 (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c2915-129">**Child Order (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
