---
title: SAP アダプターの SAPParameterCollection クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameterCollection, supported methods and classes
ms.assetid: fd09355b-95f4-4d49-a643-b13058e63d74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c94dc7e8219a2439d58fbfea78fc7fe9c42b64bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372918"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a><span data-ttu-id="129e1-102">SAP アダプターの SAPParameterCollection クラス</span><span class="sxs-lookup"><span data-stu-id="129e1-102">SAPParameterCollection class in the SAP adapter</span></span>
<span data-ttu-id="129e1-103">メソッドおよびプロパティを次のセクションの一覧、 **SAPParameterCollection**クラス。</span><span class="sxs-lookup"><span data-stu-id="129e1-103">The following section lists the methods and properties for the **SAPParameterCollection** class.</span></span> <span data-ttu-id="129e1-104">これは、派生元**System.Data.Common.DbParameterCollection**します。</span><span class="sxs-lookup"><span data-stu-id="129e1-104">This is derived from **System.Data.Common.DbParameterCollection**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="129e1-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="129e1-105">Supported Properties</span></span>  
  
|<span data-ttu-id="129e1-106">名前</span><span class="sxs-lookup"><span data-stu-id="129e1-106">Name</span></span>|<span data-ttu-id="129e1-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="129e1-107">Get/Set</span></span>|<span data-ttu-id="129e1-108">説明</span><span class="sxs-lookup"><span data-stu-id="129e1-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="129e1-109">**Count**</span><span class="sxs-lookup"><span data-stu-id="129e1-109">**Count**</span></span>|<span data-ttu-id="129e1-110">取得</span><span class="sxs-lookup"><span data-stu-id="129e1-110">Get</span></span>|<span data-ttu-id="129e1-111">コレクション内のパラメーターの数。</span><span class="sxs-lookup"><span data-stu-id="129e1-111">Number of parameters in the collection.</span></span>|  
|<span data-ttu-id="129e1-112">**IsFixedSize**</span><span class="sxs-lookup"><span data-stu-id="129e1-112">**IsFixedSize**</span></span>|<span data-ttu-id="129e1-113">取得</span><span class="sxs-lookup"><span data-stu-id="129e1-113">Get</span></span>|<span data-ttu-id="129e1-114">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="129e1-114">Not supported.</span></span> <span data-ttu-id="129e1-115">False を返します。</span><span class="sxs-lookup"><span data-stu-id="129e1-115">Returns false.</span></span>|  
|<span data-ttu-id="129e1-116">**IsReadOnly**</span><span class="sxs-lookup"><span data-stu-id="129e1-116">**IsReadOnly**</span></span>|<span data-ttu-id="129e1-117">取得</span><span class="sxs-lookup"><span data-stu-id="129e1-117">Get</span></span>|<span data-ttu-id="129e1-118">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="129e1-118">Not supported.</span></span> <span data-ttu-id="129e1-119">False を返します。</span><span class="sxs-lookup"><span data-stu-id="129e1-119">Returns false.</span></span>|  
|<span data-ttu-id="129e1-120">**IsSynchronized**</span><span class="sxs-lookup"><span data-stu-id="129e1-120">**IsSynchronized**</span></span>|<span data-ttu-id="129e1-121">取得</span><span class="sxs-lookup"><span data-stu-id="129e1-121">Get</span></span>|<span data-ttu-id="129e1-122">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="129e1-122">Not supported.</span></span> <span data-ttu-id="129e1-123">False を返します。</span><span class="sxs-lookup"><span data-stu-id="129e1-123">Returns false.</span></span>|  
|<span data-ttu-id="129e1-124">**SyncRoot**</span><span class="sxs-lookup"><span data-stu-id="129e1-124">**SyncRoot**</span></span>|<span data-ttu-id="129e1-125">取得</span><span class="sxs-lookup"><span data-stu-id="129e1-125">Get</span></span>|<span data-ttu-id="129e1-126">ロック オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="129e1-126">Returns the lock object.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="129e1-127">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="129e1-127">Supported Methods</span></span>  
  
