---
title: エラー - 重複したプロパティ フィールドの昇格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.dupPropFieldPromo
ms.assetid: 59ac55c3-7613-493c-85a3-3965c250a3bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d105b1df7d934842b3c72be3a9e2068bc9e70021
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388934"
---
# <a name="error---duplicate-property-field-promotion"></a><span data-ttu-id="490db-102">エラー - フィールドの昇格が重複したプロパティ</span><span class="sxs-lookup"><span data-stu-id="490db-102">Error - Duplicate Property Field Promotion</span></span>
<span data-ttu-id="490db-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="490db-103">**Error Code**</span></span>  
  
 <span data-ttu-id="490db-104">BEC2016</span><span class="sxs-lookup"><span data-stu-id="490db-104">BEC2016</span></span>  
  
 <span data-ttu-id="490db-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="490db-105">**Explanation**</span></span>  
  
 <span data-ttu-id="490db-106">このスキーマに複数のノードは、同じプロパティ フィールドとして昇格されているが**フィールド要素**同じプロパティ スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="490db-106">Multiple nodes in this schema are being promoted as Property Fields to the same **Field Element** node in the same property schema.</span></span>  
  
 <span data-ttu-id="490db-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="490db-107">**User Action**</span></span>  
  
 <span data-ttu-id="490db-108">使用して、**プロパティ フィールド**のタブ、**プロパティの昇格** ダイアログ ボックスにアクセス、**プロパティの昇格**のプロパティ、**スキーマ**削除のすべてが同じに関連付けられているプロパティ フィールドの昇格のいずれかのノード**フィールド要素**プロパティ スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="490db-108">Use the **Property Fields** tab of the **Promote Properties** dialog box, accessed through the **Promote Properties** property of the **Schema** node, to delete all but one of the Property Field promotions that are associated with the same **Field Element** node in the property schema.</span></span> <span data-ttu-id="490db-109">新規追加したい場合があります**フィールド要素**プロパティ スキーマのノード削除のプロモーションを独自に再昇格できるように**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="490db-109">You may want to add new **Field Element** nodes to the property schema so that the deleted promotions can be re-promoted to their own **Field Element** nodes.</span></span>