---
title: SAP アダプターで SAPParameterCollection クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 924cb884c64f337cec0e628c804b5c5a8c6cf37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a><span data-ttu-id="3ca53-102">SAP アダプターで SAPParameterCollection クラス</span><span class="sxs-lookup"><span data-stu-id="3ca53-102">SAPParameterCollection class in the SAP adapter</span></span>
<span data-ttu-id="3ca53-103">次のセクションではメソッドとプロパティの一覧表示、 **SAPParameterCollection**クラスです。</span><span class="sxs-lookup"><span data-stu-id="3ca53-103">The following section lists the methods and properties for the **SAPParameterCollection** class.</span></span> <span data-ttu-id="3ca53-104">これは、派生元**System.Data.Common.DbParameterCollection**です。</span><span class="sxs-lookup"><span data-stu-id="3ca53-104">This is derived from **System.Data.Common.DbParameterCollection**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="3ca53-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="3ca53-105">Supported Properties</span></span>  
  
|<span data-ttu-id="3ca53-106">名前</span><span class="sxs-lookup"><span data-stu-id="3ca53-106">Name</span></span>|<span data-ttu-id="3ca53-107">取得/設定</span><span class="sxs-lookup"><span data-stu-id="3ca53-107">Get/Set</span></span>|<span data-ttu-id="3ca53-108">Description</span><span class="sxs-lookup"><span data-stu-id="3ca53-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="3ca53-109">**Count**</span><span class="sxs-lookup"><span data-stu-id="3ca53-109">**Count**</span></span>|<span data-ttu-id="3ca53-110">取得</span><span class="sxs-lookup"><span data-stu-id="3ca53-110">Get</span></span>|<span data-ttu-id="3ca53-111">コレクション内のパラメーターの数。</span><span class="sxs-lookup"><span data-stu-id="3ca53-111">Number of parameters in the collection.</span></span>|  
|<span data-ttu-id="3ca53-112">**IsFixedSize**</span><span class="sxs-lookup"><span data-stu-id="3ca53-112">**IsFixedSize**</span></span>|<span data-ttu-id="3ca53-113">取得</span><span class="sxs-lookup"><span data-stu-id="3ca53-113">Get</span></span>|<span data-ttu-id="3ca53-114">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ca53-114">Not supported.</span></span> <span data-ttu-id="3ca53-115">False を返します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-115">Returns false.</span></span>|  
|<span data-ttu-id="3ca53-116">**IsReadOnly**</span><span class="sxs-lookup"><span data-stu-id="3ca53-116">**IsReadOnly**</span></span>|<span data-ttu-id="3ca53-117">取得</span><span class="sxs-lookup"><span data-stu-id="3ca53-117">Get</span></span>|<span data-ttu-id="3ca53-118">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ca53-118">Not supported.</span></span> <span data-ttu-id="3ca53-119">False を返します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-119">Returns false.</span></span>|  
|<span data-ttu-id="3ca53-120">**IsSynchronized**</span><span class="sxs-lookup"><span data-stu-id="3ca53-120">**IsSynchronized**</span></span>|<span data-ttu-id="3ca53-121">取得</span><span class="sxs-lookup"><span data-stu-id="3ca53-121">Get</span></span>|<span data-ttu-id="3ca53-122">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ca53-122">Not supported.</span></span> <span data-ttu-id="3ca53-123">False を返します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-123">Returns false.</span></span>|  
|<span data-ttu-id="3ca53-124">**SyncRoot**</span><span class="sxs-lookup"><span data-stu-id="3ca53-124">**SyncRoot**</span></span>|<span data-ttu-id="3ca53-125">取得</span><span class="sxs-lookup"><span data-stu-id="3ca53-125">Get</span></span>|<span data-ttu-id="3ca53-126">ロック オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-126">Returns the lock object.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="3ca53-127">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="3ca53-127">Supported Methods</span></span>  
  
