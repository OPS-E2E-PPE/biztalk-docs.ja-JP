---
title: 警告 - 昇格フィールド XPath が見つかりません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoFieldXPathNotFound
ms.assetid: 21b8c240-5d6f-499d-8211-6e3f2ce2a79c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f45bd1539817f010864226d07b76ca2feee8b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="warning---promoted-field-xpath-not-found"></a><span data-ttu-id="c298f-102">警告 - 昇格フィールド XPath が見つかりません</span><span class="sxs-lookup"><span data-stu-id="c298f-102">Warning - Promoted Field XPath Not Found</span></span>
<span data-ttu-id="c298f-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c298f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c298f-104">BEC1005</span><span class="sxs-lookup"><span data-stu-id="c298f-104">BEC1005</span></span>  
  
 <span data-ttu-id="c298f-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c298f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c298f-106">プロパティ フィールドの昇格に対応するノードが、スキーマに存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c298f-106">The node corresponding to the indicated property field promotion may not exist in the schema.</span></span> <span data-ttu-id="c298f-107">BizTalk エディターは、複雑な XPath の仕様を解決できない昇格させたプロパティの XPath を編集する場合に、**インスタンス XPath の編集** ダイアログ ボックスで、昇格させようとしたノードを正しく認識できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c298f-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="c298f-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c298f-108">**User Action**</span></span>  
  
 <span data-ttu-id="c298f-109">この警告で昇格させたプロパティの XPath を変更することで表示されないようにしておくことができます、**インスタンス XPath の編集**内のセルからアクセスできるダイアログ ボックスで、**ノード パス**の列**プロパティ フィールドの一覧**テーブルに対して、**プロパティ フィールド** タブで、**プロパティの昇格** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c298f-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the **Property Field List** table on the **Property Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="c298f-110">アクセスすることができます、**プロパティの昇格**からダイアログ ボックス、**プロパティの昇格**のプロパティ、**スキーマ**、Microsoft® 内のノード[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c298f-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>