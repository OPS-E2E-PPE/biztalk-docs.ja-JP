---
title: "警告 - フィールド データ型の不一致 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.fieldDataTypeMismatch
ms.assetid: 0c15d926-1d05-404b-bb16-a5fe8bc3575d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af42f5c921333e34c9ee219020cdb0fba97a7b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="warning---field-data-type-mismatch"></a><span data-ttu-id="5177b-102">警告 - フィールド データ型が一致しません</span><span class="sxs-lookup"><span data-stu-id="5177b-102">Warning - Field Data Type Mismatch</span></span>
<span data-ttu-id="5177b-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="5177b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="5177b-104">BEC1002</span><span class="sxs-lookup"><span data-stu-id="5177b-104">BEC1002</span></span>  
  
 <span data-ttu-id="5177b-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="5177b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="5177b-106">**データ型**以外にする対象のノードのプロパティが見つかりました、**データ型**のプロパティ、**フィールド要素**ノードにはされている上位変換先で、対応するプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="5177b-106">The **Data Type** property of the indicated node was found to be different than the **Data Type** property of the **Field Element** node to which it is being promoted in the corresponding property schema.</span></span> <span data-ttu-id="5177b-107">スキーマ内のノードのデータ型に割り当てられているデータ型に一致する必要があります、**フィールド要素**プロパティ フィールドを昇格するノードが使用またはには、少なくとも、割り当てられているデータ型が同じ共通言語ランタイム (CLR) 型に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5177b-107">The data type of a node in a schema should match the data type assigned to the **Field Element** node used for its Property Field promotion, or at least, the assigned data types should map to the same common language runtime (CLR) type.</span></span>  
  
 <span data-ttu-id="5177b-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="5177b-108">**User Action**</span></span>  
  
 <span data-ttu-id="5177b-109">変更、**データ型**のノードのプロパティと**フィールド要素**ノードをそれに昇格されて、同じデータ値を入力するか、少なくともデータに値型は同じ CLR データ型にマップします。</span><span class="sxs-lookup"><span data-stu-id="5177b-109">Change the **Data Type** properties of the indicated node and the **Field Element** node to which it is being promoted to the same data type value, or at least to data type values that map to the same CLR data type.</span></span>