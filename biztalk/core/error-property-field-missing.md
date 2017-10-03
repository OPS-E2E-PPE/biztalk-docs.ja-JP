---
title: "エラー - プロパティ フィールドが見つかりません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d77311e4c8585cfb7f6108364e6a5085619595a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-field-missing"></a><span data-ttu-id="a5bbc-102">エラー - プロパティ フィールドが見つかりません</span><span class="sxs-lookup"><span data-stu-id="a5bbc-102">Error - Property Field Missing</span></span>
<span data-ttu-id="a5bbc-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="a5bbc-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a5bbc-104">BEC2008</span><span class="sxs-lookup"><span data-stu-id="a5bbc-104">BEC2008</span></span>  
  
 <span data-ttu-id="a5bbc-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="a5bbc-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a5bbc-106">このスキーマのノードに昇格されて、**フィールド要素**対応するプロパティ スキーマが存在しないノード。</span><span class="sxs-lookup"><span data-stu-id="a5bbc-106">The indicated node in this schema is being promoted to a **Field Element** node in the corresponding property schema that does not exist.</span></span> <span data-ttu-id="a5bbc-107">このような状況が発生することがときに、**フィールド要素**ノードの削除、またはプロパティの昇格の対象として使用された後、プロパティ スキーマの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="a5bbc-107">This condition can occur when a **Field Element** node is removed from, or renamed in, a property schema after it has been used as the target of a property promotion.</span></span>  
  
 <span data-ttu-id="a5bbc-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="a5bbc-108">**User Action**</span></span>  
  
 <span data-ttu-id="a5bbc-109">不足しているが含まれているように、プロパティ スキーマを変更するか**フィールド要素**ノード、またはを使用して、**プロパティの昇格** ダイアログ ボックスを削除またはそれ以外の場合、関連するプロパティの昇格を変更します。</span><span class="sxs-lookup"><span data-stu-id="a5bbc-109">Either modify the property schema so that it contains the missing **Field Element** node, or use the **Promote Properties** dialog box to delete or otherwise modify the relevant property promotion.</span></span>