---
title: DeleteOnly メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf006e4ba2db1378a207c4e20136310b6977c928
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352274"
---
# <a name="deleteonly-method"></a><span data-ttu-id="d6297-102">DeleteOnly メソッド</span><span class="sxs-lookup"><span data-stu-id="d6297-102">DeleteOnly Method</span></span>
<span data-ttu-id="d6297-103">コレクション内の項目を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d6297-103">Allows you to delete items in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6297-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6297-104">Syntax</span></span>  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6297-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6297-105">Parameters</span></span>  
  
|<span data-ttu-id="d6297-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6297-106">Parameter</span></span>|<span data-ttu-id="d6297-107">説明</span><span class="sxs-lookup"><span data-stu-id="d6297-107">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="d6297-108">一連のパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6297-108">Is a set of parameters that must be supplied.</span></span> <span data-ttu-id="d6297-109">この一連のキーは、サーバー データベースに存在する必要があります。 またはエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d6297-109">This set of keys must exist in the server database, or an error occurs.</span></span> <span data-ttu-id="d6297-110">これらのキーは、特定のコンポーネント インターフェイスに対して定義されている一連の Get キーに対応します。</span><span class="sxs-lookup"><span data-stu-id="d6297-110">These keys correspond to the set of Get Keys as defined for the particular component interface.</span></span>|  
|`correctionMode`|<span data-ttu-id="d6297-111">ブール型のフラグ。</span><span class="sxs-lookup"><span data-stu-id="d6297-111">A Boolean flag.</span></span> <span data-ttu-id="d6297-112">True の場合、コレクションの過去の発効アイテムの削除を可能に設定するとします。</span><span class="sxs-lookup"><span data-stu-id="d6297-112">When set to true, allows deletion of past effective-dated items in a collection.</span></span> <span data-ttu-id="d6297-113">具体的には、EFFDT が現在有効な日付より前にある項目の削除ができます。</span><span class="sxs-lookup"><span data-stu-id="d6297-113">Specifically, it allows the deletion of items that have EFFDT prior to the current effective date.</span></span> <span data-ttu-id="d6297-114">なしこのフラグを TRUE に設定すると、これらの項目を変更しても結果 PeopleSoft サーバーから返されるエラー。</span><span class="sxs-lookup"><span data-stu-id="d6297-114">Without this flag set to TRUE, any modification to these items results in an error returned from PeopleSoft server.</span></span> <span data-ttu-id="d6297-115">**注:**`correctionMode`引数は、effective-dated 項目を含むコンポーネント インターフェイスに対してのみ公開されます。</span><span class="sxs-lookup"><span data-stu-id="d6297-115">**Note:**  The `correctionMode` argument is only exposed for those component interfaces that contain effective-dated items.</span></span> <span data-ttu-id="d6297-116">それ以外の場合、引数の一部としては表示されません。</span><span class="sxs-lookup"><span data-stu-id="d6297-116">Otherwise it is not shown as part of the argument.</span></span>|  
|`interactiveMode`|<span data-ttu-id="d6297-117">エラー処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6297-117">Used for error handling.</span></span><br /><br /> <span data-ttu-id="d6297-118">BizTalk Adapter for PeopleSoft Enterprise が PeopleSoft が提供する Api、;、コンポーネント インターフェイスで個々 のフィールドを読み書きするを使用してコンポーネント インターフェイスでプロパティにアクセスするときただし、これらの変更は、一度に 1 つずつ PeopleSoft サーバーに反映されませんが。</span><span class="sxs-lookup"><span data-stu-id="d6297-118">When accessing properties in a component interface, the BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="d6297-119">代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と連携する) では、すべての変更をパッケージ化し、1 つのパッケージ内のサーバーに変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="d6297-119">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span> <span data-ttu-id="d6297-120">個々 の更新プログラムのいずれかが失敗した場合、汎用的なエラーが返されますが、実際のエラーを特定していません。</span><span class="sxs-lookup"><span data-stu-id="d6297-120">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="d6297-121">対話モードを TRUE に設定、すべてのフィールドの更新プログラムは、サーバーに個別に送信されます。</span><span class="sxs-lookup"><span data-stu-id="d6297-121">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="d6297-122">これは、パフォーマンスに大きな影響がありますが (たとえば、フィールドを設定するために無効な値が使用されます) 場合、更新が失敗した場合は、特定のエラー情報は提供します。</span><span class="sxs-lookup"><span data-stu-id="d6297-122">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="d6297-123">`interactiveMode`パラメーターは、最大のパフォーマンスを提供し、フィールド更新レベルでエラーを報告を提供します。</span><span class="sxs-lookup"><span data-stu-id="d6297-123">The `interactiveMode` parameter provides maximum performance and provides error reporting at the field-update level.</span></span> <span data-ttu-id="d6297-124">この機能を正しく使用するをお勧めして通常の呼び出しを行った`interactiveMode`を FALSE に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6297-124">To use this feature properly, it is recommended that you make normal calls with `interactiveMode` set to FALSE.</span></span> <span data-ttu-id="d6297-125">あるは影響はないパフォーマンスにします。</span><span class="sxs-lookup"><span data-stu-id="d6297-125">There should be no impact on performance.</span></span> <span data-ttu-id="d6297-126">エラーが返された場合、interactiveMode フラグを TRUE に設定と同じ呼び出しを再試行できます。</span><span class="sxs-lookup"><span data-stu-id="d6297-126">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="d6297-127">呼び出しが失敗したときに、サーバーより正確なエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="d6297-127">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="d6297-128">サーバーに存在する構造のサブセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6297-128">Contains a subset of the structure that exists on the server.</span></span> <span data-ttu-id="d6297-129">リーフであるすべての項目が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6297-129">All items that are leaves are deleted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6297-130">コメント</span><span class="sxs-lookup"><span data-stu-id="d6297-130">Remarks</span></span>  
 <span data-ttu-id="d6297-131">プロパティは、同じデータとして型を持つ、`CreateEx`または`UpdateEx`はコンポーネント インターフェイスのメソッドただし、キー値のみが重要です。</span><span class="sxs-lookup"><span data-stu-id="d6297-131">The properties have the same data type as the `CreateEx` or `UpdateEx` methods of this component interface; however, only the key values are important.</span></span> <span data-ttu-id="d6297-132">キー以外の値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d6297-132">The non-key values are ignored.</span></span> <span data-ttu-id="d6297-133">キーの値で、サーバー上のものと一致する必要があります、それ以外の場合、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="d6297-133">The key values must match those on the server, otherwise an exception is raised.</span></span>  
  
 <span data-ttu-id="d6297-134">キーの値の使用を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6297-134">The following demonstrates the use of the key values.</span></span> <span data-ttu-id="d6297-135">場合は、コレクションには、項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6297-135">If a collection contains the items:</span></span>  
  
