---
title: GetEndpointName |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e39dc97a5d1b12b2e9978f3833092355a47b0623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345086"
---
# <a name="getendpointname"></a><span data-ttu-id="bea62-102">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="bea62-102">GetEndpointName</span></span>
<span data-ttu-id="bea62-103">スタックに現在のインターセプタ エンドポイントの名前をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="bea62-103">Pushes the name of the current interception endpoint onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea62-104">構文</span><span class="sxs-lookup"><span data-stu-id="bea62-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bea62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bea62-105">Parameters</span></span>  
 <span data-ttu-id="bea62-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="bea62-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="bea62-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="bea62-107">Pushed Value</span></span>  
 <span data-ttu-id="bea62-108">現在のインターセプタ エンドポイント名を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="bea62-108">String containing the current interception endpoint name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bea62-109">コメント</span><span class="sxs-lookup"><span data-stu-id="bea62-109">Remarks</span></span>  
 <span data-ttu-id="bea62-110">クライアントとサーバー アプリケーションの App.config ファイルで指定された同じエンドポイント名ごとに異なる名前が返されることに注意してください。 重要です。</span><span class="sxs-lookup"><span data-stu-id="bea62-110">It is important to note that the client and server applications will return different names for the same endpoint name specified in the App.config files.</span></span>  
  
 <span data-ttu-id="bea62-111">クライアント アプリケーションは、GetEndPointName 操作によって取得されるエンドポイント名は、バインディング名がアンダー スコアとコントラクト名。</span><span class="sxs-lookup"><span data-stu-id="bea62-111">For client applications, the endpoint name retrieved by the GetEndPointName operation is the binding name followed by an underscore and the contract name.</span></span>  
  
 <span data-ttu-id="bea62-112">たとえば、バインディングが設定されているサービス エンドポイントの名前プロパティが設定されていない場合、名前が設定\<*バインド*\>_\<*コントラクト*\>.</span><span class="sxs-lookup"><span data-stu-id="bea62-112">For example, if the Name property on ServiceEndpoint is not set but the binding is set, the name will be set to \<*binding*\>_\<*contract*\>.</span></span>  
  
 <span data-ttu-id="bea62-113">バインディングと名前が設定されていない場合、Name プロパティに設定されます\<*コントラクト*\>します。</span><span class="sxs-lookup"><span data-stu-id="bea62-113">If the name and binding are not set, the Name property will be set to \<*contract*\>.</span></span>  
  
 <span data-ttu-id="bea62-114">サービスの場合は、取得した名前は、App.config ファイルで指定されたエンドポイント名前です。</span><span class="sxs-lookup"><span data-stu-id="bea62-114">For the service, the name retrieved is the endpoint name specified in the App.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bea62-115">例</span><span class="sxs-lookup"><span data-stu-id="bea62-115">Example</span></span>  
 <span data-ttu-id="bea62-116">次のフィルター式の例では、PurchaseOrder_EP エンドポイントの ServiceRequest コントラクト呼び出しポイントの受信操作のインターセプタを定義します。</span><span class="sxs-lookup"><span data-stu-id="bea62-116">The following example filter expression defines an interception for the Receive operation for the ServiceRequest contract call point for the PurchaseOrder_EP endpoint.</span></span> <span data-ttu-id="bea62-117">これは、次の論理手順で行います。</span><span class="sxs-lookup"><span data-stu-id="bea62-117">This is done in the following logical steps:</span></span>  
  
1.  <span data-ttu-id="bea62-118">現在の操作名を"Receive"を比較し、結果 (true または false) をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="bea62-118">Compare the current operation name to "Receive" and push the result (true or false) onto the stack.</span></span>  
  
2.  <span data-ttu-id="bea62-119">現在のサービス コントラクト呼び出しポイントを"ServiceRequest"を比較し、結果 (true または false) をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="bea62-119">Compare the current service contract call point to "ServiceRequest" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="bea62-120">スタック上に 2 つのブール値はようになりました。</span><span class="sxs-lookup"><span data-stu-id="bea62-120">There are now two Boolean values on the stack.</span></span>  
  
3.  <span data-ttu-id="bea62-121">ブール値を使用して、前の手順の結果を比較**と**操作と、スタックにプッシュの結果。</span><span class="sxs-lookup"><span data-stu-id="bea62-121">Compare the results of the preceding steps using a Boolean **And** operation and push the result on the stack.</span></span> <span data-ttu-id="bea62-122">これにより、1 つのブール値がスタックに残ります。</span><span class="sxs-lookup"><span data-stu-id="bea62-122">This leaves one Boolean value on the stack.</span></span>  
  
4.  <span data-ttu-id="bea62-123">現在のエンドポイントを"PurchaseOrder_EP"を比較し、結果 (true または false) をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="bea62-123">Compare the current endpoint to "PurchaseOrder_EP" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="bea62-124">スタック上に 2 つのブール値はようになりました。</span><span class="sxs-lookup"><span data-stu-id="bea62-124">There are now two Boolean values on the stack.</span></span>  
  
5.  <span data-ttu-id="bea62-125">最後に、ブール値を使用して、スタック上の 2 つのブール値を比較**と**操作と、結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="bea62-125">Finally, compare the two Boolean values on the stack using a Boolean **And** operation and push the result onto the stack.</span></span> <span data-ttu-id="bea62-126">コントラクトと操作の名前、ポイントが正常に呼び出す場合は true であるブール値に対してエンドポイント比較の結果が一致すると、およびそれ以外の場合は false、これを確認します。</span><span class="sxs-lookup"><span data-stu-id="bea62-126">This checks the result of the endpoint comparison against a Boolean value, which is true if the operation name and contract call point successfully matched, and which is false otherwise.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bea62-127">参照</span><span class="sxs-lookup"><span data-stu-id="bea62-127">See Also</span></span>  
 [<span data-ttu-id="bea62-128">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="bea62-128">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)