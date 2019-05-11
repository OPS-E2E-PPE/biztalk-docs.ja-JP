---
title: エラー - プロパティ フィールドが見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b1ce11e6b4bb140f6effe657bff060410a0e2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388493"
---
# <a name="error---property-field-missing"></a><span data-ttu-id="2adf6-102">エラー - プロパティ フィールドが見つかりません</span><span class="sxs-lookup"><span data-stu-id="2adf6-102">Error - Property Field Missing</span></span>
<span data-ttu-id="2adf6-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="2adf6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2adf6-104">BEC2008</span><span class="sxs-lookup"><span data-stu-id="2adf6-104">BEC2008</span></span>  
  
 <span data-ttu-id="2adf6-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="2adf6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2adf6-106">このスキーマのノードに昇格されて、**フィールド要素**対応するプロパティ スキーマが存在しないノード。</span><span class="sxs-lookup"><span data-stu-id="2adf6-106">The indicated node in this schema is being promoted to a **Field Element** node in the corresponding property schema that does not exist.</span></span> <span data-ttu-id="2adf6-107">この条件が発生することがときに、**フィールド要素**ノードを削除、またはプロパティの昇格の対象として使用された後、プロパティ スキーマの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="2adf6-107">This condition can occur when a **Field Element** node is removed from, or renamed in, a property schema after it has been used as the target of a property promotion.</span></span>  
  
 <span data-ttu-id="2adf6-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="2adf6-108">**User Action**</span></span>  
  
 <span data-ttu-id="2adf6-109">プロパティ スキーマを変更か、存在しないように**フィールド要素**ノード、または使用して、**プロパティの昇格** ダイアログ ボックスを削除またはそれ以外の場合、関連するプロパティの昇格を変更します。</span><span class="sxs-lookup"><span data-stu-id="2adf6-109">Either modify the property schema so that it contains the missing **Field Element** node, or use the **Promote Properties** dialog box to delete or otherwise modify the relevant property promotion.</span></span>