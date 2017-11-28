---
title: "エラー - フィールドの昇格が重複したプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.dupPropFieldPromo
ms.assetid: 59ac55c3-7613-493c-85a3-3965c250a3bb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87d9f6ee346f5aae98ea69c2ce4e00c4fa1d6dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---duplicate-property-field-promotion"></a><span data-ttu-id="61261-102">エラー - フィールドの昇格が重複したプロパティ</span><span class="sxs-lookup"><span data-stu-id="61261-102">Error - Duplicate Property Field Promotion</span></span>
<span data-ttu-id="61261-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="61261-103">**Error Code**</span></span>  
  
 <span data-ttu-id="61261-104">BEC2016</span><span class="sxs-lookup"><span data-stu-id="61261-104">BEC2016</span></span>  
  
 <span data-ttu-id="61261-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="61261-105">**Explanation**</span></span>  
  
 <span data-ttu-id="61261-106">このスキーマに複数のノードは、同じプロパティ フィールドとして昇格されている、**フィールド要素**同じプロパティ スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="61261-106">Multiple nodes in this schema are being promoted as Property Fields to the same **Field Element** node in the same property schema.</span></span>  
  
 <span data-ttu-id="61261-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="61261-107">**User Action**</span></span>  
  
 <span data-ttu-id="61261-108">使用して、**プロパティ フィールド**のタブ、**プロパティの昇格** ダイアログ ボックスを使用してアクセス、**プロパティの昇格**のプロパティ、**スキーマ**以外に、同じ関連付けられているプロパティ フィールドの昇格のいずれかをすべて削除するノード、**フィールド要素**プロパティ スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="61261-108">Use the **Property Fields** tab of the **Promote Properties** dialog box, accessed through the **Promote Properties** property of the **Schema** node, to delete all but one of the Property Field promotions that are associated with the same **Field Element** node in the property schema.</span></span> <span data-ttu-id="61261-109">新規に追加することがあります**フィールド要素**ノード、プロパティ スキーマを削除したプロモーションを独自に再度昇格できるように**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="61261-109">You may want to add new **Field Element** nodes to the property schema so that the deleted promotions can be re-promoted to their own **Field Element** nodes.</span></span>