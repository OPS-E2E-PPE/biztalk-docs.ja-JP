---
title: GetOperationName |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f858269c-d412-43e3-85e1-398afa9375ab
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e22020add39840b0d2fe4c2fd88156321a18c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246138"
---
# <a name="getoperationname"></a><span data-ttu-id="9ee1d-102">GetOperationName</span><span class="sxs-lookup"><span data-stu-id="9ee1d-102">GetOperationName</span></span>
<span data-ttu-id="9ee1d-103">現在の操作の名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="9ee1d-103">Pushes the name of the current operation onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ee1d-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetOperationName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ee1d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ee1d-105">Parameters</span></span>  
 <span data-ttu-id="9ee1d-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="9ee1d-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="9ee1d-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="9ee1d-107">Pushed Value</span></span>  
 <span data-ttu-id="9ee1d-108">現在の操作の名前を格納している文字列。</span><span class="sxs-lookup"><span data-stu-id="9ee1d-108">String containing the name of the current operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ee1d-109">解説</span><span class="sxs-lookup"><span data-stu-id="9ee1d-109">Remarks</span></span>  
 <span data-ttu-id="9ee1d-110">GetOperationName を使用するときは、アプリケーションで呼び出される操作名と比較してください。</span><span class="sxs-lookup"><span data-stu-id="9ee1d-110">When using GetOperationName, make sure you compare the operation name as it is invoked by your application.</span></span> <span data-ttu-id="9ee1d-111">たとえば、サービス コントラクトの name 属性を使用してカスタム名を割り当てると、クライアントは、メソッドのカスタム名を使用して生成された既定のプロキシを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ee1d-111">For example, if you use the name attribute on a service contract to assign a custom name, the client will have its default proxy generated with the custom name for the method.</span></span> <span data-ttu-id="9ee1d-112">しかし、サーバー アプリケーションは、name 属性で指定された名前ではなく、対応する操作の実際のメソッド名を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ee1d-112">However, the server application will use the actual method names for the corresponding operations and not the one specified in the name attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ee1d-113">例</span><span class="sxs-lookup"><span data-stu-id="9ee1d-113">Example</span></span>  
 <span data-ttu-id="9ee1d-114">次の例では、`GetOperationName` を使用して、"AuthorizePayment" という名前の操作をフィルタ処理する式を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ee1d-114">In the following sample, `GetOperationName` is used to build an expression that filters for the operation named "AuthorizePayment".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>AuthorizePayment</ic:Argument>  
    </ic:Operation>  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ee1d-115">参照</span><span class="sxs-lookup"><span data-stu-id="9ee1d-115">See Also</span></span>  
 [<span data-ttu-id="9ee1d-116">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="9ee1d-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)