|<span data-ttu-id="3ca53-128">名前</span><span class="sxs-lookup"><span data-stu-id="3ca53-128">Name</span></span>|<span data-ttu-id="3ca53-129">Description</span><span class="sxs-lookup"><span data-stu-id="3ca53-129">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3ca53-130">**Add(SAPParameter)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-130">**Add(SAPParameter)**</span></span>|<span data-ttu-id="3ca53-131">パラメーターは、1 つ以上の ParameterCollection に属することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca53-131">Parameter cannot belong to more than one ParameterCollection.</span></span>|  
|<span data-ttu-id="3ca53-132">**してください。**</span><span class="sxs-lookup"><span data-stu-id="3ca53-132">**Add(object)**</span></span>|<span data-ttu-id="3ca53-133">オブジェクトは、SAPParameter 型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3ca53-133">Object should be of SAPParameter type.</span></span>|  
|<span data-ttu-id="3ca53-134">**AddRange(System.Array)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-134">**AddRange(System.Array)**</span></span>|<span data-ttu-id="3ca53-135">SAPParameter インスタンスの配列を追加します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-135">Adds an array of SAPParameter instances.</span></span>|  
|<span data-ttu-id="3ca53-136">**Clear()**</span><span class="sxs-lookup"><span data-stu-id="3ca53-136">**Clear()**</span></span>|<span data-ttu-id="3ca53-137">コレクション内のパラメーターを消去します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-137">Clears the parameters in the collection.</span></span>|  
|<span data-ttu-id="3ca53-138">**Contains(object)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-138">**Contains(object)**</span></span>|<span data-ttu-id="3ca53-139">パラメーターのインスタンスに基づいてチェックします。</span><span class="sxs-lookup"><span data-stu-id="3ca53-139">Checks based on parameter instance.</span></span>|  
|<span data-ttu-id="3ca53-140">**Contains(string)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-140">**Contains(string)**</span></span>|<span data-ttu-id="3ca53-141">パラメーター名に基づいたチェックします。</span><span class="sxs-lookup"><span data-stu-id="3ca53-141">Checks based on parameter name.</span></span>|  
|<span data-ttu-id="3ca53-142">**CopyTo (SAPParameter, int)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-142">**CopyTo(SAPParameter[], int)**</span></span>|<span data-ttu-id="3ca53-143">SAPParameter 型の配列にパラメーター リストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3ca53-143">Copies parameter list to an array of SAPParameter types.</span></span>|  
|<span data-ttu-id="3ca53-144">**CopyTo (System.Array、int)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-144">**CopyTo(System.Array, int)**</span></span>|<span data-ttu-id="3ca53-145">配列にパラメーター リストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3ca53-145">Copies parameter list to an array.</span></span>|  
|<span data-ttu-id="3ca53-146">**GetEnumerator()**</span><span class="sxs-lookup"><span data-stu-id="3ca53-146">**GetEnumerator()**</span></span>|<span data-ttu-id="3ca53-147">パラメーターのコレクションの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-147">Gets an enumerator for the parameters in the collection.</span></span>|  
|<span data-ttu-id="3ca53-148">**IndexOf(object)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-148">**IndexOf(object)**</span></span>|<span data-ttu-id="3ca53-149">SAPParameter インスタンスに基づいて、パラメーターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="3ca53-149">Index of parameter based on SAPParameter instance.</span></span>|  
|<span data-ttu-id="3ca53-150">**IndexOf(string)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-150">**IndexOf(string)**</span></span>|<span data-ttu-id="3ca53-151">SAPParameter 名に基づくパラメーターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="3ca53-151">Index of parameter based on SAPParameter name.</span></span>|  
|<span data-ttu-id="3ca53-152">**挿入 (int, object)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-152">**Insert(int, object)**</span></span>|<span data-ttu-id="3ca53-153">コレクションに、SAPParameter を挿入します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-153">Inserts an SAPParameter into the collection.</span></span>|  
|<span data-ttu-id="3ca53-154">**Remove(object)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-154">**Remove(object)**</span></span>|<span data-ttu-id="3ca53-155">インスタンスに基づくコレクションに、SAPParameter を削除します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-155">Removes an SAPParameter into the collection based on instance.</span></span>|  
|<span data-ttu-id="3ca53-156">**RemoveAt(int)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-156">**RemoveAt(int)**</span></span>|<span data-ttu-id="3ca53-157">コレクション内の指定したインデックス位置に、SAPParameter を削除します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-157">Removes an SAPParameter into the collection at a given index.</span></span>|  
|<span data-ttu-id="3ca53-158">**RemoveAt(string)**</span><span class="sxs-lookup"><span data-stu-id="3ca53-158">**RemoveAt(string)**</span></span>|<span data-ttu-id="3ca53-159">名前に基づくコレクションに、SAPParameter を削除します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-159">Removes an SAPParameter into the collection based on name.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ca53-160">参照</span><span class="sxs-lookup"><span data-stu-id="3ca53-160">See Also</span></span>  
 [<span data-ttu-id="3ca53-161">SAP アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="3ca53-161">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)