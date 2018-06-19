---
title: エラー - 型名が有効ではありません |Microsoft ドキュメント
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
ms.openlocfilehash: 7dac6d85d3b16ec691a4cc73b179515b70686791
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241418"
---
# <a name="error---type-name-not-valid"></a><span data-ttu-id="bb9d9-102">エラー - 型名が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="bb9d9-102">Error - Type Name Not Valid</span></span>
<span data-ttu-id="bb9d9-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="bb9d9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="bb9d9-104">BEC2011</span><span class="sxs-lookup"><span data-stu-id="bb9d9-104">BEC2011</span></span>  
  
 <span data-ttu-id="bb9d9-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="bb9d9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="bb9d9-106">**型名**このスキーマ ファイルのプロパティが無効です。</span><span class="sxs-lookup"><span data-stu-id="bb9d9-106">The **Type Name** property of this schema file is not valid.</span></span> <span data-ttu-id="bb9d9-107">の値、**型名**プロパティは、自動的に生成された c# クラス名の名前として使用する必要がある必要があります、有効な c# 識別子予約済みの BizTalk キーワードをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bb9d9-107">Because the value of the **Type Name** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="bb9d9-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="bb9d9-108">**User Action**</span></span>  
  
 <span data-ttu-id="bb9d9-109">Microsoft® で関連するスキーマ ファイルを選択[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティ値が有効な c# 識別子は、予約済みの BizTalk キーワードではありません。</span><span class="sxs-lookup"><span data-stu-id="bb9d9-109">Select the relevant schema file in Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>