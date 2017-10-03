---
title: "DeleteOnly メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3982c67b4c2eb572a57a4ad602b1d302f9b53ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deleteonly-method"></a><span data-ttu-id="639d6-102">DeleteOnly メソッド</span><span class="sxs-lookup"><span data-stu-id="639d6-102">DeleteOnly Method</span></span>
<span data-ttu-id="639d6-103">コレクション内のアイテムを削除できます。</span><span class="sxs-lookup"><span data-stu-id="639d6-103">Allows you to delete items in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="639d6-104">Syntax</span></span>  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="639d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="639d6-105">Parameters</span></span>  
  
|<span data-ttu-id="639d6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="639d6-106">Parameter</span></span>|<span data-ttu-id="639d6-107">Description</span><span class="sxs-lookup"><span data-stu-id="639d6-107">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="639d6-108">指定する必要があるパラメーター セットです。</span><span class="sxs-lookup"><span data-stu-id="639d6-108">Is a set of parameters that must be supplied.</span></span> <span data-ttu-id="639d6-109">このキー セットはサーバー データベースに存在する必要があります。存在しない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="639d6-109">This set of keys must exist in the server database, or an error occurs.</span></span> <span data-ttu-id="639d6-110">これらのキーは、特定のコンポーネント インターフェイスに定義された一連の Get キーに対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-110">These keys correspond to the set of Get Keys as defined for the particular component interface.</span></span>|  
|`correctionMode`|<span data-ttu-id="639d6-111">ブール型のフラグ。</span><span class="sxs-lookup"><span data-stu-id="639d6-111">A Boolean flag.</span></span> <span data-ttu-id="639d6-112">true に設定すると、コレクションの有効日が過去になったアイテムを削除できます。</span><span class="sxs-lookup"><span data-stu-id="639d6-112">When set to true, allows deletion of past effective-dated items in a collection.</span></span> <span data-ttu-id="639d6-113">具体的には、EFFDT が現在の有効日より前になっているアイテムを削除できます。</span><span class="sxs-lookup"><span data-stu-id="639d6-113">Specifically, it allows the deletion of items that have EFFDT prior to the current effective date.</span></span> <span data-ttu-id="639d6-114">このフラグを TRUE に設定しない場合、これらの項目への変更により、PeopleSoft サーバーからエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-114">Without this flag set to TRUE, any modification to these items results in an error returned from PeopleSoft server.</span></span> <span data-ttu-id="639d6-115">**注:** 、`correctionMode`引数は、effective-dated 項目を含むコンポーネント インターフェイスに対してのみ公開されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-115">**Note:**  The `correctionMode` argument is only exposed for those component interfaces that contain effective-dated items.</span></span> <span data-ttu-id="639d6-116">それ以外の場合、引数の一部としては表示されません。</span><span class="sxs-lookup"><span data-stu-id="639d6-116">Otherwise it is not shown as part of the argument.</span></span>|  
|`interactiveMode`|<span data-ttu-id="639d6-117">エラー処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-117">Used for error handling.</span></span><br /><br /> <span data-ttu-id="639d6-118">コンポーネント インターフェイスでプロパティにアクセスする場合、BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft から提供されている API を使用してコンポーネント インターフェイス内の個々のフィールドを読み書きします。ただし、これらの変更は一度に 1 つずつ PeopleSoft サーバーに伝達されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="639d6-118">When accessing properties in a component interface, the BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="639d6-119">代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と対話) が、すべての変更を 1 つのパッケージにしてサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="639d6-119">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span> <span data-ttu-id="639d6-120">個別の更新が失敗した場合、汎用エラーが返されます。このエラーは、実際のエラーを特定しません。</span><span class="sxs-lookup"><span data-stu-id="639d6-120">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="639d6-121">対話モードを TRUE に設定することで、すべてのフィールド更新がサーバーに個別に送信されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-121">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="639d6-122">これによってパフォーマンスに大きな影響が及びますが、更新が失敗した場合 (たとえば、フィールドの設定に無効な値が使用された場合) には、具体的なエラー情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-122">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="639d6-123">`interactiveMode` パラメーターを使用すると、パフォーマンスを最大限に発揮し、フィールド更新レベルでエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-123">The `interactiveMode` parameter provides maximum performance and provides error reporting at the field-update level.</span></span> <span data-ttu-id="639d6-124">この機能を適切に使用するには、`interactiveMode` を FALSE に設定して通常の呼び出しを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="639d6-124">To use this feature properly, it is recommended that you make normal calls with `interactiveMode` set to FALSE.</span></span> <span data-ttu-id="639d6-125">パフォーマンスへの影響はありません。</span><span class="sxs-lookup"><span data-stu-id="639d6-125">There should be no impact on performance.</span></span> <span data-ttu-id="639d6-126">エラーが返された場合は、interactiveMode フラグを TRUE に設定して同じ呼び出しを再試行できます。</span><span class="sxs-lookup"><span data-stu-id="639d6-126">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="639d6-127">呼び出しが失敗した場合、サーバーはより正確なエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="639d6-127">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="639d6-128">サーバーに存在する構造のサブセットが入ります。</span><span class="sxs-lookup"><span data-stu-id="639d6-128">Contains a subset of the structure that exists on the server.</span></span> <span data-ttu-id="639d6-129">リーフであるアイテムはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-129">All items that are leaves are deleted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="639d6-130">解説</span><span class="sxs-lookup"><span data-stu-id="639d6-130">Remarks</span></span>  
 <span data-ttu-id="639d6-131">プロパティのデータ型はコンポーネント インターフェイスの `CreateEx` メソッドまたは `UpdateEx` メソッドと同じです。ただし、キー値のみが重要です。</span><span class="sxs-lookup"><span data-stu-id="639d6-131">The properties have the same data type as the `CreateEx` or `UpdateEx` methods of this component interface; however, only the key values are important.</span></span> <span data-ttu-id="639d6-132">キー以外の値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-132">The non-key values are ignored.</span></span> <span data-ttu-id="639d6-133">キー値はサーバーのキー値と一致する必要があります。一致しない場合、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="639d6-133">The key values must match those on the server, otherwise an exception is raised.</span></span>  
  
 <span data-ttu-id="639d6-134">次に、キー値の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="639d6-134">The following demonstrates the use of the key values.</span></span> <span data-ttu-id="639d6-135">コレクションに次のアイテムがあるとします。</span><span class="sxs-lookup"><span data-stu-id="639d6-135">If a collection contains the items:</span></span>  
  
