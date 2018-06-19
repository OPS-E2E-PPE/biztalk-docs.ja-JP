---
title: フィルター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8dad59d-4a47-4794-bbf9-cba02fe7f0bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efa69998b1782f42d7730744fd88534d26a87835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245802"
---
# <a name="filter"></a><span data-ttu-id="99f65-102">[フィルター]</span><span class="sxs-lookup"><span data-stu-id="99f65-102">Filter</span></span>
<span data-ttu-id="99f65-103">`Filter` 要素には、`Expression` または `true` に評価される `false` が含まれています。これに基づいて、イベントは処理またはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="99f65-103">The `Filter` element contains an `Expression` that evaluates to `true` or `false` and determines when an event should be processed or skipped.</span></span>  
  
## <a name="format"></a><span data-ttu-id="99f65-104">Format</span><span class="sxs-lookup"><span data-stu-id="99f65-104">Format</span></span>  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a><span data-ttu-id="99f65-105">解説</span><span class="sxs-lookup"><span data-stu-id="99f65-105">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="99f65-106">例</span><span class="sxs-lookup"><span data-stu-id="99f65-106">Example</span></span>  
 <span data-ttu-id="99f65-107">次の例は、イベントに関連付けられたワークフローのユーザー キーが "DocumentUrl" と等しい場合に `true` に評価されるフィルタを定義します。</span><span class="sxs-lookup"><span data-stu-id="99f65-107">The following example defines a filter that evaluates to `true` when the user key for the workflow associated with the event equals "DocumentUrl":</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99f65-108">参照</span><span class="sxs-lookup"><span data-stu-id="99f65-108">See Also</span></span>  
 [<span data-ttu-id="99f65-109">インターセプタ OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="99f65-109">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)