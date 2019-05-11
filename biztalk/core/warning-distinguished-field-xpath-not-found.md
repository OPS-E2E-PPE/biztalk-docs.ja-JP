---
title: 警告 - 識別フィールドの XPath が見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.distingFieldXPathNotFound
ms.assetid: a925c39c-9ae1-4334-b329-aa2f5afd97ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48306b164a3ce3bc0ef999ad8eb7d0d6bbedd444
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393719"
---
# <a name="warning---distinguished-field-xpath-not-found"></a><span data-ttu-id="d69db-102">警告 - 識別フィールドの XPath が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="d69db-102">Warning - Distinguished Field XPath Not Found</span></span>
<span data-ttu-id="d69db-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d69db-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d69db-104">BEC1006</span><span class="sxs-lookup"><span data-stu-id="d69db-104">BEC1006</span></span>  
  
 <span data-ttu-id="d69db-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d69db-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d69db-106">識別フィールドの昇格に対応するノードは、スキーマが存在しません。</span><span class="sxs-lookup"><span data-stu-id="d69db-106">The node corresponding to the indicated Distinguished Field promotion may not exist in the schema.</span></span> <span data-ttu-id="d69db-107">BizTalk エディターは、複雑な XPath の仕様を解決することはできません、昇格させたプロパティの XPath を編集した場合に、**インスタンス XPath の編集**がダイアログ ボックスで、または昇格させようとしたノードを正しく認識しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d69db-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="d69db-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d69db-108">**User Action**</span></span>  
  
 <span data-ttu-id="d69db-109">この警告の XPath で昇格させたプロパティを変更することで表示されないように、**インスタンス XPath の編集** ダイアログ ボックスでは、内のセルからアクセスできる、**ノード パス**上のテーブルの列、**識別フィールド** タブで、**プロパティの昇格** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d69db-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the table on the **Distinguished Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="d69db-110">アクセスすることができます、**プロパティの昇格** ダイアログ ボックスから、**プロパティの昇格**のプロパティ、**スキーマ**Microsoft® ノード[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d69db-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>