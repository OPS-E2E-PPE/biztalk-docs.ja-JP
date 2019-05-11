---
title: Find メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81599a87a88aaa383616653435119ec95d6ff430
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345386"
---
# <a name="find-method"></a><span data-ttu-id="2a8cf-102">Find メソッド</span><span class="sxs-lookup"><span data-stu-id="2a8cf-102">Find Method</span></span>
<span data-ttu-id="2a8cf-103">指定された部分検索キーに合致するキーの一覧を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-103">Used to return a list of keys that satisfy the supplied partial search keys.</span></span> <span data-ttu-id="2a8cf-104">インスタンスを 1 つだけ持つコンポーネント インターフェイス、つまりがないこと、キーに注意してください、`Find()`関数は生成されません。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-104">Note that for a component interface that has only one instance, that is, there is no key, the `Find()` function is not generated.</span></span> <span data-ttu-id="2a8cf-105">参照してください[Get メソッド](../core/get-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-105">See also [Get Method](../core/get-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a8cf-106">構文</span><span class="sxs-lookup"><span data-stu-id="2a8cf-106">Syntax</span></span>  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a8cf-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a8cf-107">Parameters</span></span>  
  
|<span data-ttu-id="2a8cf-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a8cf-108">Parameter</span></span>|<span data-ttu-id="2a8cf-109">説明</span><span class="sxs-lookup"><span data-stu-id="2a8cf-109">Description</span></span>|  
|---------------|-----------------|  
|`partialKey`|<span data-ttu-id="2a8cf-110">個々 のキーが省略可能な構造体。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-110">A structure where the individual keys are optional.</span></span>|  
|`keyList`|<span data-ttu-id="2a8cf-111">一致するキーの一覧、`partialKey`します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-111">A list of keys that matches the `partialKey`.</span></span> <span data-ttu-id="2a8cf-112">これは、出力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-112">It is an output parameter.</span></span><br /><br /> <span data-ttu-id="2a8cf-113">キーは、特定のコンポーネント インターフェイスに定義された Find Keys のセットに対応します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-113">The keys correspond to the set of Find Keys as defined for the particular component interface.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a8cf-114">コメント</span><span class="sxs-lookup"><span data-stu-id="2a8cf-114">Remarks</span></span>  
 <span data-ttu-id="2a8cf-115">部分キーを指定すると、PeopleSoft 内部の同じワイルドカード検索を使用することは`Find()`関数。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-115">When you specify the partial keys, it is possible to use the same wildcard search available from the PeopleSoft internal `Find()` function.</span></span> <span data-ttu-id="2a8cf-116">たとえば、「11」の部分のアカウント キーは「11」で始まるすべてのアカウント キーを返しますの一方"40"が、キーの任意の場所にある「40」が含まれているすべてのアカウント キーを返します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-116">For example, the partial ACCOUNT key of "11" returns all ACCOUNT keys that start with "11", whereas "%40" returns all ACCOUNT keys that contain "40" anywhere within the key.</span></span> <span data-ttu-id="2a8cf-117">部分キー「_4_4」は、2 番目と 4 番目の位置に文字「4」ですべてのアカウント キーを返します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-117">A partial key "_4_4" returns all ACCOUNT keys with the character "4" in the 2nd and 4th positions.</span></span>  
  
 <span data-ttu-id="2a8cf-118">注:PeopleSoft Server の現在の実装で 300 を超える項目が、検索条件に一致する場合は、呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-118">Note: With the current implementation of the PeopleSoft Server, if more than 300 items match the search criteria, the call fails.</span></span> <span data-ttu-id="2a8cf-119">これは、PeopleSoft server の制限です。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-119">This is a restriction of the PeopleSoft server.</span></span> <span data-ttu-id="2a8cf-120">Microsoft BizTalk Adapter for PeopleSoft Enterprise`Find()`メソッドが提供される場合、PeopleSoft`Find`コンポーネント インターフェイスで関数が有効になっており、Get キーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a8cf-120">The Microsoft BizTalk Adapter for PeopleSoft Enterprise `Find()` method is provided if the PeopleSoft `Find` function in the component interface is enabled and Get keys are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a8cf-121">参照</span><span class="sxs-lookup"><span data-stu-id="2a8cf-121">See Also</span></span>  
 [<span data-ttu-id="2a8cf-122">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="2a8cf-122">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)