- <span data-ttu-id="d6297-136">item0</span><span class="sxs-lookup"><span data-stu-id="d6297-136">item0</span></span>  
  
- <span data-ttu-id="d6297-137">item1</span><span class="sxs-lookup"><span data-stu-id="d6297-137">item1</span></span>  
  
- <span data-ttu-id="d6297-138">item2</span><span class="sxs-lookup"><span data-stu-id="d6297-138">item2</span></span>  
  
- <span data-ttu-id="d6297-139">item3</span><span class="sxs-lookup"><span data-stu-id="d6297-139">item3</span></span>  
  
  <span data-ttu-id="d6297-140">Item1 と item3 を削除するには、プロパティの item1 と item3 のキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6297-140">You can delete item1 and item3 by providing the keys of item1 and item3 in the properties:</span></span>  
  
- <span data-ttu-id="d6297-141">item1</span><span class="sxs-lookup"><span data-stu-id="d6297-141">item1</span></span>  
  
- <span data-ttu-id="d6297-142">item3</span><span class="sxs-lookup"><span data-stu-id="d6297-142">item3</span></span>  
  
  <span data-ttu-id="d6297-143">呼び出しの後は、サーバーは、残りの項目をコレクション内に。</span><span class="sxs-lookup"><span data-stu-id="d6297-143">After the call, the server has the remaining items in the collection:</span></span>  
  
