---
title: インターセプター BamActivity 要素 |Microsoft Docs
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
ms.openlocfilehash: 07d9929e1122f00ede80c1d3e7c9efff5a2f3fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382061"
---
# <a name="interceptor-bamactivity-element"></a><span data-ttu-id="2b7d7-102">インターセプタ BamActivity 要素</span><span class="sxs-lookup"><span data-stu-id="2b7d7-102">Interceptor BamActivity Element</span></span>
<span data-ttu-id="2b7d7-103">**BamActivity**要素が 1 つの BAM アクティビティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2b7d7-103">The **BamActivity** element defines a single BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="2b7d7-104">形式</span><span class="sxs-lookup"><span data-stu-id="2b7d7-104">Format</span></span>  
 <span data-ttu-id="2b7d7-105">`BamActivity`要素が含まれています、**名前**属性し、1 つ以上含む`OnEvent`要素。</span><span class="sxs-lookup"><span data-stu-id="2b7d7-105">The `BamActivity` element includes a **Name** attribute and contains one or more `OnEvent` elements.</span></span>  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a><span data-ttu-id="2b7d7-106">属性</span><span class="sxs-lookup"><span data-stu-id="2b7d7-106">Attributes</span></span>  
  
|<span data-ttu-id="2b7d7-107">属性名</span><span class="sxs-lookup"><span data-stu-id="2b7d7-107">Attribute name</span></span>|<span data-ttu-id="2b7d7-108">説明</span><span class="sxs-lookup"><span data-stu-id="2b7d7-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2b7d7-109">名前</span><span class="sxs-lookup"><span data-stu-id="2b7d7-109">Name</span></span>|<span data-ttu-id="2b7d7-110">BAM アクティビティのユーザー定義名。</span><span class="sxs-lookup"><span data-stu-id="2b7d7-110">User-defined name of the BAM activity.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b7d7-111">例</span><span class="sxs-lookup"><span data-stu-id="2b7d7-111">Example</span></span>  
 <span data-ttu-id="2b7d7-112">次の例には、"myorderworkflow"、単一の OnEvent とサンプル BamActivity にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b7d7-112">The following example contains a sample BamActivity for "MyOrderWorkflow" with a single OnEvent.</span></span>  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b7d7-113">参照</span><span class="sxs-lookup"><span data-stu-id="2b7d7-113">See Also</span></span>  
 <span data-ttu-id="2b7d7-114">[インターセプター EventSource 要素](../core/interceptor-eventsource-element.md) </span><span class="sxs-lookup"><span data-stu-id="2b7d7-114">[Interceptor EventSource Element](../core/interceptor-eventsource-element.md) </span></span>  
 [<span data-ttu-id="2b7d7-115">インターセプター OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="2b7d7-115">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)