---
title: 警告 - に昇格させたフィールド XPath が見つかりません |Microsoft Docs
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
ms.openlocfilehash: 59534a03155ca0a8f43cf4f4e8018718e0fd8305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393668"
---
# <a name="warning---promoted-field-xpath-not-found"></a><span data-ttu-id="b6773-102">警告 - に昇格させたフィールド XPath が見つかりません</span><span class="sxs-lookup"><span data-stu-id="b6773-102">Warning - Promoted Field XPath Not Found</span></span>
<span data-ttu-id="b6773-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="b6773-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b6773-104">BEC1005</span><span class="sxs-lookup"><span data-stu-id="b6773-104">BEC1005</span></span>  
  
 <span data-ttu-id="b6773-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="b6773-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b6773-106">プロパティ フィールドの昇格に対応するノードは、スキーマが存在しません。</span><span class="sxs-lookup"><span data-stu-id="b6773-106">The node corresponding to the indicated property field promotion may not exist in the schema.</span></span> <span data-ttu-id="b6773-107">BizTalk エディターは、複雑な XPath の仕様を解決することはできません、昇格させたプロパティの XPath を編集した場合に、**インスタンス XPath の編集**がダイアログ ボックスで、または昇格させようとしたノードを正しく認識しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6773-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="b6773-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="b6773-108">**User Action**</span></span>  
  
 <span data-ttu-id="b6773-109">この警告の XPath で昇格させたプロパティを変更することで表示されないように、**インスタンス XPath の編集** ダイアログ ボックスでは、内のセルからアクセスできる、**ノード パス**の列**プロパティ フィールドの一覧**テーブルに対して、**プロパティ フィールド** タブで、**プロパティの昇格** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b6773-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the **Property Field List** table on the **Property Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="b6773-110">アクセスすることができます、**プロパティの昇格** ダイアログ ボックスから、**プロパティの昇格**のプロパティ、**スキーマ**Microsoft® ノード[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b6773-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>