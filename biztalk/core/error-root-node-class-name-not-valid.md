---
title: エラー - ルート ノードのクラス名が有効ではありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootNodeClassNameNotValid
ms.assetid: 48b4f7e4-8c20-4e94-86be-1425ea62f8c5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca403fe7b99bf42f326485e6bd1788911d0dc32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388476"
---
# <a name="error---root-node-class-name-not-valid"></a><span data-ttu-id="481c6-102">エラー - ルート ノードのクラス名が無効です。</span><span class="sxs-lookup"><span data-stu-id="481c6-102">Error - Root Node Class Name Not Valid</span></span>
<span data-ttu-id="481c6-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="481c6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="481c6-104">BEC2012</span><span class="sxs-lookup"><span data-stu-id="481c6-104">BEC2012</span></span>  
  
 <span data-ttu-id="481c6-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="481c6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="481c6-106">**RootNode TypeName**のこのスキーマのルート ノードのいずれかのプロパティが無効です。</span><span class="sxs-lookup"><span data-stu-id="481c6-106">The **RootNode TypeName** property of one of the root nodes in this schema is not valid.</span></span> <span data-ttu-id="481c6-107">の値、 **RootNode TypeName**プロパティの自動的に生成された名前として使用されますC#クラス名、有効な場合がありますC#識別子、予約済みの BizTalk キーワードにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="481c6-107">Because the value of the **RootNode TypeName** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="481c6-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="481c6-108">**User Action**</span></span>  
  
 <span data-ttu-id="481c6-109">対象のルート ノードを選択し、次に、Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、変更、 **RootNode TypeName**プロパティが有効な値にC#識別子と予約済みの BizTalk キーワードではありません。</span><span class="sxs-lookup"><span data-stu-id="481c6-109">Select the indicated root node, and then in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>