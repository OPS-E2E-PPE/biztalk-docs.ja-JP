---
title: 削除 Namespace サンプルの動作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf5834b4-e0fd-4180-9d15-4cdd99f0f353
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e82e4f369d8db2230b44586cbb928ea57b27f462
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294522"
---
# <a name="how-the-remove-namespace-sample-works"></a><span data-ttu-id="3032e-102">削除 Namespace サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="3032e-102">How the Remove Namespace Sample Works</span></span>
<span data-ttu-id="3032e-103">2 番目と 3 番目のテストを使用して、**削除 Namespace**コンポーネント、 **NamespaceSampleSendPipeline**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="3032e-103">The second and third tests use the **Remove Namespace** component located in the **NamespaceSampleSendPipeline** pipeline.</span></span> <span data-ttu-id="3032e-104">これは、ルート ノードで、次のような名前空間でドキュメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="3032e-104">It takes as input a document with a namespace on the root node, such as the following:</span></span>  
  
```  
<ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2"   
    xmlns:ns0="http://schemas.microsoft.biztalk.esb.test.com/test">  
```  
  
 <span data-ttu-id="3032e-105">**削除 Namespace**コンポーネントは、単にこの名前空間を削除し、次に示すようにルート ノードの名前空間がないドキュメントを返します。</span><span class="sxs-lookup"><span data-stu-id="3032e-105">The **Remove Namespace** component simply removes this namespace and returns a document that does not have a root node namespace, as shown here:</span></span>  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```