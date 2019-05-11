---
title: SAP アダプターの SAPDataReader クラス |Microsoft Docs
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05550dea2c42d8227e0c135759eea24238c0e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372956"
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a><span data-ttu-id="698e1-102">SAP アダプターの SAPDataReader クラス</span><span class="sxs-lookup"><span data-stu-id="698e1-102">SAPDataReader class in the SAP adapter</span></span>
<span data-ttu-id="698e1-103">メソッドおよびプロパティを次のセクションの一覧、 **SAPDataReader**クラス。</span><span class="sxs-lookup"><span data-stu-id="698e1-103">The following section lists the methods and properties for the **SAPDataReader** class.</span></span> <span data-ttu-id="698e1-104">これは、派生元**System.Data.Common.DbDataReader**します。</span><span class="sxs-lookup"><span data-stu-id="698e1-104">This is derived from **System.Data.Common.DbDataReader**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="698e1-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="698e1-105">Supported Properties</span></span>  
  
|<span data-ttu-id="698e1-106">名前</span><span class="sxs-lookup"><span data-stu-id="698e1-106">Name</span></span>|<span data-ttu-id="698e1-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="698e1-107">Get/Set</span></span>|<span data-ttu-id="698e1-108">説明</span><span class="sxs-lookup"><span data-stu-id="698e1-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="698e1-109">**[奥行]**</span><span class="sxs-lookup"><span data-stu-id="698e1-109">**Depth**</span></span>|<span data-ttu-id="698e1-110">取得</span><span class="sxs-lookup"><span data-stu-id="698e1-110">Get</span></span>|<span data-ttu-id="698e1-111">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="698e1-111">Not supported.</span></span> <span data-ttu-id="698e1-112">0 を返します。</span><span class="sxs-lookup"><span data-stu-id="698e1-112">Returns 0.</span></span>|  
|<span data-ttu-id="698e1-113">**FieldCount**</span><span class="sxs-lookup"><span data-stu-id="698e1-113">**FieldCount**</span></span>|<span data-ttu-id="698e1-114">取得</span><span class="sxs-lookup"><span data-stu-id="698e1-114">Get</span></span>|<span data-ttu-id="698e1-115">現在のレコード セット内のフィールドの数</span><span class="sxs-lookup"><span data-stu-id="698e1-115">Number of fields in the current record set</span></span>|  
|<span data-ttu-id="698e1-116">**IsClosed**</span><span class="sxs-lookup"><span data-stu-id="698e1-116">**IsClosed**</span></span>|<span data-ttu-id="698e1-117">取得</span><span class="sxs-lookup"><span data-stu-id="698e1-117">Get</span></span>|<span data-ttu-id="698e1-118">データ リーダーの状態を返します</span><span class="sxs-lookup"><span data-stu-id="698e1-118">Returns status of data reader</span></span>|  
|<span data-ttu-id="698e1-119">**RecordsAffected**</span><span class="sxs-lookup"><span data-stu-id="698e1-119">**RecordsAffected**</span></span>|<span data-ttu-id="698e1-120">取得</span><span class="sxs-lookup"><span data-stu-id="698e1-120">Get</span></span>|<span data-ttu-id="698e1-121">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="698e1-121">Not supported.</span></span> <span data-ttu-id="698e1-122">-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="698e1-122">Returns -1</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="698e1-123">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="698e1-123">Supported Methods</span></span>  
  
|<span data-ttu-id="698e1-124">名前</span><span class="sxs-lookup"><span data-stu-id="698e1-124">Name</span></span>|<span data-ttu-id="698e1-125">説明</span><span class="sxs-lookup"><span data-stu-id="698e1-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="698e1-126">**Close()**</span><span class="sxs-lookup"><span data-stu-id="698e1-126">**Close()**</span></span>|<span data-ttu-id="698e1-127">DataReader を閉じる</span><span class="sxs-lookup"><span data-stu-id="698e1-127">Closes the DataReader</span></span>|  
|<span data-ttu-id="698e1-128">**Get [メソッド]** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="698e1-128">**Get [methods]** <sup>\*</sup></span></span><br /><br /> <span data-ttu-id="698e1-129">場所 [メソッド] は、必要なデータ型です。</span><span class="sxs-lookup"><span data-stu-id="698e1-129">where [methods] is the expected data type.</span></span> <span data-ttu-id="698e1-130">例:</span><span class="sxs-lookup"><span data-stu-id="698e1-130">E.g.</span></span> <span data-ttu-id="698e1-131">GetInt32(int)</span><span class="sxs-lookup"><span data-stu-id="698e1-131">GetInt32(int)</span></span>|<span data-ttu-id="698e1-132">必要なデータ型に基づいて列の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="698e1-132">Gets column value based on the data type expected</span></span>|  
|<span data-ttu-id="698e1-133">**IsDBNull(int)**</span><span class="sxs-lookup"><span data-stu-id="698e1-133">**IsDBNull(int)**</span></span>|<span data-ttu-id="698e1-134">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="698e1-134">Not supported.</span></span> <span data-ttu-id="698e1-135">False を返します。</span><span class="sxs-lookup"><span data-stu-id="698e1-135">Returns false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="698e1-136">参照</span><span class="sxs-lookup"><span data-stu-id="698e1-136">See Also</span></span>  
 [<span data-ttu-id="698e1-137">SAP アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="698e1-137">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)