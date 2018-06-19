---
title: エラー - ルート ノードのクラス名が有効ではありません |Microsoft ドキュメント
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
ms.openlocfilehash: 2ff170609ef37b1d7f2b00a4d4ca3952b89eef9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240970"
---
# <a name="error---root-node-class-name-not-valid"></a><span data-ttu-id="e4e36-102">エラー - ルート ノードのクラス名が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="e4e36-102">Error - Root Node Class Name Not Valid</span></span>
<span data-ttu-id="e4e36-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="e4e36-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e4e36-104">BEC2012</span><span class="sxs-lookup"><span data-stu-id="e4e36-104">BEC2012</span></span>  
  
 <span data-ttu-id="e4e36-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="e4e36-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e4e36-106">**RootNode TypeName**このスキーマのルート ノードのいずれかのプロパティが無効です。</span><span class="sxs-lookup"><span data-stu-id="e4e36-106">The **RootNode TypeName** property of one of the root nodes in this schema is not valid.</span></span> <span data-ttu-id="e4e36-107">の値、 **RootNode TypeName**プロパティは、自動的に生成された c# クラス名の名前として使用する必要がある必要があります、有効な c# 識別子予約済みの BizTalk キーワードをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e4e36-107">Because the value of the **RootNode TypeName** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="e4e36-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="e4e36-108">**User Action**</span></span>  
  
 <span data-ttu-id="e4e36-109">対象のルート ノードを選択してから、Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで変更、 **RootNode TypeName**プロパティ値を正しい c# 識別子は、予約済みの BizTalk キーワードをします。</span><span class="sxs-lookup"><span data-stu-id="e4e36-109">Select the indicated root node, and then in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>