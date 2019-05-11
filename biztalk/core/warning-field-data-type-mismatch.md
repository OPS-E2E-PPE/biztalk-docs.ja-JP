---
title: 警告 - フィールド データ型の不一致 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.fieldDataTypeMismatch
ms.assetid: 0c15d926-1d05-404b-bb16-a5fe8bc3575d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50d74dfb16dbd03eb92e6880681721608389840a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393676"
---
# <a name="warning---field-data-type-mismatch"></a><span data-ttu-id="d82dc-102">警告 - フィールド データ型が一致しません</span><span class="sxs-lookup"><span data-stu-id="d82dc-102">Warning - Field Data Type Mismatch</span></span>
<span data-ttu-id="d82dc-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d82dc-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d82dc-104">BEC1002</span><span class="sxs-lookup"><span data-stu-id="d82dc-104">BEC1002</span></span>  
  
 <span data-ttu-id="d82dc-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d82dc-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d82dc-106">**データ型**違っているように、対象ノードのプロパティが見つかりました、**データ型**のプロパティ、**フィールド要素**ノードを昇格で、対応するプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="d82dc-106">The **Data Type** property of the indicated node was found to be different than the **Data Type** property of the **Field Element** node to which it is being promoted in the corresponding property schema.</span></span> <span data-ttu-id="d82dc-107">スキーマ内のノードのデータ型に割り当てられているデータ型と一致する必要があります、**フィールド要素**、そのプロパティのフィールドを昇格するノードが使用または少なくとも、割り当てられているデータ型が同じ共通言語ランタイム (CLR) 型にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d82dc-107">The data type of a node in a schema should match the data type assigned to the **Field Element** node used for its Property Field promotion, or at least, the assigned data types should map to the same common language runtime (CLR) type.</span></span>  
  
 <span data-ttu-id="d82dc-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d82dc-108">**User Action**</span></span>  
  
 <span data-ttu-id="d82dc-109">変更、**データ型**対象のノードのプロパティと**フィールド要素**ノードを昇格、同じデータを値を入力または少なくともデータ型値の同じ CLR データ型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d82dc-109">Change the **Data Type** properties of the indicated node and the **Field Element** node to which it is being promoted to the same data type value, or at least to data type values that map to the same CLR data type.</span></span>