-   <span data-ttu-id="639d6-136">item0</span><span class="sxs-lookup"><span data-stu-id="639d6-136">item0</span></span>  
  
-   <span data-ttu-id="639d6-137">item1</span><span class="sxs-lookup"><span data-stu-id="639d6-137">item1</span></span>  
  
-   <span data-ttu-id="639d6-138">item2</span><span class="sxs-lookup"><span data-stu-id="639d6-138">item2</span></span>  
  
-   <span data-ttu-id="639d6-139">item3</span><span class="sxs-lookup"><span data-stu-id="639d6-139">item3</span></span>  
  
 <span data-ttu-id="639d6-140">プロパティの item1 と item3 のキーを指定すると、item1 と item3 を削除できます。</span><span class="sxs-lookup"><span data-stu-id="639d6-140">You can delete item1 and item3 by providing the keys of item1 and item3 in the properties:</span></span>  
  
-   <span data-ttu-id="639d6-141">item1</span><span class="sxs-lookup"><span data-stu-id="639d6-141">item1</span></span>  
  
-   <span data-ttu-id="639d6-142">item3</span><span class="sxs-lookup"><span data-stu-id="639d6-142">item3</span></span>  
  
 <span data-ttu-id="639d6-143">呼び出し後、サーバーのコレクションには次のアイテムが残ります。</span><span class="sxs-lookup"><span data-stu-id="639d6-143">After the call, the server has the remaining items in the collection:</span></span>  
  
-   <span data-ttu-id="639d6-144">item0</span><span class="sxs-lookup"><span data-stu-id="639d6-144">item0</span></span>  
  
