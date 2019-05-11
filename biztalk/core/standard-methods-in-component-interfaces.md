---
title: コンポーネント インターフェイスの標準メソッド |Microsoft Docs
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
ms.openlocfilehash: 308e099f6e16cadd671785947300ada4e113e7a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392902"
---
# <a name="standard-methods-in-component-interfaces"></a><span data-ttu-id="2dbd8-102">コンポーネント インターフェイスの標準メソッド</span><span class="sxs-lookup"><span data-stu-id="2dbd8-102">Standard Methods in Component Interfaces</span></span>
<span data-ttu-id="2dbd8-103">コンポーネント インターフェイスの標準的な方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-103">The standard methods for the component interface are as follows:</span></span>  
  
- `Create`  
  
- `Find`  
  
- `Get`  
  
- `Save`  
  
  <span data-ttu-id="2dbd8-104">基になるコンポーネントでこれらのメソッドにのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-104">Only those methods in the underlying component are available.</span></span> <span data-ttu-id="2dbd8-105">たとえば、基になるコンポーネントが含まれていない`Add`機能、`Create`は使用できません。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-105">For example, if the underlying component does not contain `Add` capabilities, `Create` is unavailable.</span></span>  
  
## <a name="viewing-or-changing-available-methods"></a><span data-ttu-id="2dbd8-106">表示または使用可能なメソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-106">Viewing or Changing Available Methods</span></span>  
  
#### <a name="to-view-or-change-available-methods"></a><span data-ttu-id="2dbd8-107">表示または使用可能なメソッドを変更するには</span><span class="sxs-lookup"><span data-stu-id="2dbd8-107">To view or change available methods</span></span>  
  
1.  <span data-ttu-id="2dbd8-108">コンポーネント インターフェイスを開く**プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-108">Open the component interface **Properties** dialog box.</span></span>  
  
     <span data-ttu-id="2dbd8-109">![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")</span><span class="sxs-lookup"><span data-stu-id="2dbd8-109">![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")</span></span>  
  
2.  <span data-ttu-id="2dbd8-110">をクリックして、**標準メソッド**タブ。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-110">Click the **Standard Methods** tab.</span></span>  
  
3.  <span data-ttu-id="2dbd8-111">目的のメソッドを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-111">Select the desired methods, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbd8-112">参照</span><span class="sxs-lookup"><span data-stu-id="2dbd8-112">See Also</span></span>  
 <span data-ttu-id="2dbd8-113">[コンポーネント インターフェイスを作成する方法](../core/how-to-create-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="2dbd8-113">[How to Create Component Interfaces](../core/how-to-create-component-interfaces.md) </span></span>  
 [<span data-ttu-id="2dbd8-114">付録 c:コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="2dbd8-114">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)