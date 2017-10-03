---
title: "SAP アダプターで SAPDataReader クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a><span data-ttu-id="78cfb-102">SAP アダプターで SAPDataReader クラス</span><span class="sxs-lookup"><span data-stu-id="78cfb-102">SAPDataReader class in the SAP adapter</span></span>
<span data-ttu-id="78cfb-103">次のセクションではメソッドとプロパティの一覧表示、 **SAPDataReader**クラスです。</span><span class="sxs-lookup"><span data-stu-id="78cfb-103">The following section lists the methods and properties for the **SAPDataReader** class.</span></span> <span data-ttu-id="78cfb-104">これは、派生元**System.Data.Common.DbDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="78cfb-104">This is derived from **System.Data.Common.DbDataReader**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="78cfb-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="78cfb-105">Supported Properties</span></span>  
  
|<span data-ttu-id="78cfb-106">名前</span><span class="sxs-lookup"><span data-stu-id="78cfb-106">Name</span></span>|<span data-ttu-id="78cfb-107">取得/設定</span><span class="sxs-lookup"><span data-stu-id="78cfb-107">Get/Set</span></span>|<span data-ttu-id="78cfb-108">Description</span><span class="sxs-lookup"><span data-stu-id="78cfb-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="78cfb-109">**[奥行]**</span><span class="sxs-lookup"><span data-stu-id="78cfb-109">**Depth**</span></span>|<span data-ttu-id="78cfb-110">取得</span><span class="sxs-lookup"><span data-stu-id="78cfb-110">Get</span></span>|<span data-ttu-id="78cfb-111">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78cfb-111">Not supported.</span></span> <span data-ttu-id="78cfb-112">0 を返します。</span><span class="sxs-lookup"><span data-stu-id="78cfb-112">Returns 0.</span></span>|  
|<span data-ttu-id="78cfb-113">**FieldCount**</span><span class="sxs-lookup"><span data-stu-id="78cfb-113">**FieldCount**</span></span>|<span data-ttu-id="78cfb-114">取得</span><span class="sxs-lookup"><span data-stu-id="78cfb-114">Get</span></span>|<span data-ttu-id="78cfb-115">現在のレコード セット内のフィールドの数</span><span class="sxs-lookup"><span data-stu-id="78cfb-115">Number of fields in the current record set</span></span>|  
|<span data-ttu-id="78cfb-116">**IsClosed**</span><span class="sxs-lookup"><span data-stu-id="78cfb-116">**IsClosed**</span></span>|<span data-ttu-id="78cfb-117">取得</span><span class="sxs-lookup"><span data-stu-id="78cfb-117">Get</span></span>|<span data-ttu-id="78cfb-118">データ リーダーの状態を返します</span><span class="sxs-lookup"><span data-stu-id="78cfb-118">Returns status of data reader</span></span>|  
|<span data-ttu-id="78cfb-119">**RecordsAffected**</span><span class="sxs-lookup"><span data-stu-id="78cfb-119">**RecordsAffected**</span></span>|<span data-ttu-id="78cfb-120">取得</span><span class="sxs-lookup"><span data-stu-id="78cfb-120">Get</span></span>|<span data-ttu-id="78cfb-121">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78cfb-121">Not supported.</span></span> <span data-ttu-id="78cfb-122">-1 を返します</span><span class="sxs-lookup"><span data-stu-id="78cfb-122">Returns -1</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="78cfb-123">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="78cfb-123">Supported Methods</span></span>  
  
|<span data-ttu-id="78cfb-124">名前</span><span class="sxs-lookup"><span data-stu-id="78cfb-124">Name</span></span>|<span data-ttu-id="78cfb-125">Description</span><span class="sxs-lookup"><span data-stu-id="78cfb-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="78cfb-126">**Close()**</span><span class="sxs-lookup"><span data-stu-id="78cfb-126">**Close()**</span></span>|<span data-ttu-id="78cfb-127">DataReader を終了します。</span><span class="sxs-lookup"><span data-stu-id="78cfb-127">Closes the DataReader</span></span>|  
|<span data-ttu-id="78cfb-128">**Get [メソッド]**<sup>*</sup></span><span class="sxs-lookup"><span data-stu-id="78cfb-128">**Get [methods]** <sup>*</sup></span></span><br /><br /> <span data-ttu-id="78cfb-129">ここで [メソッド] は、予想されるデータ型です。</span><span class="sxs-lookup"><span data-stu-id="78cfb-129">where [methods] is the expected data type.</span></span> <span data-ttu-id="78cfb-130">例:</span><span class="sxs-lookup"><span data-stu-id="78cfb-130">E.g.</span></span> <span data-ttu-id="78cfb-131">GetInt32(int)</span><span class="sxs-lookup"><span data-stu-id="78cfb-131">GetInt32(int)</span></span>|<span data-ttu-id="78cfb-132">予期されるデータ型に基づいて列の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="78cfb-132">Gets column value based on the data type expected</span></span>|  
|<span data-ttu-id="78cfb-133">**IsDBNull(int)**</span><span class="sxs-lookup"><span data-stu-id="78cfb-133">**IsDBNull(int)**</span></span>|<span data-ttu-id="78cfb-134">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78cfb-134">Not supported.</span></span> <span data-ttu-id="78cfb-135">False を返します。</span><span class="sxs-lookup"><span data-stu-id="78cfb-135">Returns false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78cfb-136">参照</span><span class="sxs-lookup"><span data-stu-id="78cfb-136">See Also</span></span>  
 [<span data-ttu-id="78cfb-137">SAP アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="78cfb-137">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)