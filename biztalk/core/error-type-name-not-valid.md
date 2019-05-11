---
title: エラー - 型名が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.typeNameNotValid
ms.assetid: 4c9bceeb-b009-4279-ad16-19af09e6b091
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7a99d3ca15b99c2c1a5669ddc2b89e8ae643eb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346307"
---
# <a name="error---type-name-not-valid"></a><span data-ttu-id="0a8c7-102">エラー - 型名が無効です。</span><span class="sxs-lookup"><span data-stu-id="0a8c7-102">Error - Type Name Not Valid</span></span>
<span data-ttu-id="0a8c7-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="0a8c7-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0a8c7-104">BEC2011</span><span class="sxs-lookup"><span data-stu-id="0a8c7-104">BEC2011</span></span>  
  
 <span data-ttu-id="0a8c7-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="0a8c7-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0a8c7-106">**型名**このスキーマ ファイルのプロパティが無効です。</span><span class="sxs-lookup"><span data-stu-id="0a8c7-106">The **Type Name** property of this schema file is not valid.</span></span> <span data-ttu-id="0a8c7-107">の値、**型名**プロパティの自動的に生成された名前として使用されますC#クラス名、有効な場合がありますC#識別子、予約済みの BizTalk キーワードにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0a8c7-107">Because the value of the **Type Name** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="0a8c7-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="0a8c7-108">**User Action**</span></span>  
  
 <span data-ttu-id="0a8c7-109">Microsoft® で関連するスキーマ ファイルを選択[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティが有効な値にC#識別子と予約済みの BizTalk キーワードではありません。</span><span class="sxs-lookup"><span data-stu-id="0a8c7-109">Select the relevant schema file in Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>