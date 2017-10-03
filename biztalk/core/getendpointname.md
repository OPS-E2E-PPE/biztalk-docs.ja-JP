---
title: "GetEndpointName |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1567f0b4bceb756381c4033f3243ac7a58fda366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getendpointname"></a><span data-ttu-id="3c20d-102">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="3c20d-102">GetEndpointName</span></span>
<span data-ttu-id="3c20d-103">現在のインターセプタ エンドポイントの名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c20d-103">Pushes the name of the current interception endpoint onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c20d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c20d-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c20d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c20d-105">Parameters</span></span>  
 <span data-ttu-id="3c20d-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="3c20d-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="3c20d-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="3c20d-107">Pushed Value</span></span>  
 <span data-ttu-id="3c20d-108">現在のインターセプタ エンドポイント名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="3c20d-108">String containing the current interception endpoint name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c20d-109">解説</span><span class="sxs-lookup"><span data-stu-id="3c20d-109">Remarks</span></span>  
 <span data-ttu-id="3c20d-110">クライアント アプリケーションおよびサーバー アプリケーションは、App.config ファイルで指定されている同じエンドポイント名に対して異なる名前を返します。</span><span class="sxs-lookup"><span data-stu-id="3c20d-110">It is important to note that the client and server applications will return different names for the same endpoint name specified in the App.config files.</span></span>  
  
 <span data-ttu-id="3c20d-111">クライアント アプリケーションの場合、GetEndPointName 操作で取得されるエンドポイント名はバインド名で、その後にアンダースコアとコントラクト名が続きます。</span><span class="sxs-lookup"><span data-stu-id="3c20d-111">For client applications, the endpoint name retrieved by the GetEndPointName operation is the binding name followed by an underscore and the contract name.</span></span>  
  
 <span data-ttu-id="3c20d-112">たとえば、ServiceEndpoint の Name プロパティが設定されていないバインドが設定されている場合は、名前に設定されます\<*バインディング*> _\<*コントラクト*>。</span><span class="sxs-lookup"><span data-stu-id="3c20d-112">For example, if the Name property on ServiceEndpoint is not set but the binding is set, the name will be set to \<*binding*>_\<*contract*>.</span></span>  
  
 <span data-ttu-id="3c20d-113">バインディングと名前が設定されていない場合、Name プロパティに設定されます\<*コントラクト*>。</span><span class="sxs-lookup"><span data-stu-id="3c20d-113">If the name and binding are not set, the Name property will be set to \<*contract*>.</span></span>  
  
 <span data-ttu-id="3c20d-114">サーバー アプリケーションの場合、App.config ファイルで指定されているエンドポイント名が取得されます。</span><span class="sxs-lookup"><span data-stu-id="3c20d-114">For the service, the name retrieved is the endpoint name specified in the App.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c20d-115">例</span><span class="sxs-lookup"><span data-stu-id="3c20d-115">Example</span></span>  
 <span data-ttu-id="3c20d-116">次に例示するフィルタ式では、PurchaseOrder_EP エンドポイントの ServiceRequest コントラクト呼び出しポイントについて、受信操作のインターセプタを定義します。</span><span class="sxs-lookup"><span data-stu-id="3c20d-116">The following example filter expression defines an interception for the Receive operation for the ServiceRequest contract call point for the PurchaseOrder_EP endpoint.</span></span> <span data-ttu-id="3c20d-117">これは、次のような論理的な手順によって実行します。</span><span class="sxs-lookup"><span data-stu-id="3c20d-117">This is done in the following logical steps:</span></span>  
  
1.  <span data-ttu-id="3c20d-118">現在の操作名を "Receive" と比較し、結果 ("true" または "false") をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c20d-118">Compare the current operation name to "Receive" and push the result (true or false) onto the stack.</span></span>  
  
2.  <span data-ttu-id="3c20d-119">現在のサービス コントラクト呼び出しポイントを "ServiceRequest" と比較し、結果 ("true" または "false") をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c20d-119">Compare the current service contract call point to "ServiceRequest" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="3c20d-120">この段階で、スタックには 2 つのブール値が存在します。</span><span class="sxs-lookup"><span data-stu-id="3c20d-120">There are now two Boolean values on the stack.</span></span>  
  
3.  <span data-ttu-id="3c20d-121">ブール値を使用して、上記の手順の結果を比較**と**操作と、スタックにプッシュ結果。</span><span class="sxs-lookup"><span data-stu-id="3c20d-121">Compare the results of the preceding steps using a Boolean **And** operation and push the result on the stack.</span></span> <span data-ttu-id="3c20d-122">この段階で、スタックには 1 つのブール値が存在します。</span><span class="sxs-lookup"><span data-stu-id="3c20d-122">This leaves one Boolean value on the stack.</span></span>  
  
4.  <span data-ttu-id="3c20d-123">現在のエンドポイントを "PurchaseOrder_EP" と比較し、結果 ("true" または "false") をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c20d-123">Compare the current endpoint to "PurchaseOrder_EP" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="3c20d-124">この段階で、スタックには 2 つのブール値が存在します。</span><span class="sxs-lookup"><span data-stu-id="3c20d-124">There are now two Boolean values on the stack.</span></span>  
  
5.  <span data-ttu-id="3c20d-125">最後に、ブール値を使用して、スタック上の 2 つのブール値を比較**と**操作と、結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c20d-125">Finally, compare the two Boolean values on the stack using a Boolean **And** operation and push the result onto the stack.</span></span> <span data-ttu-id="3c20d-126">これにより、ブール値に対してエンドポイント比較の結果がチェックされ、操作名とコントラクト呼び出しポイントが一致すれば true、それ以外の場合は false が返されます。</span><span class="sxs-lookup"><span data-stu-id="3c20d-126">This checks the result of the endpoint comparison against a Boolean value, which is true if the operation name and contract call point successfully matched, and which is false otherwise.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ServiceRequest</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wcf:Operation Name="GetEndpointName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>PurchaseOrder_EP</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c20d-127">参照</span><span class="sxs-lookup"><span data-stu-id="3c20d-127">See Also</span></span>  
 [<span data-ttu-id="3c20d-128">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="3c20d-128">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)