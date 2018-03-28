---
title: SAP アダプターで SAPDataReader クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a><span data-ttu-id="69302-102">SAP アダプターで SAPDataReader クラス</span><span class="sxs-lookup"><span data-stu-id="69302-102">SAPDataReader class in the SAP adapter</span></span>
<span data-ttu-id="69302-103">次のセクションではメソッドとプロパティの一覧表示、 **SAPDataReader**クラスです。</span><span class="sxs-lookup"><span data-stu-id="69302-103">The following section lists the methods and properties for the **SAPDataReader** class.</span></span> <span data-ttu-id="69302-104">これは、派生元**System.Data.Common.DbDataReader**です。</span><span class="sxs-lookup"><span data-stu-id="69302-104">This is derived from **System.Data.Common.DbDataReader**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="69302-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="69302-105">Supported Properties</span></span>  
  
|<span data-ttu-id="69302-106">名前</span><span class="sxs-lookup"><span data-stu-id="69302-106">Name</span></span>|<span data-ttu-id="69302-107">取得/設定</span><span class="sxs-lookup"><span data-stu-id="69302-107">Get/Set</span></span>|<span data-ttu-id="69302-108">Description</span><span class="sxs-lookup"><span data-stu-id="69302-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="69302-109">**[奥行]**</span><span class="sxs-lookup"><span data-stu-id="69302-109">**Depth**</span></span>|<span data-ttu-id="69302-110">取得</span><span class="sxs-lookup"><span data-stu-id="69302-110">Get</span></span>|<span data-ttu-id="69302-111">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="69302-111">Not supported.</span></span> <span data-ttu-id="69302-112">0 を返します。</span><span class="sxs-lookup"><span data-stu-id="69302-112">Returns 0.</span></span>|  
|<span data-ttu-id="69302-113">**FieldCount**</span><span class="sxs-lookup"><span data-stu-id="69302-113">**FieldCount**</span></span>|<span data-ttu-id="69302-114">取得</span><span class="sxs-lookup"><span data-stu-id="69302-114">Get</span></span>|<span data-ttu-id="69302-115">現在のレコード セット内のフィールドの数</span><span class="sxs-lookup"><span data-stu-id="69302-115">Number of fields in the current record set</span></span>|  
|<span data-ttu-id="69302-116">**IsClosed**</span><span class="sxs-lookup"><span data-stu-id="69302-116">**IsClosed**</span></span>|<span data-ttu-id="69302-117">取得</span><span class="sxs-lookup"><span data-stu-id="69302-117">Get</span></span>|<span data-ttu-id="69302-118">データ リーダーの状態を返します</span><span class="sxs-lookup"><span data-stu-id="69302-118">Returns status of data reader</span></span>|  
|<span data-ttu-id="69302-119">**RecordsAffected**</span><span class="sxs-lookup"><span data-stu-id="69302-119">**RecordsAffected**</span></span>|<span data-ttu-id="69302-120">取得</span><span class="sxs-lookup"><span data-stu-id="69302-120">Get</span></span>|<span data-ttu-id="69302-121">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="69302-121">Not supported.</span></span> <span data-ttu-id="69302-122">-1 を返します</span><span class="sxs-lookup"><span data-stu-id="69302-122">Returns -1</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="69302-123">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="69302-123">Supported Methods</span></span>  
  
|<span data-ttu-id="69302-124">名前</span><span class="sxs-lookup"><span data-stu-id="69302-124">Name</span></span>|<span data-ttu-id="69302-125">Description</span><span class="sxs-lookup"><span data-stu-id="69302-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="69302-126">**Close()**</span><span class="sxs-lookup"><span data-stu-id="69302-126">**Close()**</span></span>|<span data-ttu-id="69302-127">DataReader を終了します。</span><span class="sxs-lookup"><span data-stu-id="69302-127">Closes the DataReader</span></span>|  
|<span data-ttu-id="69302-128">**Get [メソッド]** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="69302-128">**Get [methods]** <sup>\*</sup></span></span><br /><br /> <span data-ttu-id="69302-129">ここで [メソッド] は、予想されるデータ型です。</span><span class="sxs-lookup"><span data-stu-id="69302-129">where [methods] is the expected data type.</span></span> <span data-ttu-id="69302-130">例:</span><span class="sxs-lookup"><span data-stu-id="69302-130">E.g.</span></span> <span data-ttu-id="69302-131">GetInt32(int)</span><span class="sxs-lookup"><span data-stu-id="69302-131">GetInt32(int)</span></span>|<span data-ttu-id="69302-132">予期されるデータ型に基づいて列の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="69302-132">Gets column value based on the data type expected</span></span>|  
|<span data-ttu-id="69302-133">**IsDBNull(int)**</span><span class="sxs-lookup"><span data-stu-id="69302-133">**IsDBNull(int)**</span></span>|<span data-ttu-id="69302-134">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="69302-134">Not supported.</span></span> <span data-ttu-id="69302-135">False を返します。</span><span class="sxs-lookup"><span data-stu-id="69302-135">Returns false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69302-136">参照</span><span class="sxs-lookup"><span data-stu-id="69302-136">See Also</span></span>  
 [<span data-ttu-id="69302-137">SAP アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="69302-137">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)