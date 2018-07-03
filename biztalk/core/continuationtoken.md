---
title: ContinuationToken |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0d36737ddd16e34ecfe4680c7660e16c99f676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001867"
---
# <a name="continuationtoken"></a><span data-ttu-id="0d93c-102">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="0d93c-102">ContinuationToken</span></span>
<span data-ttu-id="0d93c-103">接続トークンは、BAM インフラストラクチャ内の異種情報を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d93c-103">A continuation token is used to correlate heterogeneous information within the BAM infrastructure.</span></span> <span data-ttu-id="0d93c-104">次の種類のメッセージを構築するビジネス プロセスが考えられます。</span><span class="sxs-lookup"><span data-stu-id="0d93c-104">Consider a business process that constructs the following types of messages:</span></span>  
  
- <span data-ttu-id="0d93c-105">注文書番号により識別される注文書</span><span class="sxs-lookup"><span data-stu-id="0d93c-105">Purchase order identified by a purchase order number</span></span>  
  
- <span data-ttu-id="0d93c-106">販売注文番号により識別される販売注文</span><span class="sxs-lookup"><span data-stu-id="0d93c-106">Sales order identified by a sales order number</span></span>  
  
- <span data-ttu-id="0d93c-107">出荷指示番号により識別される出荷指示</span><span class="sxs-lookup"><span data-stu-id="0d93c-107">Shipping order identified by a shipping order number</span></span>  
  
  <span data-ttu-id="0d93c-108">このプロセスでは、次の 3 つの重要な識別子: 注文 ID、販売注文 ID、および注文 ID の配布の購入</span><span class="sxs-lookup"><span data-stu-id="0d93c-108">In this process, there are three important identifiers: purchase order ID, sales order ID and shipping order ID.</span></span> <span data-ttu-id="0d93c-109">これらの各識別子は、元の注文の有効期間において重要なイベントを示しますが、直接関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d93c-109">Each of these identifiers signals an important event in the lifetime of the original order, but they cannot be directly correlated.</span></span> <span data-ttu-id="0d93c-110">注文書に関連するイベントを追跡するには、BAM 追跡インフラストラクチャでイベントを正確に関連付けることができるようにするために、メッセージ間で共通する情報を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d93c-110">To track events related to a purchase order, the information that is common between the messages must be identified to help the BAM tracking infrastructure accurately correlate the events.</span></span>  
  
## <a name="format"></a><span data-ttu-id="0d93c-111">[形式]</span><span class="sxs-lookup"><span data-stu-id="0d93c-111">Format</span></span>  
 <span data-ttu-id="0d93c-112">接続トークンは、1 つの式要素と 1 つ以上の操作で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0d93c-112">A continuation token consists of an expression element and one or more operations:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a><span data-ttu-id="0d93c-113">コメント</span><span class="sxs-lookup"><span data-stu-id="0d93c-113">Remarks</span></span>  
 <span data-ttu-id="0d93c-114">次の一般的な演算は、ContinuationToken 式では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="0d93c-114">The following common operations are not allowed in ContinuationToken expressions:</span></span>  
  
- <span data-ttu-id="0d93c-115">And</span><span class="sxs-lookup"><span data-stu-id="0d93c-115">And</span></span>  
  
- <span data-ttu-id="0d93c-116">[等しい]</span><span class="sxs-lookup"><span data-stu-id="0d93c-116">Equals</span></span>  
  
  <span data-ttu-id="0d93c-117">[WF/WCF の Operations セクション ヘッダーには同様のチャートおよび必要に応じたその他のチャートが必要です。]</span><span class="sxs-lookup"><span data-stu-id="0d93c-117">[Operations section header in WF/WCF should have similar chart and other charts as needed]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d93c-118">例</span><span class="sxs-lookup"><span data-stu-id="0d93c-118">Example</span></span>  
 <span data-ttu-id="0d93c-119">この例では、WF プロセスの接続トークンが、`GetWorkflowProperty` を使用してワークフローから取得されます。</span><span class="sxs-lookup"><span data-stu-id="0d93c-119">In this example, a continuation token for a WF process is retrieved from the workflow by using `GetWorkflowProperty`.</span></span> <span data-ttu-id="0d93c-120">ここでは、カスタム コードを使用して、ワークフローにおける連続性のサポートを提供するよう開発者が決定しています。これはおそらく、接続トークンを確認するプロセスに 2 つまたは 3 つ以上の式が含まれるため、および外部データに依存する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="0d93c-120">Here the developer decided to provide support for continuation in the workflow by using custom code, probably because the process for determining the continuation token involves more than two or three expressions and may rely on external data.</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 <span data-ttu-id="0d93c-121">新しい WF アプリケーションまたは新しい WCF アプリケーションで、同様の機能を提供することを選択する場合があります。また、式操作を使用してトークンが簡単に確立する場合、追加のコードを記述せずに済みます。</span><span class="sxs-lookup"><span data-stu-id="0d93c-121">You may choose to provide similar functionality in your new WF or WCF applications or, if the token is easy to establish using expression operations, you can avoid writing additional code.</span></span>  
  
 <span data-ttu-id="0d93c-122">次の例を使用して、WCF プロセスの継続トークンを確立、 **XPath**の現在のメッセージからクレジット_カード番号を取得する操作と**定数**と**連結**に取得した番号を文字列"CID_"を付加する操作。</span><span class="sxs-lookup"><span data-stu-id="0d93c-122">The following example establishes a continuation token for a WCF process by using an **XPath** operation to retrieve the credit card number from the current message and the **constant** and **concatenate** operations to prepend the string "CID_" to the retrieved number:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CID_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//Purchase/Payment/CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d93c-123">参照</span><span class="sxs-lookup"><span data-stu-id="0d93c-123">See Also</span></span>  
 [<span data-ttu-id="0d93c-124">インターセプター OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="0d93c-124">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)