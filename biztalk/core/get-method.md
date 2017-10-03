---
title: "Get メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56b060cc261f707a4aa7b0d6a496a62707c4dca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-method"></a><span data-ttu-id="61c13-102">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="61c13-102">Get Method</span></span>
<span data-ttu-id="61c13-103">入力キー パラメーター (key1、key2、... に基づいてプロパティを取得するために使用</span><span class="sxs-lookup"><span data-stu-id="61c13-103">Used to retrieve properties based on the input key parameters (key1, key2, …</span></span> <span data-ttu-id="61c13-104">keyn)。</span><span class="sxs-lookup"><span data-stu-id="61c13-104">keyn).</span></span> <span data-ttu-id="61c13-105">出力パラメーターは、キー パラメーターに一致するレコードのプロパティを含む構造です。</span><span class="sxs-lookup"><span data-stu-id="61c13-105">The output parameter is a structure containing the properties of the record that matches the key parameters.</span></span> <span data-ttu-id="61c13-106">コンポーネント インターフェイスのインスタンスが 1 つしかない場合 (キーがない場合) は、Get 関数にキー パラメーターは含まれません。</span><span class="sxs-lookup"><span data-stu-id="61c13-106">If the component interface has only one instance (that is, there is no key), the Get function does not contain any key parameter.</span></span> <span data-ttu-id="61c13-107">参照してください[Find メソッド](../core/find-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="61c13-107">Also see [Find Method](../core/find-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c13-108">構文</span><span class="sxs-lookup"><span data-stu-id="61c13-108">Syntax</span></span>  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="61c13-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61c13-109">Parameters</span></span>  
  
|<span data-ttu-id="61c13-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61c13-110">Parameter</span></span>|<span data-ttu-id="61c13-111">Description</span><span class="sxs-lookup"><span data-stu-id="61c13-111">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="61c13-112">このパラメーターのセットがサーバー データベースに存在する必要があります。存在しない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="61c13-112">A set of parameters that must exist in the server database; otherwise an error occurs.</span></span> <span data-ttu-id="61c13-113">これらのキーは、特定のコンポーネント インターフェイスに定義されているキーの取得のセットと対応します。</span><span class="sxs-lookup"><span data-stu-id="61c13-113">These keys correspond to the set of Get Keys as defined for the particular Component Interface.</span></span>|  
|`properties`|<span data-ttu-id="61c13-114">呼び出しの完了時に返されるコンポーネント インターフェイスのプロパティの完全な構造が含まれます。</span><span class="sxs-lookup"><span data-stu-id="61c13-114">Contains a complete structure of the component interface properties, which is returned upon completion of the call.</span></span>|  
|`getHistoryItems`|<span data-ttu-id="61c13-115">ブール値です。</span><span class="sxs-lookup"><span data-stu-id="61c13-115">A Boolean value.</span></span> <span data-ttu-id="61c13-116">コンポーネント インターフェイスのプロパティにレベル 0 未満の有効日が指定された項目 (名前が EFFDT のキー フィールド) が含まれている場合は、追加のパラメーターとして `getHistoryItems` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c13-116">If the properties of the component interface contain effective-dated items below level 0 (that is, a key field with a name of EFFDT) the `getHistoryItems` additional parameter is required.</span></span><br /><br /> <span data-ttu-id="61c13-117">値の場合。</span><span class="sxs-lookup"><span data-stu-id="61c13-117">If the value is:</span></span><br /><br /> <span data-ttu-id="61c13-118">-True、すべての有効日が指定された項目が (任意のレベルで埋め込むことができます) をシーケンスとして返されます。</span><span class="sxs-lookup"><span data-stu-id="61c13-118">-   True—All effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="61c13-119">これには、過去の有効日が指定された項目、現在の有効日が指定された項目、および未来の有効日が指定された項目のすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61c13-119">These include all past effective dated items, the current effective dated item, as well as all future effective dated items</span></span><br /><span data-ttu-id="61c13-120">-False: 現在のおよび未来の有効日が指定された項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="61c13-120">-   False—Only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="61c13-121">同じインスタンス上の更新の後続の呼び出しになります、し`getHistoryItems`False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c13-121">If subsequent calls to update on the same instance will be made, then `getHistoryItems` should be set to False.</span></span>|  
  
### <a name="remarks"></a><span data-ttu-id="61c13-122">解説</span><span class="sxs-lookup"><span data-stu-id="61c13-122">Remarks</span></span>  
 <span data-ttu-id="61c13-123">コンポーネント インターフェイスのプロパティに有効日が含まれている場合アイテム レベル 0 (つまり、キー フィールドで名前が EFFDT の)、追加のパラメーター`getHistoryItems`が必要です。</span><span class="sxs-lookup"><span data-stu-id="61c13-123">If the properties of the component interface contain effective dated items below level 0 (that is, a key field with a name of EFFDT), an additional parameter, `getHistoryItems`, is required.</span></span> <span data-ttu-id="61c13-124">このパラメーターはブール型です。</span><span class="sxs-lookup"><span data-stu-id="61c13-124">This parameter is of type Boolean.</span></span> <span data-ttu-id="61c13-125">このパラメーターを True に設定すると、有効日が指定されたすべての項目がシーケンスとして返されます (任意のレベルで埋め込むことができます)。</span><span class="sxs-lookup"><span data-stu-id="61c13-125">If it is set to True, all effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="61c13-126">過去の未来の有効日が指定された項目だけでなく、有効日が指定された項目、現在の有効日が指定された項目すべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61c13-126">These include all past effective dated items, the current effective dated item, as well as all future effective dated items.</span></span> <span data-ttu-id="61c13-127">`getHistoryItems` パラメーターを False に設定すると、現在または未来の有効日が指定された項目のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="61c13-127">If the `getHistoryItems` parameter is set to False, only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="61c13-128">同じインスタンスで続けて更新の呼び出しを行う場合は、`getHistoryItems` を False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c13-128">If subsequent calls to update on the same instance are to be made, then `getHistoryItems` should be set to False.</span></span> <span data-ttu-id="61c13-129">関連項目[UpdateEx メソッド](../core/updateex-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="61c13-129">See also [UpdateEx Method](../core/updateex-method.md).</span></span>  
  
 <span data-ttu-id="61c13-130">コンポーネント インターフェイスにキーがない場合 (インスタンスが 1 つしかない場合)、`Get()` メソッドの形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="61c13-130">If the component interface does not have a key, as in the case where only one instance can exist, then the `Get()` method has the form:</span></span>  
  
```  
Get(properties)  
```  
  
 <span data-ttu-id="61c13-131">有効日が指定された項目の詳細については、PeopleSoft Enterprise のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c13-131">For more information on effective dated items, see the PeopleSoft Enterprise documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61c13-132">コンポーネント インターフェイスで PeopleSoft の `Get()` 関数が有効な場合、BizTalk Adapter for PeopleSoft Enterprise `Get` メソッドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="61c13-132">The BizTalk Adapter for PeopleSoft Enterprise `Get()` method is provided if the PeopleSoft `Get` function in the component interface is enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c13-133">参照</span><span class="sxs-lookup"><span data-stu-id="61c13-133">See Also</span></span>  
 [<span data-ttu-id="61c13-134">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="61c13-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)