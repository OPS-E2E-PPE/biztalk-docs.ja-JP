---
title: GetServiceContractCallPoint |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53ebac10c1d690f47ab79c12affa3505b22f2e49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345191"
---
# <a name="getservicecontractcallpoint"></a><span data-ttu-id="1cff1-102">GetServiceContractCallPoint</span><span class="sxs-lookup"><span data-stu-id="1cff1-102">GetServiceContractCallPoint</span></span>
<span data-ttu-id="1cff1-103">現在のサービス コントラクト呼び出しポイントの名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="1cff1-103">Pushes the name of the current service contract call point onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cff1-104">構文</span><span class="sxs-lookup"><span data-stu-id="1cff1-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cff1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1cff1-105">Parameters</span></span>  
 <span data-ttu-id="1cff1-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="1cff1-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="1cff1-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="1cff1-107">Pushed Value</span></span>  
 <span data-ttu-id="1cff1-108">現在のコントラクト呼び出しポイントを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="1cff1-108">String containing the current contract call point.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cff1-109">コメント</span><span class="sxs-lookup"><span data-stu-id="1cff1-109">Remarks</span></span>  
 <span data-ttu-id="1cff1-110">Windows Communication Framework のサービスは、サービス コントラクトの有効期間中のさまざまなポイントで傍受できます。</span><span class="sxs-lookup"><span data-stu-id="1cff1-110">A Windows Communication Framework service can be intercepted at different points in the lifetime of the service contract.</span></span> <span data-ttu-id="1cff1-111">これらのポイントは、`System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint` 列挙体によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1cff1-111">These locations are defined by the `System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint` enumeration:</span></span>  
  
|<span data-ttu-id="1cff1-112">コントラクト呼び出しポイント</span><span class="sxs-lookup"><span data-stu-id="1cff1-112">Contract call point</span></span>|<span data-ttu-id="1cff1-113">説明</span><span class="sxs-lookup"><span data-stu-id="1cff1-113">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="1cff1-114">ClientReply</span><span class="sxs-lookup"><span data-stu-id="1cff1-114">ClientReply</span></span>|<span data-ttu-id="1cff1-115">クライアント応答呼び出しポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-115">Client reply call point.</span></span>|  
|<span data-ttu-id="1cff1-116">ClientRequest</span><span class="sxs-lookup"><span data-stu-id="1cff1-116">ClientRequest</span></span>|<span data-ttu-id="1cff1-117">クライアント要求呼び出しポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-117">Client request call point.</span></span>|  
|<span data-ttu-id="1cff1-118">ClientFault</span><span class="sxs-lookup"><span data-stu-id="1cff1-118">ClientFault</span></span>|<span data-ttu-id="1cff1-119">クライアント違反ポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-119">Client fault point.</span></span>|  
|<span data-ttu-id="1cff1-120">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="1cff1-120">ServiceReply</span></span>|<span data-ttu-id="1cff1-121">サービス応答呼び出しポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-121">Service reply call point.</span></span>|  
|<span data-ttu-id="1cff1-122">ServiceRequest</span><span class="sxs-lookup"><span data-stu-id="1cff1-122">ServiceRequest</span></span>|<span data-ttu-id="1cff1-123">サービス要求呼び出しポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-123">Service request call point.</span></span>|  
|<span data-ttu-id="1cff1-124">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="1cff1-124">ServiceFault</span></span>|<span data-ttu-id="1cff1-125">サービス違反ポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-125">Service fault point.</span></span>|  
|<span data-ttu-id="1cff1-126">CallbackRequest</span><span class="sxs-lookup"><span data-stu-id="1cff1-126">CallbackRequest</span></span>|<span data-ttu-id="1cff1-127">コールバック要求呼び出しポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-127">Callback request call point.</span></span>|  
|<span data-ttu-id="1cff1-128">CallbackReply</span><span class="sxs-lookup"><span data-stu-id="1cff1-128">CallbackReply</span></span>|<span data-ttu-id="1cff1-129">コールバック応答呼び出しポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-129">Callback reply call point.</span></span>|  
|<span data-ttu-id="1cff1-130">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="1cff1-130">CallbackFault</span></span>|<span data-ttu-id="1cff1-131">コールバック違反ポイントです。</span><span class="sxs-lookup"><span data-stu-id="1cff1-131">Callback fault point.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1cff1-132">例</span><span class="sxs-lookup"><span data-stu-id="1cff1-132">Example</span></span>  
 <span data-ttu-id="1cff1-133">次のサンプルには、クライアント応答状態にある特定の操作 ("Receive") を検出するように構成されたイベント フィルタ式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1cff1-133">The following sample contains an event filter expression configured to find a specific operation ("Receive") in the client reply state.</span></span> <span data-ttu-id="1cff1-134">この処理は、`GetOperationName`、`GetServiceContractCallPoint`、論理演算などの演算の組み合わせを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1cff1-134">This is done by using a combination of operations including `GetOperationName`, `GetServiceContractCallPoint`, and logical operations.</span></span>  
  
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
      <ic:Argument>ClientReply</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cff1-135">参照</span><span class="sxs-lookup"><span data-stu-id="1cff1-135">See Also</span></span>  
 [<span data-ttu-id="1cff1-136">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="1cff1-136">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)