- <span data-ttu-id="d6297-144">item0</span><span class="sxs-lookup"><span data-stu-id="d6297-144">item0</span></span>  
  
- <span data-ttu-id="d6297-145">item2</span><span class="sxs-lookup"><span data-stu-id="d6297-145">item2</span></span>  
  
  <span data-ttu-id="d6297-146">2 番目の例では、他のコレクションを格納している項目を示します。</span><span class="sxs-lookup"><span data-stu-id="d6297-146">The second example shows the items containing other collections:</span></span>  
  
- <span data-ttu-id="d6297-147">item0</span><span class="sxs-lookup"><span data-stu-id="d6297-147">item0</span></span>  
  
  -   <span data-ttu-id="d6297-148">item0a</span><span class="sxs-lookup"><span data-stu-id="d6297-148">item0a</span></span>  
  
- <span data-ttu-id="d6297-149">item1</span><span class="sxs-lookup"><span data-stu-id="d6297-149">item1</span></span>  
  
  -   <span data-ttu-id="d6297-150">item1a</span><span class="sxs-lookup"><span data-stu-id="d6297-150">item1a</span></span>  
  
  -   <span data-ttu-id="d6297-151">item1b</span><span class="sxs-lookup"><span data-stu-id="d6297-151">item1b</span></span>  
  
  -   <span data-ttu-id="d6297-152">item1c</span><span class="sxs-lookup"><span data-stu-id="d6297-152">item1c</span></span>  
  
- <span data-ttu-id="d6297-153">item2</span><span class="sxs-lookup"><span data-stu-id="d6297-153">item2</span></span>  
  
  -   <span data-ttu-id="d6297-154">item2a</span><span class="sxs-lookup"><span data-stu-id="d6297-154">item2a</span></span>  
  
  -   <span data-ttu-id="d6297-155">item2b</span><span class="sxs-lookup"><span data-stu-id="d6297-155">item2b</span></span>  
  
  <span data-ttu-id="d6297-156">Item1b と item2 のすべてを削除するには、item1b と item2 へのキーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d6297-156">You can delete item1b and all of item2 by giving the keys to item1b and item2:</span></span>  
  
- <span data-ttu-id="d6297-157">item1</span><span class="sxs-lookup"><span data-stu-id="d6297-157">item1</span></span>  
  
  -   <span data-ttu-id="d6297-158">item1b</span><span class="sxs-lookup"><span data-stu-id="d6297-158">item1b</span></span>  
  
- <span data-ttu-id="d6297-159">item2</span><span class="sxs-lookup"><span data-stu-id="d6297-159">item2</span></span>  
  
  <span data-ttu-id="d6297-160">Item2 の空のサブ コレクションを用意すると、リーフに有効にしてそのサブブランチ全体が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6297-160">By providing an empty sub-collection for item2, you turn it into a leaf and that entire sub-branch is deleted.</span></span> <span data-ttu-id="d6297-161">呼び出しの後、サーバーは、残りの項目があります。</span><span class="sxs-lookup"><span data-stu-id="d6297-161">After the call, the server has the remaining items:</span></span>  
  
- <span data-ttu-id="d6297-162">item0</span><span class="sxs-lookup"><span data-stu-id="d6297-162">item0</span></span>  
  
  -   <span data-ttu-id="d6297-163">item0a</span><span class="sxs-lookup"><span data-stu-id="d6297-163">item0a</span></span>  
  
- <span data-ttu-id="d6297-164">item1</span><span class="sxs-lookup"><span data-stu-id="d6297-164">item1</span></span>  
  
  -   <span data-ttu-id="d6297-165">item1a</span><span class="sxs-lookup"><span data-stu-id="d6297-165">item1a</span></span>  
  
  -   <span data-ttu-id="d6297-166">item1c</span><span class="sxs-lookup"><span data-stu-id="d6297-166">item1c</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6297-167">参照</span><span class="sxs-lookup"><span data-stu-id="d6297-167">See Also</span></span>  
 [<span data-ttu-id="d6297-168">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="d6297-168">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)