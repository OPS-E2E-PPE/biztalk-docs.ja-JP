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
ms.openlocfilehash: a5509fe9ec6b4d1966af84e56ca1b1571ebc3f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390273"
---
# <a name="continuationtoken"></a><span data-ttu-id="04d9e-102">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="04d9e-102">ContinuationToken</span></span>
<span data-ttu-id="04d9e-103">継続トークンは、BAM インフラストラクチャ内の異種情報を関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04d9e-103">A continuation token is used to correlate heterogeneous information within the BAM infrastructure.</span></span> <span data-ttu-id="04d9e-104">次の種類のメッセージを構築するビジネス プロセスを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="04d9e-104">Consider a business process that constructs the following types of messages:</span></span>  
  
- <span data-ttu-id="04d9e-105">注文書番号で識別される発注書</span><span class="sxs-lookup"><span data-stu-id="04d9e-105">Purchase order identified by a purchase order number</span></span>  
  
- <span data-ttu-id="04d9e-106">販売注文番号で識別される販売注文</span><span class="sxs-lookup"><span data-stu-id="04d9e-106">Sales order identified by a sales order number</span></span>  
  
- <span data-ttu-id="04d9e-107">出荷指示番号により識別される出荷指示</span><span class="sxs-lookup"><span data-stu-id="04d9e-107">Shipping order identified by a shipping order number</span></span>  
  
  <span data-ttu-id="04d9e-108">このプロセスでは、次の 3 つの重要な識別子: 注文 ID、販売注文 ID、および注文 ID の配布の購入</span><span class="sxs-lookup"><span data-stu-id="04d9e-108">In this process, there are three important identifiers: purchase order ID, sales order ID and shipping order ID.</span></span> <span data-ttu-id="04d9e-109">元の注文の有効期間中に重要なイベントを通知これらの各識別子が、直接関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="04d9e-109">Each of these identifiers signals an important event in the lifetime of the original order, but they cannot be directly correlated.</span></span> <span data-ttu-id="04d9e-110">注文書に関連するイベントを追跡するために、BAM 追跡インフラストラクチャが正確にイベントを関連付けるため、メッセージ間で共通の情報を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d9e-110">To track events related to a purchase order, the information that is common between the messages must be identified to help the BAM tracking infrastructure accurately correlate the events.</span></span>  
  
## <a name="format"></a><span data-ttu-id="04d9e-111">形式</span><span class="sxs-lookup"><span data-stu-id="04d9e-111">Format</span></span>  
 <span data-ttu-id="04d9e-112">継続トークンは、式の要素と 1 つまたは複数の操作で構成されます。</span><span class="sxs-lookup"><span data-stu-id="04d9e-112">A continuation token consists of an expression element and one or more operations:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a><span data-ttu-id="04d9e-113">コメント</span><span class="sxs-lookup"><span data-stu-id="04d9e-113">Remarks</span></span>  
 <span data-ttu-id="04d9e-114">次の一般的な操作は、ContinuationToken 式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="04d9e-114">The following common operations are not allowed in ContinuationToken expressions:</span></span>  
  
- <span data-ttu-id="04d9e-115">And</span><span class="sxs-lookup"><span data-stu-id="04d9e-115">And</span></span>  
  
- <span data-ttu-id="04d9e-116">[等しい]</span><span class="sxs-lookup"><span data-stu-id="04d9e-116">Equals</span></span>  
  
  <span data-ttu-id="04d9e-117">[WF/WCF の operations セクション ヘッダーに応じてが必要のようなグラフやその他のグラフ]</span><span class="sxs-lookup"><span data-stu-id="04d9e-117">[Operations section header in WF/WCF should have similar chart and other charts as needed]</span></span>  
  
## <a name="example"></a><span data-ttu-id="04d9e-118">例</span><span class="sxs-lookup"><span data-stu-id="04d9e-118">Example</span></span>  
 <span data-ttu-id="04d9e-119">この例では、ワークフローから、WF プロセスの継続トークンを取得を使用して`GetWorkflowProperty`します。</span><span class="sxs-lookup"><span data-stu-id="04d9e-119">In this example, a continuation token for a WF process is retrieved from the workflow by using `GetWorkflowProperty`.</span></span> <span data-ttu-id="04d9e-120">ここで継続トークンを確認するプロセスは、2 つまたは 3 つの式よりも多く、外部データに依存する可能性がありますので、おそらく、カスタム コードを使用して、ワークフローにおける連続性をサポートするよう、開発者が決定します。</span><span class="sxs-lookup"><span data-stu-id="04d9e-120">Here the developer decided to provide support for continuation in the workflow by using custom code, probably because the process for determining the continuation token involves more than two or three expressions and may rely on external data.</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 <span data-ttu-id="04d9e-121">新しい WF または WCF アプリケーションで同様の機能を提供することができます、または、トークンが簡単に式の操作を使用して確立する場合は、追加のコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d9e-121">You may choose to provide similar functionality in your new WF or WCF applications or, if the token is easy to establish using expression operations, you can avoid writing additional code.</span></span>  
  
 <span data-ttu-id="04d9e-122">次の例を使用して、WCF プロセスの継続トークンを確立、 **XPath**の現在のメッセージからクレジット_カード番号を取得する操作と**定数**と**連結**に取得した番号を文字列"CID_"を付加する操作。</span><span class="sxs-lookup"><span data-stu-id="04d9e-122">The following example establishes a continuation token for a WCF process by using an **XPath** operation to retrieve the credit card number from the current message and the **constant** and **concatenate** operations to prepend the string "CID_" to the retrieved number:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04d9e-123">参照</span><span class="sxs-lookup"><span data-stu-id="04d9e-123">See Also</span></span>  
 [<span data-ttu-id="04d9e-124">インターセプター OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="04d9e-124">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)