|<span data-ttu-id="129e1-128">名前</span><span class="sxs-lookup"><span data-stu-id="129e1-128">Name</span></span>|<span data-ttu-id="129e1-129">説明</span><span class="sxs-lookup"><span data-stu-id="129e1-129">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="129e1-130">**Add(SAPParameter)**</span><span class="sxs-lookup"><span data-stu-id="129e1-130">**Add(SAPParameter)**</span></span>|<span data-ttu-id="129e1-131">パラメーターは、1 つ以上の ParameterCollection に属することはできません。</span><span class="sxs-lookup"><span data-stu-id="129e1-131">Parameter cannot belong to more than one ParameterCollection.</span></span>|  
|<span data-ttu-id="129e1-132">**Add(object)**</span><span class="sxs-lookup"><span data-stu-id="129e1-132">**Add(object)**</span></span>|<span data-ttu-id="129e1-133">オブジェクトは、SAPParameter 型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="129e1-133">Object should be of SAPParameter type.</span></span>|  
|<span data-ttu-id="129e1-134">**AddRange(System.Array)**</span><span class="sxs-lookup"><span data-stu-id="129e1-134">**AddRange(System.Array)**</span></span>|<span data-ttu-id="129e1-135">SAPParameter インスタンスの配列を追加します。</span><span class="sxs-lookup"><span data-stu-id="129e1-135">Adds an array of SAPParameter instances.</span></span>|  
|<span data-ttu-id="129e1-136">**Clear()**</span><span class="sxs-lookup"><span data-stu-id="129e1-136">**Clear()**</span></span>|<span data-ttu-id="129e1-137">コレクション内のパラメーターを消去します。</span><span class="sxs-lookup"><span data-stu-id="129e1-137">Clears the parameters in the collection.</span></span>|  
|<span data-ttu-id="129e1-138">**Contains(object)**</span><span class="sxs-lookup"><span data-stu-id="129e1-138">**Contains(object)**</span></span>|<span data-ttu-id="129e1-139">パラメーターのインスタンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="129e1-139">Checks based on parameter instance.</span></span>|  
|<span data-ttu-id="129e1-140">**Contains(string)**</span><span class="sxs-lookup"><span data-stu-id="129e1-140">**Contains(string)**</span></span>|<span data-ttu-id="129e1-141">パラメーター名に基づいたチェックします。</span><span class="sxs-lookup"><span data-stu-id="129e1-141">Checks based on parameter name.</span></span>|  
|<span data-ttu-id="129e1-142">**CopyTo (SAPParameter, int)**</span><span class="sxs-lookup"><span data-stu-id="129e1-142">**CopyTo(SAPParameter[], int)**</span></span>|<span data-ttu-id="129e1-143">SAPParameter 型の配列にパラメーター リストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="129e1-143">Copies parameter list to an array of SAPParameter types.</span></span>|  
|<span data-ttu-id="129e1-144">**CopyTo(System.Array, int)**</span><span class="sxs-lookup"><span data-stu-id="129e1-144">**CopyTo(System.Array, int)**</span></span>|<span data-ttu-id="129e1-145">配列にパラメーター リストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="129e1-145">Copies parameter list to an array.</span></span>|  
|<span data-ttu-id="129e1-146">**GetEnumerator()**</span><span class="sxs-lookup"><span data-stu-id="129e1-146">**GetEnumerator()**</span></span>|<span data-ttu-id="129e1-147">パラメーターのコレクションの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="129e1-147">Gets an enumerator for the parameters in the collection.</span></span>|  
|<span data-ttu-id="129e1-148">**IndexOf(object)**</span><span class="sxs-lookup"><span data-stu-id="129e1-148">**IndexOf(object)**</span></span>|<span data-ttu-id="129e1-149">SAPParameter インスタンスに基づいて、パラメーターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="129e1-149">Index of parameter based on SAPParameter instance.</span></span>|  
|<span data-ttu-id="129e1-150">**IndexOf(string)**</span><span class="sxs-lookup"><span data-stu-id="129e1-150">**IndexOf(string)**</span></span>|<span data-ttu-id="129e1-151">SAPParameter 名に基づいて、パラメーターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="129e1-151">Index of parameter based on SAPParameter name.</span></span>|  
|<span data-ttu-id="129e1-152">**Insert(int, object)**</span><span class="sxs-lookup"><span data-stu-id="129e1-152">**Insert(int, object)**</span></span>|<span data-ttu-id="129e1-153">コレクション内に、SAPParameter を挿入します。</span><span class="sxs-lookup"><span data-stu-id="129e1-153">Inserts an SAPParameter into the collection.</span></span>|  
|<span data-ttu-id="129e1-154">**Remove(object)**</span><span class="sxs-lookup"><span data-stu-id="129e1-154">**Remove(object)**</span></span>|<span data-ttu-id="129e1-155">インスタンスに基づくコレクションに、SAPParameter を削除します。</span><span class="sxs-lookup"><span data-stu-id="129e1-155">Removes an SAPParameter into the collection based on instance.</span></span>|  
|<span data-ttu-id="129e1-156">**RemoveAt(int)**</span><span class="sxs-lookup"><span data-stu-id="129e1-156">**RemoveAt(int)**</span></span>|<span data-ttu-id="129e1-157">コレクション内の指定したインデックスに、SAPParameter を削除します。</span><span class="sxs-lookup"><span data-stu-id="129e1-157">Removes an SAPParameter into the collection at a given index.</span></span>|  
|<span data-ttu-id="129e1-158">**RemoveAt(string)**</span><span class="sxs-lookup"><span data-stu-id="129e1-158">**RemoveAt(string)**</span></span>|<span data-ttu-id="129e1-159">名前に基づくコレクションに、SAPParameter を削除します。</span><span class="sxs-lookup"><span data-stu-id="129e1-159">Removes an SAPParameter into the collection based on name.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="129e1-160">参照</span><span class="sxs-lookup"><span data-stu-id="129e1-160">See Also</span></span>  
 [<span data-ttu-id="129e1-161">SAP アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="129e1-161">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)