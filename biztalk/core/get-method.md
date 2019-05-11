---
title: メソッドの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fbf3b80fce70cac1ac95d21c143cdb64fae6305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345140"
---
# <a name="get-method"></a><span data-ttu-id="b19fa-102">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="b19fa-102">Get Method</span></span>
<span data-ttu-id="b19fa-103">入力キー パラメーター (key1、key2、... に基づいてプロパティを取得するために使用</span><span class="sxs-lookup"><span data-stu-id="b19fa-103">Used to retrieve properties based on the input key parameters (key1, key2, …</span></span> <span data-ttu-id="b19fa-104">keyn)。</span><span class="sxs-lookup"><span data-stu-id="b19fa-104">keyn).</span></span> <span data-ttu-id="b19fa-105">出力パラメーターは、キーのパラメーターに一致するレコードのプロパティを含む構造です。</span><span class="sxs-lookup"><span data-stu-id="b19fa-105">The output parameter is a structure containing the properties of the record that matches the key parameters.</span></span> <span data-ttu-id="b19fa-106">コンポーネント インターフェイスに 1 つだけのインスタンスがある場合 (つまりはキー)、Get 関数にキー パラメーターが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b19fa-106">If the component interface has only one instance (that is, there is no key), the Get function does not contain any key parameter.</span></span> <span data-ttu-id="b19fa-107">参照してください[Find メソッド](../core/find-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b19fa-107">Also see [Find Method](../core/find-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b19fa-108">構文</span><span class="sxs-lookup"><span data-stu-id="b19fa-108">Syntax</span></span>  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b19fa-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b19fa-109">Parameters</span></span>  
  
|<span data-ttu-id="b19fa-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b19fa-110">Parameter</span></span>|<span data-ttu-id="b19fa-111">説明</span><span class="sxs-lookup"><span data-stu-id="b19fa-111">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="b19fa-112">一連のパラメーター、サーバー データベースに存在する必要があります。それ以外の場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b19fa-112">A set of parameters that must exist in the server database; otherwise an error occurs.</span></span> <span data-ttu-id="b19fa-113">これらのキーは、特定のコンポーネント インターフェイスで定義されている一連の Get キーに対応します。</span><span class="sxs-lookup"><span data-stu-id="b19fa-113">These keys correspond to the set of Get Keys as defined for the particular Component Interface.</span></span>|  
|`properties`|<span data-ttu-id="b19fa-114">呼び出しの完了時に返されるコンポーネント インターフェイスのプロパティの完全な構造が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b19fa-114">Contains a complete structure of the component interface properties, which is returned upon completion of the call.</span></span>|  
|`getHistoryItems`|<span data-ttu-id="b19fa-115">ブール値です。</span><span class="sxs-lookup"><span data-stu-id="b19fa-115">A Boolean value.</span></span> <span data-ttu-id="b19fa-116">コンポーネント インターフェイスのプロパティが、effective-dated 項目レベル 0 未満 (と名前が EFFDT のキー フィールド) を含めることがかどうか、`getHistoryItems`追加のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b19fa-116">If the properties of the component interface contain effective-dated items below level 0 (that is, a key field with a name of EFFDT) the `getHistoryItems` additional parameter is required.</span></span><br /><br /> <span data-ttu-id="b19fa-117">値の場合。</span><span class="sxs-lookup"><span data-stu-id="b19fa-117">If the value is:</span></span><br /><br /> <span data-ttu-id="b19fa-118">-True-すべての有効日が指定された項目が (任意のレベルで埋め込むでした) ことがシーケンスとして返されます。</span><span class="sxs-lookup"><span data-stu-id="b19fa-118">-   True—All effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="b19fa-119">過去の有効日が指定された項目、現在の有効日が指定された項目だけでなく今後すべての有効日が指定された項目すべてが含まれます</span><span class="sxs-lookup"><span data-stu-id="b19fa-119">These include all past effective dated items, the current effective dated item, as well as all future effective dated items</span></span><br /><span data-ttu-id="b19fa-120">-False-のみ現在と未来の有効日が指定された項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="b19fa-120">-   False—Only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="b19fa-121">同じインスタンスで更新する後続の呼び出しが行われます、し`getHistoryItems`を False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b19fa-121">If subsequent calls to update on the same instance will be made, then `getHistoryItems` should be set to False.</span></span>|  
  
### <a name="remarks"></a><span data-ttu-id="b19fa-122">コメント</span><span class="sxs-lookup"><span data-stu-id="b19fa-122">Remarks</span></span>  
 <span data-ttu-id="b19fa-123">コンポーネント インターフェイスのプロパティには、有効な日付が含まれている場合の項目レベル (つまり、キー フィールドの名前が EFFDT の)、0 未満、追加のパラメーター`getHistoryItems`が必要です。</span><span class="sxs-lookup"><span data-stu-id="b19fa-123">If the properties of the component interface contain effective dated items below level 0 (that is, a key field with a name of EFFDT), an additional parameter, `getHistoryItems`, is required.</span></span> <span data-ttu-id="b19fa-124">このパラメーターはブール型です。</span><span class="sxs-lookup"><span data-stu-id="b19fa-124">This parameter is of type Boolean.</span></span> <span data-ttu-id="b19fa-125">True に設定されている場合は、すべての有効日が指定された項目が (任意のレベルで埋め込むでした) ことがシーケンスとして返されます。</span><span class="sxs-lookup"><span data-stu-id="b19fa-125">If it is set to True, all effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="b19fa-126">過去の有効日が指定された項目、現在の有効日が指定された項目だけでなく今後すべての有効日が指定された項目すべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b19fa-126">These include all past effective dated items, the current effective dated item, as well as all future effective dated items.</span></span> <span data-ttu-id="b19fa-127">場合、`getHistoryItems`パラメーターは、False に設定されて、のみ、現在と未来の有効日が指定された項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="b19fa-127">If the `getHistoryItems` parameter is set to False, only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="b19fa-128">同じインスタンスで更新する後続の呼び出しがし、作成される場合`getHistoryItems`を False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b19fa-128">If subsequent calls to update on the same instance are to be made, then `getHistoryItems` should be set to False.</span></span> <span data-ttu-id="b19fa-129">参照してください[UpdateEx メソッド](../core/updateex-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b19fa-129">See also [UpdateEx Method](../core/updateex-method.md).</span></span>  
  
 <span data-ttu-id="b19fa-130">コンポーネント インターフェイスが 1 つだけのインスタンスが存在できるケースのように、キーを持たない場合、`Get()`メソッドの形式。</span><span class="sxs-lookup"><span data-stu-id="b19fa-130">If the component interface does not have a key, as in the case where only one instance can exist, then the `Get()` method has the form:</span></span>  
  
```  
Get(properties)  
```  
  
 <span data-ttu-id="b19fa-131">有効日が指定された項目の詳細については、PeopleSoft Enterprise のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b19fa-131">For more information on effective dated items, see the PeopleSoft Enterprise documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b19fa-132">BizTalk Adapter for PeopleSoft Enterprise`Get()`メソッドが提供される場合、PeopleSoft`Get`コンポーネント インターフェイスで機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b19fa-132">The BizTalk Adapter for PeopleSoft Enterprise `Get()` method is provided if the PeopleSoft `Get` function in the component interface is enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19fa-133">参照</span><span class="sxs-lookup"><span data-stu-id="b19fa-133">See Also</span></span>  
 [<span data-ttu-id="b19fa-134">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="b19fa-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)