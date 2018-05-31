---
title: '付録 c: コンポーネント インターフェイスの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enterprise Integration Points
- EIP
- component interfaces
ms.assetid: 2e3bc5ef-24ea-4e09-8e95-31feefaf5536
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c482a01de8f6040f31e6563c97b041dedbe9e88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230266"
---
# <a name="appendix-c-using-component-interfaces"></a><span data-ttu-id="e29be-102">付録 c: コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="e29be-102">Appendix C: Using Component Interfaces</span></span>
<span data-ttu-id="e29be-103">このセクションのトピックでは、新しいコンポーネント インターフェイスを作成する方法を説明 — および既存のコンポーネント インターフェイスを変更する方法: Microsoft BizTalk adapter for PeopleSoft Enterprise の使用をします。</span><span class="sxs-lookup"><span data-stu-id="e29be-103">The topics in this section describe how to create new component interfaces—and how to modify existing component interfaces—for use with Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="e29be-104">また、それらのコンポーネント インターフェイスにセキュリティを適用する方法、およびそれらのコンポーネント インターフェイスをテストする方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="e29be-104">They also describe how to apply security to those component interfaces and how to test them.</span></span>  
  
 <span data-ttu-id="e29be-105">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e29be-105">You can do the following:</span></span>  
  
-   <span data-ttu-id="e29be-106">PeopleSoft が提供しているコンポーネント インターフェイスをアプリケーションで使用する。</span><span class="sxs-lookup"><span data-stu-id="e29be-106">Use component interfaces supplied by PeopleSoft with your application.</span></span>  
  
     <span data-ttu-id="e29be-107">コンポーネント インターフェイスは、Enterprise Integration Points (EIP) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e29be-107">Component interfaces also are known as Enterprise Integration Points (EIP).</span></span>  
  
-   <span data-ttu-id="e29be-108">既存のコンポーネント インターフェイスを変更する。</span><span class="sxs-lookup"><span data-stu-id="e29be-108">Modify an existing component interface.</span></span>  
  
-   <span data-ttu-id="e29be-109">新しいコンポーネント インターフェイスを作成する。</span><span class="sxs-lookup"><span data-stu-id="e29be-109">Create a new component interface.</span></span>  
  
 <span data-ttu-id="e29be-110">コンポーネント インターフェイスを使用する前に、セキュリティを適用しテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e29be-110">Before using your component interface, you must apply and test security.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e29be-111">このセクションの目的は役立つ補足説明を提供することです。このセクションは PeopleSoft のマニュアルに代わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="e29be-111">This section is intended as a helpful supplement; it is not a substitute for PeopleSoft documentation.</span></span> <span data-ttu-id="e29be-112">PeopleSoft コンポーネント インターフェイスの完全な最新情報については、PeopleSoft オンライン ライブラリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e29be-112">For complete and up-to-date information about PeopleSoft component interfaces, see the PeopleSoft Online Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e29be-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e29be-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e29be-114">コンポーネント インターフェイスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e29be-114">How to Create Component Interfaces</span></span>](../core/how-to-create-component-interfaces.md)  
  
-   [<span data-ttu-id="e29be-115">コンポーネント インターフェイスの標準メソッド</span><span class="sxs-lookup"><span data-stu-id="e29be-115">Standard Methods in Component Interfaces</span></span>](../core/standard-methods-in-component-interfaces.md)  
  
-   [<span data-ttu-id="e29be-116">コンポーネント インターフェイスをセキュリティ保護する方法</span><span class="sxs-lookup"><span data-stu-id="e29be-116">How to Help Secure Component Interfaces</span></span>](../core/how-to-help-secure-component-interfaces.md)  
  
-   [<span data-ttu-id="e29be-117">コンポーネント インターフェイスをテストする方法</span><span class="sxs-lookup"><span data-stu-id="e29be-117">How to Test Component Interfaces</span></span>](../core/how-to-test-component-interfaces.md)