-   <span data-ttu-id="639d6-145">item2</span><span class="sxs-lookup"><span data-stu-id="639d6-145">item2</span></span>  
  
 <span data-ttu-id="639d6-146">2 番目の例では、他のコレクションが入ったアイテムを示します。</span><span class="sxs-lookup"><span data-stu-id="639d6-146">The second example shows the items containing other collections:</span></span>  
  
-   <span data-ttu-id="639d6-147">item0</span><span class="sxs-lookup"><span data-stu-id="639d6-147">item0</span></span>  
  
    -   <span data-ttu-id="639d6-148">item0a</span><span class="sxs-lookup"><span data-stu-id="639d6-148">item0a</span></span>  
  
-   <span data-ttu-id="639d6-149">item1</span><span class="sxs-lookup"><span data-stu-id="639d6-149">item1</span></span>  
  
    -   <span data-ttu-id="639d6-150">item1a</span><span class="sxs-lookup"><span data-stu-id="639d6-150">item1a</span></span>  
  
    -   <span data-ttu-id="639d6-151">item1b</span><span class="sxs-lookup"><span data-stu-id="639d6-151">item1b</span></span>  
  
    -   <span data-ttu-id="639d6-152">item1c</span><span class="sxs-lookup"><span data-stu-id="639d6-152">item1c</span></span>  
  
-   <span data-ttu-id="639d6-153">item2</span><span class="sxs-lookup"><span data-stu-id="639d6-153">item2</span></span>  
  
    -   <span data-ttu-id="639d6-154">item2a</span><span class="sxs-lookup"><span data-stu-id="639d6-154">item2a</span></span>  
  
    -   <span data-ttu-id="639d6-155">item2b</span><span class="sxs-lookup"><span data-stu-id="639d6-155">item2b</span></span>  
  
 <span data-ttu-id="639d6-156">item1b と item2 へのキーを指定することで item1b とすべての item2 を削除できます。</span><span class="sxs-lookup"><span data-stu-id="639d6-156">You can delete item1b and all of item2 by giving the keys to item1b and item2:</span></span>  
  
-   <span data-ttu-id="639d6-157">item1</span><span class="sxs-lookup"><span data-stu-id="639d6-157">item1</span></span>  
  
    -   <span data-ttu-id="639d6-158">item1b</span><span class="sxs-lookup"><span data-stu-id="639d6-158">item1b</span></span>  
  
-   <span data-ttu-id="639d6-159">item2</span><span class="sxs-lookup"><span data-stu-id="639d6-159">item2</span></span>  
  
 <span data-ttu-id="639d6-160">item2 の空のサブコレクションを指定することで、item2 をリーフにし、そのサブブランチ全体が削除されます。</span><span class="sxs-lookup"><span data-stu-id="639d6-160">By providing an empty sub-collection for item2, you turn it into a leaf and that entire sub-branch is deleted.</span></span> <span data-ttu-id="639d6-161">呼び出し後、サーバーには次のアイテムが残ります。</span><span class="sxs-lookup"><span data-stu-id="639d6-161">After the call, the server has the remaining items:</span></span>  
  
-   <span data-ttu-id="639d6-162">item0</span><span class="sxs-lookup"><span data-stu-id="639d6-162">item0</span></span>  
  
    -   <span data-ttu-id="639d6-163">item0a</span><span class="sxs-lookup"><span data-stu-id="639d6-163">item0a</span></span>  
  
-   <span data-ttu-id="639d6-164">item1</span><span class="sxs-lookup"><span data-stu-id="639d6-164">item1</span></span>  
  
    -   <span data-ttu-id="639d6-165">item1a</span><span class="sxs-lookup"><span data-stu-id="639d6-165">item1a</span></span>  
  
    -   <span data-ttu-id="639d6-166">item1c</span><span class="sxs-lookup"><span data-stu-id="639d6-166">item1c</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639d6-167">参照</span><span class="sxs-lookup"><span data-stu-id="639d6-167">See Also</span></span>  
 [<span data-ttu-id="639d6-168">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="639d6-168">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)