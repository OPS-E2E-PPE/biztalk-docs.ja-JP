---
title: SAP アダプターの SAPParameter クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f87932d7add9723d67e0af822a8d6f389b59fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372942"
---
# <a name="sapparameter-class-in-the-sap-adapter"></a><span data-ttu-id="dface-102">SAP アダプターの SAPParameter クラス</span><span class="sxs-lookup"><span data-stu-id="dface-102">SAPParameter class in the SAP adapter</span></span>
<span data-ttu-id="dface-103">メソッドおよびプロパティを次のセクションの一覧、 **SAPParameter**クラス。</span><span class="sxs-lookup"><span data-stu-id="dface-103">The following section lists the methods and properties for the **SAPParameter** class.</span></span> <span data-ttu-id="dface-104">これは、派生元**System.Data.Common.DbParameter**します。</span><span class="sxs-lookup"><span data-stu-id="dface-104">This is derived from **System.Data.Common.DbParameter**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="dface-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="dface-105">Supported Properties</span></span>  
  
|<span data-ttu-id="dface-106">名前</span><span class="sxs-lookup"><span data-stu-id="dface-106">Name</span></span>|<span data-ttu-id="dface-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="dface-107">Get/Set</span></span>|<span data-ttu-id="dface-108">説明</span><span class="sxs-lookup"><span data-stu-id="dface-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="dface-109">**DbType**</span><span class="sxs-lookup"><span data-stu-id="dface-109">**DbType**</span></span>|<span data-ttu-id="dface-110">取得</span><span class="sxs-lookup"><span data-stu-id="dface-110">Get</span></span>|<span data-ttu-id="dface-111">DbType 場合は、パラメーターが返されます。</span><span class="sxs-lookup"><span data-stu-id="dface-111">DbType if the parameter returned.</span></span> <span data-ttu-id="dface-112">設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dface-112">Cannot be set.</span></span>|  
|<span data-ttu-id="dface-113">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="dface-113">**Direction**</span></span>|<span data-ttu-id="dface-114">Get と Set</span><span class="sxs-lookup"><span data-stu-id="dface-114">Get and Set</span></span>|<span data-ttu-id="dface-115">ParameterDirection.ReturnValue がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-115">ParameterDirection.ReturnValue not supported.</span></span>|  
|<span data-ttu-id="dface-116">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="dface-116">**IsNullable**</span></span>|-|<span data-ttu-id="dface-117">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-117">Not supported.</span></span>|  
|<span data-ttu-id="dface-118">**ParameterName**</span><span class="sxs-lookup"><span data-stu-id="dface-118">**ParameterName**</span></span>|<span data-ttu-id="dface-119">Get と Set</span><span class="sxs-lookup"><span data-stu-id="dface-119">Get and Set</span></span>|<span data-ttu-id="dface-120">パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="dface-120">Name of the parameter.</span></span>|  
|<span data-ttu-id="dface-121">**Size**</span><span class="sxs-lookup"><span data-stu-id="dface-121">**Size**</span></span>|-|<span data-ttu-id="dface-122">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-122">Not supported.</span></span>|  
|<span data-ttu-id="dface-123">**SourceColumn**</span><span class="sxs-lookup"><span data-stu-id="dface-123">**SourceColumn**</span></span>|-|<span data-ttu-id="dface-124">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-124">Not supported.</span></span>|  
|<span data-ttu-id="dface-125">**SourceColumnNullMapping**</span><span class="sxs-lookup"><span data-stu-id="dface-125">**SourceColumnNullMapping**</span></span>|-|<span data-ttu-id="dface-126">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-126">Not supported.</span></span>|  
|<span data-ttu-id="dface-127">**SourceVersion**</span><span class="sxs-lookup"><span data-stu-id="dface-127">**SourceVersion**</span></span>|-|<span data-ttu-id="dface-128">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-128">Not supported.</span></span>|  
|<span data-ttu-id="dface-129">**[値]**</span><span class="sxs-lookup"><span data-stu-id="dface-129">**Value**</span></span>|<span data-ttu-id="dface-130">Get と Set</span><span class="sxs-lookup"><span data-stu-id="dface-130">Get and Set</span></span>|<span data-ttu-id="dface-131">パラメーターの値</span><span class="sxs-lookup"><span data-stu-id="dface-131">Value of the parameter</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="dface-132">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="dface-132">Supported Methods</span></span>  
  
|<span data-ttu-id="dface-133">名前</span><span class="sxs-lookup"><span data-stu-id="dface-133">Name</span></span>|<span data-ttu-id="dface-134">説明</span><span class="sxs-lookup"><span data-stu-id="dface-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dface-135">**ResetDbType()**</span><span class="sxs-lookup"><span data-stu-id="dface-135">**ResetDbType()**</span></span>|<span data-ttu-id="dface-136">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dface-136">Not supported.</span></span>|  
  
## <a name="supported-constructors"></a><span data-ttu-id="dface-137">サポートされているコンス トラクター</span><span class="sxs-lookup"><span data-stu-id="dface-137">Supported Constructors</span></span>  
  
|<span data-ttu-id="dface-138">名前</span><span class="sxs-lookup"><span data-stu-id="dface-138">Name</span></span>|<span data-ttu-id="dface-139">説明</span><span class="sxs-lookup"><span data-stu-id="dface-139">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dface-140">**SAPParameter()**</span><span class="sxs-lookup"><span data-stu-id="dface-140">**SAPParameter()**</span></span>|<span data-ttu-id="dface-141">SAP パラメーターのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="dface-141">SAP parameter instance.</span></span>|  
|<span data-ttu-id="dface-142">**SAPParameter(string)**</span><span class="sxs-lookup"><span data-stu-id="dface-142">**SAPParameter(string)**</span></span>|<span data-ttu-id="dface-143">SAP SAP パラメーターの名前のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="dface-143">SAP parameter with SAP parameter name.</span></span>|  
|<span data-ttu-id="dface-144">**SAPParameter(string, DbType)**</span><span class="sxs-lookup"><span data-stu-id="dface-144">**SAPParameter(string, DbType)**</span></span>|<span data-ttu-id="dface-145">SAP パラメーター名と DbType SAP パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dface-145">SAP parameter with SAP parameter name and DbType.</span></span>|  
|<span data-ttu-id="dface-146">**SAPParameter (文字列、オブジェクト)**</span><span class="sxs-lookup"><span data-stu-id="dface-146">**SAPParameter(string, object)**</span></span>|<span data-ttu-id="dface-147">SAP パラメーター名および値を持つ SAP パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dface-147">SAP parameter with SAP parameter name and value.</span></span> <span data-ttu-id="dface-148">複合型は、DataTable の型の値と XML 文字列があります。</span><span class="sxs-lookup"><span data-stu-id="dface-148">Complex types have value of type DataTable and XML string.</span></span>|  
|<span data-ttu-id="dface-149">**SAPParameter(string, ParameterDirection)**</span><span class="sxs-lookup"><span data-stu-id="dface-149">**SAPParameter(string, ParameterDirection)**</span></span>|<span data-ttu-id="dface-150">SAP パラメーターの名前とパラメーターの方向を持つ SAP パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dface-150">SAP parameter with SAP parameter name and parameter direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dface-151">参照</span><span class="sxs-lookup"><span data-stu-id="dface-151">See Also</span></span>  
 [<span data-ttu-id="dface-152">SAP アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="dface-152">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)