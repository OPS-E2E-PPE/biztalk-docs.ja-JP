---
title: "Windows Communication Foundation での操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6b5344b8fb2c5a5ba7a68b112adb50133198c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-in-windows-communication-foundation"></a><span data-ttu-id="afb01-102">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="afb01-102">Operations in Windows Communication Foundation</span></span>
<span data-ttu-id="afb01-103">このセクションでは、BAM WCF インターセプタによってサポートされているカスタム操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="afb01-103">This section contains the custom operations supported by the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="afb01-104">操作名要素に Action 属性が含まれている場合は、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="afb01-104">Note that if an operation name element contains an Action attribute:</span></span>  
  
1.  <span data-ttu-id="afb01-105">操作名は、クライアントとサーバーの両方の name 属性によって識別される名前です。</span><span class="sxs-lookup"><span data-stu-id="afb01-105">The operation name is the one identified by the name attribute for both the client and the server,</span></span>  
  
2.  <span data-ttu-id="afb01-106">応答パス (コールバック応答)、クライアント応答、およびサービス応答の場合、操作名は同じ属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="afb01-106">For reply paths (callback reply), client reply and service rely, the operation name is identified by the name attribute.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afb01-107">応答メッセージに含まれているノードには、name 属性によって指定された名前に単語 "Result" を追加した名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="afb01-107">Reply messages will have a node that is named by appending the word "Result" to the name specified by the name attribute.</span></span> <span data-ttu-id="afb01-108">XPath がこの命名規則に従っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afb01-108">You must ensure that the XPaths reflect this naming convention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afb01-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="afb01-109">In This Section</span></span>  
  
-   [<span data-ttu-id="afb01-110">AutoGenerateCorrelationToken</span><span class="sxs-lookup"><span data-stu-id="afb01-110">AutoGenerateCorrelationToken</span></span>](../core/autogeneratecorrelationtoken.md)  
  
-   [<span data-ttu-id="afb01-111">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="afb01-111">GetContextProperty</span></span>](../core/getcontextproperty1.md)  
  
-   [<span data-ttu-id="afb01-112">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="afb01-112">GetEndpointName</span></span>](../core/getendpointname.md)  
  
-   [<span data-ttu-id="afb01-113">GetOperationName</span><span class="sxs-lookup"><span data-stu-id="afb01-113">GetOperationName</span></span>](../core/getoperationname.md)  
  
-   [<span data-ttu-id="afb01-114">GetServiceContractCallPoint</span><span class="sxs-lookup"><span data-stu-id="afb01-114">GetServiceContractCallPoint</span></span>](../core/getservicecontractcallpoint.md)  
  
-   [<span data-ttu-id="afb01-115">XPath</span><span class="sxs-lookup"><span data-stu-id="afb01-115">XPath</span></span>](../core/xpath.md)