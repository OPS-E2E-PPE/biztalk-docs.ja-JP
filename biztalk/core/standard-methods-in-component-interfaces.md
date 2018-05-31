---
title: コンポーネント インターフェイスの標準メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44b3977a3921d92b1f3f83dd3e744f14b5709fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278050"
---
# <a name="standard-methods-in-component-interfaces"></a><span data-ttu-id="763f1-102">コンポーネント インターフェイスの標準メソッド</span><span class="sxs-lookup"><span data-stu-id="763f1-102">Standard Methods in Component Interfaces</span></span>
<span data-ttu-id="763f1-103">コンポーネント インターフェイスの標準メソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="763f1-103">The standard methods for the component interface are as follows:</span></span>  
  
-   `Create`  
  
-   `Find`  
  
-   `Get`  
  
-   `Save`  
  
 <span data-ttu-id="763f1-104">使用できるのは、基になるコンポーネントに含まれている上記のメソッドだけです。</span><span class="sxs-lookup"><span data-stu-id="763f1-104">Only those methods in the underlying component are available.</span></span> <span data-ttu-id="763f1-105">たとえば、基になるコンポーネントに `Add` 機能が含まれていない場合、`Create` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="763f1-105">For example, if the underlying component does not contain `Add` capabilities, `Create` is unavailable.</span></span>  
  
## <a name="viewing-or-changing-available-methods"></a><span data-ttu-id="763f1-106">使用可能なメソッドの表示または変更</span><span class="sxs-lookup"><span data-stu-id="763f1-106">Viewing or Changing Available Methods</span></span>  
  
#### <a name="to-view-or-change-available-methods"></a><span data-ttu-id="763f1-107">使用可能なメソッドを表示または変更するには</span><span class="sxs-lookup"><span data-stu-id="763f1-107">To view or change available methods</span></span>  
  
1.  <span data-ttu-id="763f1-108">コンポーネント インターフェイスを開く**プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="763f1-108">Open the component interface **Properties** dialog box.</span></span>  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  <span data-ttu-id="763f1-109">クリックして、**標準メソッド**タブです。</span><span class="sxs-lookup"><span data-stu-id="763f1-109">Click the **Standard Methods** tab.</span></span>  
  
3.  <span data-ttu-id="763f1-110">目的のメソッドを選択し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="763f1-110">Select the desired methods, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="763f1-111">参照</span><span class="sxs-lookup"><span data-stu-id="763f1-111">See Also</span></span>  
 <span data-ttu-id="763f1-112">[コンポーネント インターフェイスを作成する方法](../core/how-to-create-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="763f1-112">[How to Create Component Interfaces](../core/how-to-create-component-interfaces.md) </span></span>  
 [<span data-ttu-id="763f1-113">付録 c: コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="763f1-113">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)