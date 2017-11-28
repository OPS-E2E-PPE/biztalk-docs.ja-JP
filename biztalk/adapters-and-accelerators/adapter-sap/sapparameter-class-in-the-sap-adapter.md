---
title: "SAP アダプターで SAPParameter クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ff43c344cc14adb3deef226c270adc3ca94f2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapparameter-class-in-the-sap-adapter"></a><span data-ttu-id="a2cf6-102">SAP アダプターで SAPParameter クラス</span><span class="sxs-lookup"><span data-stu-id="a2cf6-102">SAPParameter class in the SAP adapter</span></span>
<span data-ttu-id="a2cf6-103">次のセクションではメソッドとプロパティの一覧表示、 **SAPParameter**クラスです。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-103">The following section lists the methods and properties for the **SAPParameter** class.</span></span> <span data-ttu-id="a2cf6-104">これは、派生元**System.Data.Common.DbParameter**です。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-104">This is derived from **System.Data.Common.DbParameter**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="a2cf6-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="a2cf6-105">Supported Properties</span></span>  
  
|<span data-ttu-id="a2cf6-106">名前</span><span class="sxs-lookup"><span data-stu-id="a2cf6-106">Name</span></span>|<span data-ttu-id="a2cf6-107">取得/設定</span><span class="sxs-lookup"><span data-stu-id="a2cf6-107">Get/Set</span></span>|<span data-ttu-id="a2cf6-108">Description</span><span class="sxs-lookup"><span data-stu-id="a2cf6-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="a2cf6-109">**DbType**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-109">**DbType**</span></span>|<span data-ttu-id="a2cf6-110">取得</span><span class="sxs-lookup"><span data-stu-id="a2cf6-110">Get</span></span>|<span data-ttu-id="a2cf6-111">DbType 場合は、パラメーターが返されます。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-111">DbType if the parameter returned.</span></span> <span data-ttu-id="a2cf6-112">設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-112">Cannot be set.</span></span>|  
|<span data-ttu-id="a2cf6-113">**方向**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-113">**Direction**</span></span>|<span data-ttu-id="a2cf6-114">Get および Set</span><span class="sxs-lookup"><span data-stu-id="a2cf6-114">Get and Set</span></span>|<span data-ttu-id="a2cf6-115">ParameterDirection.ReturnValue がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-115">ParameterDirection.ReturnValue not supported.</span></span>|  
|<span data-ttu-id="a2cf6-116">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-116">**IsNullable**</span></span>|-|<span data-ttu-id="a2cf6-117">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-117">Not supported.</span></span>|  
|<span data-ttu-id="a2cf6-118">**パラメーター名**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-118">**ParameterName**</span></span>|<span data-ttu-id="a2cf6-119">Get および Set</span><span class="sxs-lookup"><span data-stu-id="a2cf6-119">Get and Set</span></span>|<span data-ttu-id="a2cf6-120">パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-120">Name of the parameter.</span></span>|  
|<span data-ttu-id="a2cf6-121">**サイズ**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-121">**Size**</span></span>|-|<span data-ttu-id="a2cf6-122">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-122">Not supported.</span></span>|  
|<span data-ttu-id="a2cf6-123">**SourceColumn**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-123">**SourceColumn**</span></span>|-|<span data-ttu-id="a2cf6-124">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-124">Not supported.</span></span>|  
|<span data-ttu-id="a2cf6-125">**SourceColumnNullMapping**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-125">**SourceColumnNullMapping**</span></span>|-|<span data-ttu-id="a2cf6-126">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-126">Not supported.</span></span>|  
|<span data-ttu-id="a2cf6-127">**SourceVersion**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-127">**SourceVersion**</span></span>|-|<span data-ttu-id="a2cf6-128">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-128">Not supported.</span></span>|  
|<span data-ttu-id="a2cf6-129">**値**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-129">**Value**</span></span>|<span data-ttu-id="a2cf6-130">Get および Set</span><span class="sxs-lookup"><span data-stu-id="a2cf6-130">Get and Set</span></span>|<span data-ttu-id="a2cf6-131">パラメーターの値</span><span class="sxs-lookup"><span data-stu-id="a2cf6-131">Value of the parameter</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="a2cf6-132">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="a2cf6-132">Supported Methods</span></span>  
  
|<span data-ttu-id="a2cf6-133">名前</span><span class="sxs-lookup"><span data-stu-id="a2cf6-133">Name</span></span>|<span data-ttu-id="a2cf6-134">Description</span><span class="sxs-lookup"><span data-stu-id="a2cf6-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="a2cf6-135">**ResetDbType()**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-135">**ResetDbType()**</span></span>|<span data-ttu-id="a2cf6-136">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-136">Not supported.</span></span>|  
  
## <a name="supported-constructors"></a><span data-ttu-id="a2cf6-137">サポートされているコンス トラクター</span><span class="sxs-lookup"><span data-stu-id="a2cf6-137">Supported Constructors</span></span>  
  
|<span data-ttu-id="a2cf6-138">名前</span><span class="sxs-lookup"><span data-stu-id="a2cf6-138">Name</span></span>|<span data-ttu-id="a2cf6-139">Description</span><span class="sxs-lookup"><span data-stu-id="a2cf6-139">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="a2cf6-140">**SAPParameter()**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-140">**SAPParameter()**</span></span>|<span data-ttu-id="a2cf6-141">SAP パラメーターのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-141">SAP parameter instance.</span></span>|  
|<span data-ttu-id="a2cf6-142">**SAPParameter(string)**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-142">**SAPParameter(string)**</span></span>|<span data-ttu-id="a2cf6-143">SAP パラメーターの名前を持つ SAP パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-143">SAP parameter with SAP parameter name.</span></span>|  
|<span data-ttu-id="a2cf6-144">**SAPParameter (string, DbType)**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-144">**SAPParameter(string, DbType)**</span></span>|<span data-ttu-id="a2cf6-145">SAP パラメーター名と DbType SAP パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-145">SAP parameter with SAP parameter name and DbType.</span></span>|  
|<span data-ttu-id="a2cf6-146">**SAPParameter (文字列、オブジェクト)**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-146">**SAPParameter(string, object)**</span></span>|<span data-ttu-id="a2cf6-147">SAP パラメーター名と値を持つ SAP パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-147">SAP parameter with SAP parameter name and value.</span></span> <span data-ttu-id="a2cf6-148">複合型では、データ テーブルの型の値と XML 文字列があります。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-148">Complex types have value of type DataTable and XML string.</span></span>|  
|<span data-ttu-id="a2cf6-149">**SAPParameter (string, ParameterDirection)**</span><span class="sxs-lookup"><span data-stu-id="a2cf6-149">**SAPParameter(string, ParameterDirection)**</span></span>|<span data-ttu-id="a2cf6-150">SAP パラメーターの名前とパラメーターの方向と SAP のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-150">SAP parameter with SAP parameter name and parameter direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2cf6-151">参照</span><span class="sxs-lookup"><span data-stu-id="a2cf6-151">See Also</span></span>  
 [<span data-ttu-id="a2cf6-152">SAP アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="a2cf6-152">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)