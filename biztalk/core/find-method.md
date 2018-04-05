---
title: Find メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 9a5432c68c36dcf8e769351af6d57f3cd3ed712b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="find-method"></a><span data-ttu-id="ac4ee-102">Find メソッド</span><span class="sxs-lookup"><span data-stu-id="ac4ee-102">Find Method</span></span>
<span data-ttu-id="ac4ee-103">指定された部分検索キーに合致するキーの一覧を返すために使用します。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-103">Used to return a list of keys that satisfy the supplied partial search keys.</span></span> <span data-ttu-id="ac4ee-104">インスタンスが 1 つだけしかないコンポーネント インターフェイスの場合、つまりキーが存在しない場合、`Find()` 関数は生成されません。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-104">Note that for a component interface that has only one instance, that is, there is no key, the `Find()` function is not generated.</span></span> <span data-ttu-id="ac4ee-105">関連項目[Get メソッド](../core/get-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-105">See also [Get Method](../core/get-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4ee-106">構文</span><span class="sxs-lookup"><span data-stu-id="ac4ee-106">Syntax</span></span>  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac4ee-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac4ee-107">Parameters</span></span>  
  
|<span data-ttu-id="ac4ee-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac4ee-108">Parameter</span></span>|<span data-ttu-id="ac4ee-109">Description</span><span class="sxs-lookup"><span data-stu-id="ac4ee-109">Description</span></span>|  
|---------------|-----------------|  
|`partialKey`|<span data-ttu-id="ac4ee-110">個々のキーが任意の場合の構造。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-110">A structure where the individual keys are optional.</span></span>|  
|`keyList`|<span data-ttu-id="ac4ee-111">`partialKey` と一致するキーのリスト。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-111">A list of keys that matches the `partialKey`.</span></span> <span data-ttu-id="ac4ee-112">これは、出力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-112">It is an output parameter.</span></span><br /><br /> <span data-ttu-id="ac4ee-113">特定のコンポーネント インターフェイスについて定義された Find Keys のセットに対応するキー。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-113">The keys correspond to the set of Find Keys as defined for the particular component interface.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac4ee-114">解説</span><span class="sxs-lookup"><span data-stu-id="ac4ee-114">Remarks</span></span>  
 <span data-ttu-id="ac4ee-115">部分キーを指定する場合、PeopleSoft 内部の `Find()` 関数の場合と同じワイルドカード検索を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-115">When you specify the partial keys, it is possible to use the same wildcard search available from the PeopleSoft internal `Find()` function.</span></span> <span data-ttu-id="ac4ee-116">たとえば、"11" という部分 ACCOUNT キーは "11" で始まるすべての ACCOUNT キーを返し、"%40" の場合はキー内に "40" が含まれるすべての ACCOUNT キーを返します。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-116">For example, the partial ACCOUNT key of "11" returns all ACCOUNT keys that start with "11", whereas "%40" returns all ACCOUNT keys that contain "40" anywhere within the key.</span></span> <span data-ttu-id="ac4ee-117">"_4_4" という部分キーは、2 文字目と 4 文字目に "4" という文字が含まれるすべての ACCOUNT キーを返します。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-117">A partial key "_4_4" returns all ACCOUNT keys with the character "4" in the 2nd and 4th positions.</span></span>  
  
 <span data-ttu-id="ac4ee-118">注: PeopleSoft Server の現在の実装で 300 を超える項目が検索条件に一致する場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-118">Note: With the current implementation of the PeopleSoft Server, if more than 300 items match the search criteria, the call fails.</span></span> <span data-ttu-id="ac4ee-119">これは、PeopleSoft Server の制限です。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-119">This is a restriction of the PeopleSoft server.</span></span> <span data-ttu-id="ac4ee-120">Microsoft BizTalk Adapter for PeopleSoft Enterprise の `Find()` メソッドは、コンポーネント インターフェイスに含まれる PeopleSoft の `Find` 関数が有効で、Get キーが利用できる場合に提供されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ee-120">The Microsoft BizTalk Adapter for PeopleSoft Enterprise `Find()` method is provided if the PeopleSoft `Find` function in the component interface is enabled and Get keys are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4ee-121">参照</span><span class="sxs-lookup"><span data-stu-id="ac4ee-121">See Also</span></span>  
 [<span data-ttu-id="ac4ee-122">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="ac4ee-122">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)