---
title: インターセプタ BamActivity 要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dee61b4-83cd-4a22-b8a6-1c1a7ea3648b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43869922e46187c8b2e06155d525e428edd905
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257066"
---
# <a name="interceptor-bamactivity-element"></a><span data-ttu-id="27725-102">インターセプタ BamActivity 要素</span><span class="sxs-lookup"><span data-stu-id="27725-102">Interceptor BamActivity Element</span></span>
<span data-ttu-id="27725-103">**BamActivity**要素は、1 つの BAM アクティビティを定義します。</span><span class="sxs-lookup"><span data-stu-id="27725-103">The **BamActivity** element defines a single BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="27725-104">Format</span><span class="sxs-lookup"><span data-stu-id="27725-104">Format</span></span>  
 <span data-ttu-id="27725-105">`BamActivity`要素が含まれています、**名前**属性を 1 つ以上含む`OnEvent`要素。</span><span class="sxs-lookup"><span data-stu-id="27725-105">The `BamActivity` element includes a **Name** attribute and contains one or more `OnEvent` elements.</span></span>  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a><span data-ttu-id="27725-106">属性</span><span class="sxs-lookup"><span data-stu-id="27725-106">Attributes</span></span>  
  
|<span data-ttu-id="27725-107">属性名</span><span class="sxs-lookup"><span data-stu-id="27725-107">Attribute name</span></span>|<span data-ttu-id="27725-108">Description</span><span class="sxs-lookup"><span data-stu-id="27725-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="27725-109">名前</span><span class="sxs-lookup"><span data-stu-id="27725-109">Name</span></span>|<span data-ttu-id="27725-110">BAM アクティビティのユーザー定義名です。</span><span class="sxs-lookup"><span data-stu-id="27725-110">User-defined name of the BAM activity.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27725-111">例</span><span class="sxs-lookup"><span data-stu-id="27725-111">Example</span></span>  
 <span data-ttu-id="27725-112">次の例には、単一の OnEvent を持つ、"MyOrderWorkflow" というサンプルの BamActivity が含まれています。</span><span class="sxs-lookup"><span data-stu-id="27725-112">The following example contains a sample BamActivity for "MyOrderWorkflow" with a single OnEvent.</span></span>  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27725-113">参照</span><span class="sxs-lookup"><span data-stu-id="27725-113">See Also</span></span>  
 <span data-ttu-id="27725-114">[インターセプタ EventSource 要素](../core/interceptor-eventsource-element.md) </span><span class="sxs-lookup"><span data-stu-id="27725-114">[Interceptor EventSource Element](../core/interceptor-eventsource-element.md) </span></span>  
 [<span data-ttu-id="27725-115">インターセプタ OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="27725-115">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)